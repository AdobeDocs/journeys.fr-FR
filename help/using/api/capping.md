---
title: Description de l’API de plafonnement
description: En savoir plus sur l’API de plafonnement.
contentOwner: sauviat
products: journeys
audience: audiences
content-type: reference
topic-tags: journeys
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: tm+mt
source-wordcount: '1065'
ht-degree: 25%

---


# Utilisation de l’API de plafonnement

## Introduction

[!DNL Journey Orchestration]Les API de prennent en charge 5 000 événements/secondes, mais certains systèmes ou API externes ne peuvent pas avoir un débit équivalent. C&#39;est pourquoi [!DNL Journey Orchestration] est fourni avec une fonctionnalité dédiée appelée API de plafonnement pour surveiller et limiter la vitesse que nous imposons aux systèmes externes.

Lors de la configuration d&#39;une source de données, vous allez définir une connexion à un système pour récupérer des informations supplémentaires qui seront utilisées dans vos voyages, ou pour une définition d&#39;action, vous allez configurer la connexion d&#39;un système tiers pour envoyer des messages ou des appels d&#39;API. Chaque fois qu&#39;un appel d&#39;API est effectué par Journey, l&#39;API de plafonnement est interrogée, l&#39;appel est transmis par le moteur d&#39;API. Si une limite est définie, l&#39;appel est rejeté et le système externe ne sera pas surchargé.

