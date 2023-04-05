---
product: adobe campaign
title: Utilisation de l’API de limitation
description: En savoir plus sur l’API de limitation
products: journeys
feature: Journeys
role: User
level: Intermediate
source-git-commit: fa493cf1e856378e4d79a6932c30cebf5e11e028
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 21%

---

# Utilisation de l’API de limitation

L’API de limitation vous aide à créer, configurer et surveiller vos configurations de limitation.

>[!IMPORTANT]
>
>Actuellement, une seule configuration est autorisée par organisation. Une configuration doit être définie sur un environnement de test de production (fourni par x-sandbox-name dans les en-têtes).
>
>Une configuration est appliquée au niveau de l’organisation.
>
>Lorsque la limite définie dans l’API est atteinte, d’autres événements sont placés en file d’attente pendant 6 heures au maximum. Cette valeur ne peut pas être modifiée.

## Description de l’API de limitation {#description}

| Méthode | Chemin | Description |
|---|---|---|
| [!DNL POST] | list/throttlingConfigs | Obtention d’une liste des configurations de ralentissement |
| [!DNL POST] | /throttlingConfigs | Création d’une configuration de ralentissement |
| [!DNL POST] | /throttlingConfigs/`{uid}`/deploy | Déploiement d’une configuration de limitation |
| [!DNL POST] | /throttlingConfigs/`{uid}`/undeploy | Annulation du déploiement d’une configuration de ralentissement |
| [!DNL POST] | /throttlingConfigs/`{uid}`/canDeploy | Vérifiez si une configuration de limitation peut être déployée ou non. |
| [!DNL PUT] | /throttlingConfigs/`{uid}` | Mise à jour d’une configuration de ralentissement |
| [!DNL GET] | /throttlingConfigs/`{uid}` | Récupération d’une configuration de ralentissement |
| [!DNL DELETE] | /throttlingConfigs/`{uid}` | Suppression d’une configuration de ralentissement |

## Configuration du ralentissement {#configuration}

Voici la structure d’une configuration de limitation. **name** et **description** Les attributs sont facultatifs.

```
{
    "name": "<given name - free text>",
    "description": "<given description - free text>"
    "urlPattern": "<endpoint URL - wildcards are allowed>",
    "methods": [ "<HTTP method such as GET, POST, PUT>" ],
    "maxThroughput": <max call throughput>
}
```

Exemple :

```
{
  "name": "throttling-config-external",
  "description": "example of throttling config for an external endpoint",
  "urlPattern": "https://api.example.org/data/2.5/*",
  "methods": ["POST", "PUT"],
  "maxThroughput": 4000
}
```

## Erreurs

Lors de la création ou de la mise à jour d’une configuration, le processus valide la configuration donnée et renvoie l’état de validation identifié par son identifiant unique, au choix :

```
"ok" or "error"
```

>[!IMPORTANT]
>
>Attributs **maxThroughput**, **urlPattern** et **methods** sont obligatoires.
>
>**maxThroughput** doit être comprise entre 200 et 5 000.

Lors de la création, de la suppression ou du déploiement d’une configuration de limitation, les erreurs suivantes peuvent se produire :

