---
title: Description de l’API de limitation
description: En savoir plus sur l’API de limitation.
contentOwner: sauviat
products: journeys
audience: audiences
content-type: reference
topic-tags: journeys
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ca4dc447d8ae4ee18e50d7e9a18faf3fa47ae223
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 100%

---


# Utilisation de l’API de limitation

## Introduction

Les API de [!DNL Journey Orchestration] prennent en charge 5 000 événements/seconde, mais certains systèmes ou API externes ne peuvent pas atteindre un débit équivalent. C’est la raison pour laquelle [!DNL Journey Orchestration] propose une fonctionnalité dédiée, appelée API de limitation, pour surveiller et limiter la vitesse imposée aux systèmes externes.

Lors de la configuration d’une source de données, vous allez définir une connexion à un système pour récupérer des informations supplémentaires, qui seront ensuite utilisées dans vos parcours. Pour une définition d’action, vous allez configurer la connexion d’un système tiers pour envoyer des messages ou des appels d’API. Pour chaque appel d’API effectué par Journey, l’API de limitation est interrogée à l’aide d’un appel transmis par le moteur d’API. Si une limite est définie, l’appel est rejeté, ce qui permet d’éviter une surcharge du système externe.

Pour en savoir plus sur la configuration d’une action ou d’une source de données, voir les sections [À propos des actions](https://docs.adobe.com/content/help/fr-FR/journeys/using/action-journeys/action.html) et [À propos des sources de données](https://docs.adobe.com/content/help/fr-FR/journeys/using/data-source-journeys/about-data-sources.html)


## Ressources

>[!NOTE]
>
>L’API de limitation de [!DNL Journey Orchestration] est décrite dans un fichier Swagger disponible [ici](https://adobedocs.github.io/JourneyAPI/docs/).

Pour utiliser cette API avec votre instance [!DNL Journey Orchestration], vous devez utiliser la console Adobe I/O. Vous pouvez y accéder selon les indications de la section [Prise en main d’Adobe Developer Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md), puis les différentes sections de cette page.

Pour tester et préparer votre intégration, une collection Postman est disponible [ici](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

## Authentification

### Configuration de l’accès aux API

La configuration de l’accès aux API [!DNL Journey Orchestration] est effectuée comme suit. Chacune de ces étapes est détaillée dans la [documentation Adobe I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Pour gérer les certificats dans Adobe I/O, assurez-vous de disposer des droits d’<b>administrateur système</b> sur l’organisation ou d’un [compte de développeur](https://helpx.adobe.com/fr/enterprise/using/manage-developers.html) dans Admin Console.

1. **Vérifiez que vous disposez d’un certificat numérique**, ou créez-en un si nécessaire. Les clés publique et privée fournies avec le certificat sont nécessaires dans les étapes suivantes.
1. **Créez une nouvelle intégration avec[!DNL Journey Orchestration]Service** dans Adobe I/O et configurez-la. L’accès au profil du produit est nécessaire pour [!DNL Journey Orchestration] et Adobe Experience Platform. Vos informations d’identification seront alors générées (clé d’API, secret client...).
1. **Créez un jeton Web JSON (JWT)** à partir des informations d’identification précédemment générées, et signez-le avec votre clé privée. Le jeton JWT code toutes les informations d’identité et de sécurité dont Adobe a besoin pour vérifier votre identité et vous accorder l’accès à l’API. Cette étape est présentée dans cette [section](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Échangez votre jeton JWT pour un jeton d’accès** à l’aide d’une requête POST ou via l’interface de Developer Console. Ce jeton d’accès devra être utilisé dans chaque en-tête de vos requêtes d’API.

Pour établir une session d’API Adobe I/O de service à service sécurisée, chaque requête adressée à un service Adobe doit inclure les informations ci-dessous dans l’en-tête d’autorisation.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZATION>** : il s’agit de votre ORGANIZATION ID personnel, fourni par Adobe pour chacune de vos instances :

   * &lt;ORGANIZATION> : votre instance de production

   Pour obtenir votre valeur ORGANIZATION ID, contactez votre administrateur ou votre contact technique Adobe. Vous pouvez également la récupérer dans Adobe I/O lors de la création d’une nouvelle intégration, dans la liste des licences (voir la <a href="https://www.adobe.io/authentication.html">documentation Adobe I/O</a>).

* **&lt;ACCESS_TOKEN>** : votre jeton d’accès personnel, récupéré lors de l’échange de votre JWT par le biais d’une requête POST.

* **&lt;API_KEY>** : votre clé d’API personnelle. Elle est fournie dans Adobe I/O après la création d’une nouvelle intégration avec [!DNL Journey Orchestration] Service.



## Description de l’API de limitation

L’API de limitation vous permet de créer, configurer et suivre vos configurations de limitation.

| Méthodologie | Chemin | Description |
|---|---|---|
| [!DNL POST] | list/endpointConfigs | Obtention d’une liste des configurations de limitation des points d’entrée |
| [!DNL POST] | /endpointConfigs | Création d’une configuration de limitation des points d’entrée |
| [!DNL POST] | /endpointConfigs/{uid}/deploy | Déploiement d’une configuration de limitation des points d’entrée |
| [!DNL POST] | /endpointConfigs/{uid}/undeploy | Annulation du déploiement d’une configuration de limitation des points d’entrée |
| [!DNL POST] | /endpointConfigs/{uid}/canDeploy | Vérification de la possibilité de déployer ou non une configuration de limitation des points d’entrée |
| [!DNL PUT] | /endpointConfigs/{uid} | Mise à jour de la configuration de limitation des points d’entrée |
| [!DNL GET] | /endpointConfigs/{uid} | Récupération d’une configuration de limitation des points d’entrée |
| [!DNL DELETE] | /endpointConfigs/{uid} | Suppression d’une configuration de limitation des points d’entrée |

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
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: invalid service name <!--<given value>-->: must be &#39;dataSource&#39; or &#39;action&#39;


L’avertissement potentiel est :

**ERR_ENDPOINTCONFIG_106**: capping config: max HTTP connections not defined: no limitation by default



## Cas d’utilisation

Cette section décrit les cinq principaux cas d’utilisation que vous pouvez mettre en œuvre pour gérer la configuration des limitations dans [!DNL Journey Orchestration].

Pour vous aider dans les tests et la configuration, une collection Postman est disponible [ici](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

Elle a été créée pour partager la collection de variables Postman générée par le biais des options __[Intégrations de la console Adobe I/O](https://console.adobe.io/integrations) > Essayez-la > Télécharger pour Postman__, qui génère un fichier d’environnement Postman contenant les valeurs d’intégration sélectionnées.

Une fois le téléchargement puis le chargement effectués dans Postman, vous devez ajouter trois variables : `{JO_HOST}`, `{Base_Path}` et `{SANDBOX_NAME}`.
* `{JO_HOST}` : URL de passerelle [!DNL Journey Orchestration]
* `{BASE_PATH}` : point d’entrée pour l’API. La valeur est &#39;/authoring&#39;
* `{SANDBOX_NAME}` : l’en-tête **x-sandbox-name** (par exemple, « prod ») correspondant au nom sandbox dans lequel les opérations d’API auront lieu. Pour plus d’informations, consultez la [présentation des sandbox](https://docs.adobe.com/content/help/fr-FR/experience-platform/sandbox/home.html).

Dans la section suivante, vous trouverez la liste classée des appels API REST pour effectuer le cas d&#39;utilisation.

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