Pour en savoir plus sur l’action ou la configuration des sources de données, voir [A propos des actions](https://docs.adobe.com/content/help/en/journeys/using/action-journeys/action.html) ou [A propos des sources de données.](https://docs.adobe.com/content/help/en/journeys/using/data-source-journeys/about-data-sources.html)


## Ressources

L’API [!DNL Journey Orchestration] de plafonnement est décrite dans un fichier Swagger disponible [ici](https://adobedocs.github.io/JourneyAPI/docs/).

Pour utiliser cette API avec votre [!DNL Journey Orchestration] instance, vous devez utiliser la console AdobeIO. Vous pouvez le début en suivant cette [section Prise en main de Adobe Developer Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) , puis en utilisant les sections de cette page.

Pour tester et préparer votre intégration, une collection Postman est disponible [ici](https://github.com/AdobeDocs/JourneyAPI/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

## Authentification

### Configuration de l’accès aux API

[!DNL Journey Orchestration] L’accès à l’API est configuré par les étapes ci-dessous. Chacune de ces étapes est détaillée dans la documentation [Adobe IO](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Pour gérer les certificats dans Adobe IO, assurez-vous de disposer des droits d’<b>administrateur système</b> sur l’organisation ou d’un <a href="https://helpx.adobe.com/enterprise/using/manage-developers.html">compte de développeur </a> dans la console d’administration.

1. **Vérifiez que vous disposez d’un certificat numérique**, ou créez-en un si nécessaire. Les clés publique et privée fournies avec le certificat sont nécessaires dans les étapes suivantes.
1. **[!DNL Journey Orchestration]Créez une nouvelle intégration avec Service** dans Adobe IO et configurez-la. L’accès au profil du produit est nécessaire pour [!DNL Journey Orchestration] Adobe Experience Platform. Vos informations d’identification seront alors générées (clé d’API, secret client...).
1. **Créez un jeton Web JSON (JWT)** à partir des informations d’identification précédemment générées, et signez-le avec votre clé privée. Le jeton JWT code toutes les informations d’identité et de sécurité dont Adobe a besoin pour vérifier votre identité et vous accorder l’accès à l’API. Cette étape est détaillée dans cette [section](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Échangez votre JWT pour un Jeton d&#39;accès** via une demande POST ou via l’interface de la Console développeur. Ce jeton d’accès devra être utilisé dans chaque en-tête de vos requêtes d’API.

Pour établir une session d’API Adobe I/O de service à service sécurisée, chaque requête adressée à un service Adobe doit inclure les informations ci-dessous dans l’en-tête d’autorisation.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZATION>** : il s’agit de votre ORGANIZATION ID personnel, fourni par Adobe pour chacune de vos instances :

   * &lt;ORGANIZATION> : votre instance de production
   Pour obtenir votre valeur ORGANIZATION ID, contactez votre administrateur ou votre contact technique Adobe. Vous pouvez également la récupérer dans Adobe I/O lors de la création d’une nouvelle intégration, dans la liste des licences (voir la <a href="https://www.adobe.io/authentication.html">documentation Adobe IO</a>).

* **&lt;ACCESS_TOKEN>**: Votre jeton d&#39;accès personnel, qui a été récupéré lors de l’échange de votre JWT par le biais d’une demande POST.

* **&lt;API_KEY>** : votre clé d’API personnelle. It is provided in Adobe I/O after creating a new integration to [!DNL Journey Orchestration] Service.



## Description de l’API de plafonnement

L’API de plafonnement vous aide à créer, configurer et contrôler vos configurations de plafonnement.

| Méthodologie | Chemin | Description |
|---|---|---|
| POST | liste/endpointConfigs | Obtenir une liste des configurations de plafonnement des points de terminaison |
| POST | /endpointConfigs | Création d’une configuration de plafonnement des points de terminaison |
| POST | /endpointConfigs/{uid}/deploy | Déploiement d’une configuration de plafonnement des points de terminaison |
| POST | /endpointConfigs/{uid}/undeploy | Annulation du déploiement d’une configuration de plafonnement de point de terminaison |
| POST | /endpointConfigs/{uid}/canDeploy | Vérifier si une configuration de plafonnement de point de terminaison peut être déployée ou non |
| PUT | /endpointConfigs/{uid} | Mise à jour de la configuration de plafonnement des points de terminaison |
| GET | /endpointConfigs/{uid} | Récupération d’une configuration de plafonnement des points de terminaison |
| SUPPRIMER | /endpointConfigs/{uid} | Suppression d’une configuration de recouvrement d’un point de terminaison |

Lorsqu’une configuration est créée ou mise à jour, une vérification est automatiquement effectuée pour garantir la syntaxe et l’intégrité de la charge utile.
Si certains problèmes se produisent, l’opération renvoie un avertissement ou des erreurs pour vous aider à corriger la configuration.



## Configuration du point de terminaison

Voici la structure de base d’une configuration de point de terminaison :

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

### Exemple:

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

Lorsqu’une méthode **canDeploy** est appelée, le processus valide la configuration et renvoie l’état de validation identifié par son identifiant unique, soit :

```
"ok" or "error"
```

Les erreurs potentielles sont les suivantes :

* **ERR_ENDPOINTCONFIG_100**: capping config : URL manquante ou non valide
* **ERR_ENDPOINTCONFIG_101**: capping config : URL mal formée
* **ERR_ENDPOINTCONFIG_102**: capping config : URL mal formée : wildchar dans l&#39;url non autorisé dans host:port
* **ERR_ENDPOINTCONFIG_103**: capping config : méthodes HTTP manquantes
* **ERR_ENDPOINTCONFIG_104**: capping config : aucune note d&#39;appel définie
* **ERR_ENDPOINTCONFIG_107**: capping config : nombre d&#39;appels max non valide (maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**: capping config : nombre d&#39;appels max non valide (periodInMs)
* **ERR_ENDPOINTCONFIG_111**: capping config : impossible de créer la configuration du point de terminaison : charge utile non valide
* **ERR_ENDPOINTCONFIG_112**: capping config : impossible de créer la configuration du point de terminaison : attente d’une charge utile JSON
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: nom de service non valide <!--<given value>-->: doit être &quot;dataSource&quot; ou &quot;action&quot;


L&#39;avertissement potentiel est :

**ERR_ENDPOINTCONFIG_106**: capping config : connexions HTTP max non définies : aucune limitation par défaut



## Cas d’utilisation

Dans cette section, vous trouverez les cinq principaux cas d&#39;utilisation que vous pouvez effectuer pour gérer votre configuration de plafonnement dans [!DNL Journey Orchestration].

Pour vous aider dans vos tests et votre configuration, une collection Postman est disponible [ici](https://github.com/AdobeDocs/JourneyAPI/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

Cette collection Postman a été créée pour partager la collection de variables Postman générée via Intégrations __[de la Console d&#39;E/S d&#39;](https://console.adobe.io/integrations)Adobe > Essayez-la > Télécharger pour Postman__, qui génère un fichier d&#39;Environnement Postman avec les valeurs d&#39;intégration sélectionnées.

Une fois téléchargé et téléchargé dans Postman, vous devez ajouter deux variables : `{JO_HOST}` et `{Base_Path}`.
* `{JO_HOST}` : [!DNL Journey Orchestration] URL de passerelle
* `{BASE_PATH}` : point d’entrée pour l’API. La valeur est &quot;/authoring&quot;



Cas d’utilisation n°1 : **Création et déploiement d&#39;une nouvelle configuration de plafonnement**

1. liste
1. créer
1. candeploy
1. déployer

Cas d&#39;utilisation n°2 : **Mise à jour et déploiement d’une configuration de plafonnement non encore déployée**

1. liste
1. get
1. update
1. candeploy
1. déployer

Cas d&#39;utilisation n°3 : **Annulation du déploiement et suppression d’une configuration de mise en cache déployée**

1. liste
1. annuler
1. delete

Cas d&#39;utilisation n°4 : **Supprimez une configuration de plafonnement déployée.**

Dans un seul appel d&#39;API, vous pouvez annuler le déploiement et supprimer la configuration à l&#39;aide du paramètre forceDelete.
1. liste
1. delete, avec le paramètre forceDelete

Cas d&#39;utilisation n°5 : **Mise à jour d’une configuration de mise en cache déjà déployée**

1. liste
1. get
1. update
1. annuler
1. candeploy
1. déployer