* **ERR_THROTTLING_CONFIG_100**: configuration de ralentissement : `<mandatory attribute>` required
* **ERR_THROTTLING_CONFIG_101**: configuration de ralentissement : maxThroughput est requis et doit être supérieur ou égal à 200 et inférieur ou égal à 5 000
* **ERR_THROTTLING_CONFIG_104**: configuration de ralentissement : modèle d’URL mal formé
* **ERR_THROTTLING_CONFIG_105**: configuration de ralentissement : caractères génériques non autorisés dans la partie hôte du modèle d’URL
* **ERR_THROTTLING_CONFIG_106**: configuration de ralentissement : payload non valide
* **THROTTLING_CONFIG_DELETE_FORBIDDEN_ERROR : 1456**, &quot;Impossible de supprimer une configuration de limitation déployée. Annuler le déploiement avant de le supprimer&quot;
* **THROTLING_CONFIG_DELETE_ERROR : 1457**, &quot;Impossible de supprimer la configuration de ralentissement : &quot;erreur inattendue&quot;
* **THROTLING_CONFIG_DEPLOY_ERROR : 1458**, &quot;Impossible de déployer la configuration de ralentissement : &quot;erreur inattendue&quot;
* **THROTLING_CONFIG_UNDEPLOY_ERROR : 1459**, &quot;Impossible d’annuler le déploiement de la configuration de ralentissement : &quot;erreur inattendue&quot;
* **THROTTLING_CONFIG_GET_ERROR : 1460**, &quot;Impossible d’obtenir la configuration de ralentissement : &quot;erreur inattendue&quot;
* **THROTTLING_CONFIG_UPDATE_NOT_PRINCIPAL_ERROR : 1461**, &quot;Impossible de mettre à jour la configuration de ralentissement : la version du runtime n’est pas principale&quot;
* **THROTTLING_CONFIG_UPDATE_ERROR : 1462**, &quot;Impossible de mettre à jour la configuration de ralentissement : &quot;erreur inattendue&quot;
* **THROTTLING_CONFIG_NON_PROD_SANDBOX_ERROR : 1463**, &quot;Opération non autorisée dans la configuration de ralentissement : non prod sandbox&quot;
* **THROTTLING_CONFIG_CREATE_ERROR : 1464**, &quot;Impossible de créer une configuration de ralentissement : &quot;erreur inattendue&quot;
* **THROTTLING_CONFIG_CREATE_LIMIT_ERROR : 1465**, &quot;Impossible de créer une configuration de ralentissement : une seule configuration autorisée par organisation&quot;
* **THROTTLING_CONFIG_ALREADY_DEPLOYED_ERROR : 14466**, &quot;Impossible de déployer la configuration de ralentissement : déjà déployé&quot;
* **THROTTLING_CONFIG_NOT_FOUND_ERROR : 14467**, &quot;configuration de ralentissement introuvable&quot;
* **THROTTLING_CONFIG_NOT_DEPLOYED_ERROR : 14468**, &quot;Impossible d’annuler le déploiement de la configuration de ralentissement : non encore déployé&quot;

**Exemples d’erreurs**

Lors de la création d’une configuration sur un environnement de test non prod :

```
{
    "status": 400,
    "error": "{\"code\":1463,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Operation not allowed on throttling config: non prod sandbox\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:384\",\"schema\":\"throttlingConfigs$ui-tests\"}",
    "requestId": "5sgnAYXs8mpswwjAFEIaAU2faQYbtyHc"
}
```

Au cas où la sandbox donnée n’existe pas :

```
{
    "status": 500,
    "error": "{\"code\":4000,\"family\":\"INTERNAL_ERROR\",\"message\":\"INTERNAL ERROR\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.common.exceptions.ApiErrorException:43\"}",
    "requestId": "04ZJ4e5ki4bYs3lfO17a7hovRGewjvdK"
}
```

Lors de la création d’une autre configuration :

```
{
    "status": 400,
    "error": "{\"code\":1465,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Can't create throttling config: only one config allowed per org\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:108\",\"schema\":\"throttlingConfigs$prod\"}",
    "requestId": "A7ezT8JhOQT4WIAf1Fv7K2wCDA8281qM"
}
```

## Cas d’utilisation {#uc}

Pour vous aider dans les tests et la configuration, une collection Postman est disponible [ici](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Throttling-API_postman-collection.json).

