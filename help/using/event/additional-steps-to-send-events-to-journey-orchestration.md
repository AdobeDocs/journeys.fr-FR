---
title: Autres étapes pour envoyer des événements à l’orchestration Journey
description: En savoir plus sur les étapes supplémentaires pour envoyer des événements à l'orchestration Journey
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---



# Autres étapes pour envoyer des événements à l’orchestration Journey {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>Lors de la création d’un événement, l’orchestration du voyage génère automatiquement un identifiant pour cet événement. Le système poussant l’événement ne doit pas générer d’identifiant, il doit utiliser celui disponible dans l’aperçu de la charge utile. Voir la section [](../event/previewing-the-payload.md).

Pour configurer les événements à envoyer aux API **[!UICONTROL d’envoi en]**flux continu et à utiliser dans l’orchestration du parcours, procédez comme suit :

1. Récupérez l’URL d’entrée à partir des API de plateforme de données (voir API [d’administration de](https://www.adobe.io/apis/cloudplatform/dataservices/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/getting_started_with_platform_streaming_ingestion.md)diffusion en continu).
1. Copiez la charge dans l’aperçu de la charge dans le menu **[!UICONTROL Evénement]**. Voir la section[](../event/defining-the-payload-fields.md).

Vous devez ensuite configurer le système de données qui transfère les événements vers les API d’importation en flux continu à l’aide de la charge utile que vous avez copiée :

1. Configurez un appel d’API POST vers l’URL des API d’importation en flux continu (appelée entrée).
1. Utilisez la charge utile que vous avez copiée de l’orchestration de voyage dans le corps (&quot;section de données&quot;) de l’appel d’API aux API d’importation en flux continu. Voir ci-dessous un exemple
1. Déterminez où obtenir toutes les variables présentes dans la charge utile. Exemple : si l’événement est censé transmettre l’adresse, la charge utile collée indiquera &quot;adresse&quot; : &quot;string&quot;. &quot;string&quot; doit être remplacé par la variable qui renseigne automatiquement la valeur appropriée, c’est-à-dire le courrier électronique de la personne à qui envoyer un message. Notez que dans l’aperçu de la charge utile, dans la section **[!UICONTROL En-tête]**, nous renseignons automatiquement de nombreuses valeurs censées faciliter votre travail.
1. Sélectionnez &quot;application/json&quot; comme type de corps.
1. Transmettez votre ID IMS ORG dans l&#39;en-tête à l&#39;aide de la clé &quot;x-gw-ims-org-id&quot;. Pour cette valeur, utilisez votre ID IMS ORG (&quot;XXX@AdobeOrg&quot;).

Voici un exemple d’événement d’API de gestion en flux continu :

```
{
    "header": {
        "msgType": "xdmEntityCreate",
        "msgId": "c25585b9-252e-431d-b562-e73da70c04e7",
        "msgVersion": "1.0",
        "xactionId": "f5995abe-c49d-4848-9577-a7a4fc2996fb",
        "datasetId": "string - required if you want the data to land in a specific dataset - not mandatory",
        "imsOrgId": "XXX@AdobeOrg",
        "schemaRef": {
            "id": "XXX",
            "contentType": "application/vnd.adobe.xed-full+json;version=1"
        },
        "source": {
            "name": "Journeys"
        }
    },
    "body": {
        "xdmMeta": {
            "schemaRef": {
                "id": "XXX",
                "contentType": "application/vnd.adobe.xed-full+json;version=1"
            }
        },
        "xdmEntity": {
            "_instance_name": {
                "person": {
                    "firstName": "string",
                    "lastName": "string",
                    "gender": "string",
                    "birthYear": 10,
                    "emailAddress": "string"
                }
            },
            "identityMap": {
                "Email": [
                {
                    "id": "string"
                    }
                ]
            },
            "_id": "string",
            "timestamp": "2018-05-29T00:00:00.000Z",
            "_experience": {
                "campaign": {
                    "orchestration": {
                    "eventID": "XXX"
                    }
                }
            }
        }
    }
}
```

Pour faciliter l’identification du lieu où coller la partie &quot;données&quot;, vous pouvez utiliser un outil de visualisation JSON tel que [https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)

Pour résoudre les problèmes liés aux API d&#39;importation en flux continu, reportez-vous à cette [page](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingestion_FAQ.md).
