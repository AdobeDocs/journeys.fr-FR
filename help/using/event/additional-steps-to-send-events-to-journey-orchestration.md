---
title: Étapes supplémentaires pour l’envoi d’événements à Journey Orchestration
description: En savoir plus sur les étapes supplémentaires pour l’envoi d’événements à Journey Orchestration
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: ht
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---



# Étapes supplémentaires pour l’envoi d’événements à Journey Orchestration {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>Lors de la création d’un événement, Journey Orchestration génère automatiquement un identifiant qui lui correspond. Le système à l’origine de l’envoi de l’événement ne doit pas générer d’identifiant, mais plutôt utiliser celui indiqué dans l’aperçu de la payload. Voir [](../event/previewing-the-payload.md).

Pour configurer les événements qui doivent être envoyés aux **[!UICONTROL API d’ingestion de diffusion]** et utilisés dans Journey Orchestration, procédez comme suit :

1. Récupérez l’URL d’entrée à partir des API de Data Platform (voir [API d’ingestion de diffusion](https://www.adobe.io/apis/cloudplatform/dataservices/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/getting_started_with_platform_streaming_ingestion.md)).
1. Copiez la payload depuis son aperçu dans le menu **[!UICONTROL Événement]**. Voir [](../event/defining-the-payload-fields.md).

Vous devez ensuite configurer le système de données qui envoie les événements vers les API d’ingestion de diffusion à l’aide de la payload que vous avez copiée :

1. Configurez un appel d’API POST à l’URL des API d’ingestion de diffusion (désignée sous le nom d’entrée).
1. Utilisez la payload que vous avez copiée dans Journey Orchestration dans le corps (« section de données ») de l’appel d’API vers les API d’ingestion de diffusion. Reportez-vous à l’exemple ci-dessous.
1. Déterminez où obtenir toutes les variables présentes dans la payload. Exemple : si l’événement est censé transmettre l’adresse, la payload collée indique &quot;address&quot;: &quot;string&quot;. &quot;string&quot; doit être remplacé par la variable qui renseigne automatiquement la valeur appropriée, c’est-à-dire l’adresse email du destinataire du message. Notez que dans la section **[!UICONTROL Header]** de l’aperçu de la payload, de nombreuses valeurs sont renseignées automatiquement afin de vous faciliter la tâche.
1. Sélectionnez &quot;application/json&quot; comme type de corps.
1. Transmettez votre identifiant d’organisation IMS dans l’en-tête à l’aide de la clé &quot;x-gw-ims-org-id&quot;. Pour cette valeur, utilisez votre identifiant d’organisation IMS (&quot;XXX@AdobeOrg&quot;).

Voici un exemple d’événement d’API d’ingestion de diffusion :

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

Pour identifier plus facilement l’endroit où coller la partie « données », vous pouvez utiliser un outil de visualisation JSON tel que [https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com).

Pour résoudre les problèmes liés aux API d’ingestion de diffusion, consultez cette [page](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingestion_FAQ.md).
