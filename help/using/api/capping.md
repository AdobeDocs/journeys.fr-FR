---
product: adobe campaign
title: Description de l’API de limitation
description: En savoir plus sur l’API de limitation.
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
source-git-commit: 1f91bae24dfcb291dd354e4bff9eab85afdaf5a1
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 99%

---


# Utilisation de l’API de limitation {#work}

L’API de limitation vous permet de créer, configurer et suivre vos configurations de limitation.

## Description de l’API de limitation

| Méthode | Chemin | Description |
|---|---|---|
| [!DNL POST] | list/endpointConfigs | Obtention d’une liste des configurations de limitation des points d’entrée |
| [!DNL POST] | /endpointConfigs | Création d’une configuration de limitation des points d’entrée |
| [!DNL POST] | /endpointConfigs/`{uid}`/deploy | Déploiement d’une configuration de limitation des points d’entrée |
| [!DNL POST] | /endpointConfigs/`{uid}`/undeploy | Annulation du déploiement d’une configuration de limitation des points d’entrée |
| [!DNL POST] | /endpointConfigs/`{uid}`/canDeploy | Vérification de la possibilité de déployer ou non une configuration de limitation des points d’entrée |
| [!DNL PUT] | /endpointConfigs/`{uid}` | Mise à jour de la configuration de limitation des points d’entrée |
| [!DNL GET] | /endpointConfigs/`{uid}` | Récupération d’une configuration de limitation des points d’entrée |
| [!DNL DELETE] | /endpointConfigs/`{uid}` | Suppression d’une configuration de limitation des points d’entrée |

Lorsqu’une configuration est créée ou mise à jour, une vérification est automatiquement effectuée pour garantir la syntaxe et l’intégrité de la payload.
Si certains problèmes se produisent, l’opération renvoie un avertissement ou des erreurs pour vous aider à corriger la configuration.

## Configuration du point d’entrée

Voici la structure de base d’une configuration de point d’entrée :

```
{
    "url": "<endpoint URL>",  //wildcards are allowed in the endpoint URL
    "methods": [ "<HTTP method such as GET, POST, >, ...],
    "services": {
        "<service name>": { . //must be "action" or "dataSource" 
            "maxHttpConnections": <max connections count to the endpoint>
            "rating": {          
                "maxCallsCount": <max calls to be performed in the period defined by period/timeUnit>,
                "periodInMs": <integer value greater than 0>
            }
        },
        ...
    }
}
```

### Exemple :

```
`{
  "url": "https://api.example.org/data/2.5/*",
  "methods": [
    "GET"
  ],
  "services": {
    "dataSource": {
      "maxHttpConnections": 30000,
      "rating": {
        "maxCallsCount": 5000,
        "periodInMs": 1000
      }
    }
  },
  "orgId": "<IMS Org Id>"
}
```

## Avertissement et erreurs

Lorsqu’une méthode **canDeploy** est appelée, le processus valide la configuration et renvoie le statut de validation identifié par son identifiant unique, au choix :

```
"ok" or "error"
```

Les erreurs potentielles sont les suivantes :

* **ERR_ENDPOINTCONFIG_100**: capping config: missing or invalid url
* **ERR_ENDPOINTCONFIG_101**: capping config: malformed url
* **ERR_ENDPOINTCONFIG_102**: capping config: malformed url: wildchar in url not allowed in host:port
* **ERR_ENDPOINTCONFIG_103**: capping config: missing HTTP methods
* **ERR_ENDPOINTCONFIG_104**: capping config: no call rating defined
* **ERR_ENDPOINTCONFIG_107**: capping config: invalid max calls count (maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**: capping config: invalid max calls count (periodInMs)
* **ERR_ENDPOINTCONFIG_111**: capping config: can&#39;t create endpoint config: invalid payload
* **ERR_ENDPOINTCONFIG_112**: capping config: can&#39;t create endpoint config: expecting a JSON payload
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: invalid service name `<!--<given value>-->`: must be &#39;dataSource&#39; or &#39;action&#39;

L’avertissement potentiel est :

**ERR_ENDPOINTCONFIG_106**: capping config: max HTTP connections not defined: no limitation by default

## Cas d’utilisation

Cette section décrit les cinq principaux cas d’utilisation que vous pouvez mettre en œuvre pour gérer la configuration des limitations dans [!DNL Journey Orchestration].

Pour vous aider dans les tests et la configuration, une collection Postman est disponible [ici](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

Elle a été créée pour partager la collection de variables Postman générée par le biais des options __[Intégrations de la console Adobe I/O](https://console.adobe.io/integrations) > Essayez-la > Télécharger pour Postman__, qui génère un fichier d’environnement Postman contenant les valeurs d’intégration sélectionnées.

Une fois le téléchargement puis le chargement effectués dans Postman, vous devez ajouter trois variables : `{JO_HOST}`, `{BASE_PATH}` et `{SANDBOX_NAME}`.
* `{JO_HOST}` : URL de passerelle [!DNL Journey Orchestration]
* `{BASE_PATH}` : point d’entrée pour l’API. La valeur est &#39;/authoring&#39;
* `{SANDBOX_NAME}` : l’en-tête **x-sandbox-name** (par exemple, « prod ») correspondant au nom sandbox dans lequel les opérations d’API auront lieu. Pour plus d’informations, consultez la [Présentation des sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=fr).

Dans la section suivante, vous trouverez la liste classée des appels API REST pour effectuer le cas d’utilisation.

Cas d’utilisation n°1 : **création et déploiement d’une nouvelle configuration de limitation**

1. list
1. create
1. candeploy
1. deploy

Cas d’utilisation n°2 : **mise à jour et déploiement d’une configuration de limitation non encore déployée**

1. list
1. get
1. update
1. candeploy
1. deploy

Cas d’utilisation n°3 : **annulation du déploiement et suppression d’une configuration de limitation déployée**

1. list
1. undeploy
1. delete

Cas d’utilisation n°4 : **suppression d’une configuration de limitation déployée**

En un seul appel d’API, vous pouvez annuler le déploiement et supprimer la configuration à l’aide du paramètre forceDelete.
1. list
1. delete, avec le paramètre forceDelete

Cas d’utilisation n°5 : **mise à jour d’une configuration de limitation déjà déployée**

1. list
1. get
1. update
1. undeploy
1. candeploy
1. deploy