Elle a été créée pour partager la collection de variables Postman générée par le biais des options __[Intégrations de la console Adobe I/O](https://console.adobe.io/integrations) > Essayez-la > Télécharger pour Postman__, qui génère un fichier d’environnement Postman contenant les valeurs d’intégration sélectionnées.

Une fois le téléchargement puis le chargement effectués dans Postman, vous devez ajouter trois variables : `{JO_HOST}`, `{BASE_PATH}` et `{SANDBOX_NAME}`.
* `{JO_HOST}` : URL de passerelle [!DNL Journey Orchestration]
* `{BASE_PATH}` : point d’entrée pour l’API. La valeur est &#39;/authoring&#39;
* `{SANDBOX_NAME}` : l’en-tête **x-sandbox-name** (par exemple, « prod ») correspondant au nom sandbox dans lequel les opérations d’API auront lieu. Pour plus d’informations, consultez la [Présentation des sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=fr).

Dans la section suivante, vous trouverez la liste classée des appels API REST pour effectuer le cas d’utilisation.

Cas d’utilisation n°1 : **Création et déploiement d’une nouvelle configuration de limitation**

1. list
1. create
1. candeploy
1. deploy

Cas d’utilisation n°2 : **Mise à jour et déploiement d’une configuration de limitation non encore déployée**

1. list
1. get
1. update
1. candeploy
1. deploy

Cas d’utilisation n°3 : **Annulation du déploiement et suppression d’une configuration de limitation déployée**

1. list
1. undeploy
1. delete

Cas d’utilisation n°4 : **Suppression d’une configuration de ralentissement déployée**

En un seul appel d’API, vous pouvez annuler le déploiement et supprimer la configuration à l’aide du paramètre forceDelete.

1. list
1. delete, avec le paramètre forceDelete

Cas d’utilisation n°5 : **Mise à jour d’une configuration de limitation déjà déployée**

>[!NOTE]
>
>Il n’est pas nécessaire d’annuler le déploiement de la configuration avant la mise à jour.

1. list
1. get
1. update

## Cycle de vie de la configuration au niveau de l’exécution {#config}

Lorsqu’une configuration n’est pas déployée, elle est marquée comme inactive au niveau de l’exécution et les événements en attente continuent à être traités pendant 24 heures. Il est ensuite supprimé dans le service d’exécution.

Une fois la configuration non déployée, il est possible de la mettre à jour et de la redéployer. Cela crée une nouvelle configuration d’exécution qui sera prise en compte dans l’exécution des actions à venir.

Lors de la mise à jour d’une configuration déjà déployée, les nouvelles valeurs sont prises en compte immédiatement. Les ressources système sous-jacentes sont automatiquement adaptées. Cette opération est optimale par rapport à l’annulation du déploiement, puis au redéploiement de la configuration.

## Exemples de réponses {#responses}

**Création - POST**

```
{
    "canDeploy": {
        "validationStatus": "ok"
    },
    "createdElement": {
        "name": "throttling-config-external",
        "description": "example of throttling config for an external endpoint",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "PUT",
            "POST"
        ],
        "maxThroughput": 4000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T10:48:16.099647Z"
        },
        "state": "created",
        "authoringFormatVersion": "1.0"
    },
    "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "uri": "/voyager/apis/throttlingConfigs/043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "resStatus": "created"
}
```

**Update - PUT**

```
{
    "updatedElement": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z"
        },
        "state": "updated",
        "authoringFormatVersion": "1.0",
        "hasBeenDeployed": false
    },
    "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "uri": "/voyager/apis/throttlingConfigs/043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "resStatus": "updated",
    "canDeploy": {
        "validationStatus": "ok"
    }
}
```

**Lecture (après mise à jour) - GET**

```
{
    "result": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z"
        },
        "state": "updated",
        "authoringFormatVersion": "1.0",
        "hasBeenDeployed": false
    }
}
```

**Lecture (après déploiement) - GET**

```
{
    "result": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "authoringFormatVersion": "1.0",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "version": "1.0",
        "state": "deployed",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z",
            "lastDeployedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastDeployedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastDeployedAt": "2023-03-22T11:46:07.532648Z"
        },
        "hasBeenDeployed": true
    }
}
```
