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
translation-type: tm+mt
source-git-commit: e353d593ab2710f50a88a3715378c86c2e37b4f6
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 100%

---



# Étapes supplémentaires pour l’envoi d’événements à [!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>Lors de la création d’un événement, [!DNL Journey Orchestration] génère automatiquement un identifiant qui lui correspond. Le système à l’origine de l’envoi de l’événement ne doit pas générer d’identifiant, mais plutôt utiliser celui indiqué dans l’aperçu de la payload. Voir [cette page](../event/previewing-the-payload.md).

Pour configurer les événements qui doivent être envoyés aux **[!UICONTROL API d’ingestion en flux continu]** et utilisés dans [!DNL Journey Orchestration], procédez comme suit :

1. Récupérez l’URL d’inlet à partir des API d’Adobe Experience Platform (voir [API d’ingestion en flux continu](https://docs.adobe.com/content/help/fr-FR/experience-platform/ingestion/streaming/overview.html)).
1. Copiez la payload depuis son aperçu dans le menu **[!UICONTROL Événement]**. Voir [cette page](../event/defining-the-payload-fields.md).

Vous devez ensuite configurer le système de données qui envoie les événements vers les API d’ingestion en flux continu à l’aide de la payload que vous avez copiée :

1. Configurez un appel d’API POST à l’URL des API d’ingestion en flux continu (désignée sous le nom « inlet »).
1. Utilisez la payload que vous avez copiée depuis [!DNL Journey Orchestration], dans le corps (« section de données ») de l’appel d’API, vers les API d’ingestion en flux continu. Reportez-vous à l’exemple ci-dessous.
1. Déterminez où obtenir toutes les variables présentes dans la payload. Exemple : si l’événement est censé transmettre l’adresse, la payload collée indique &quot;address&quot;: &quot;string&quot;. &quot;string&quot; doit être remplacé par la variable qui renseigne automatiquement la valeur appropriée, c’est-à-dire l’adresse email du destinataire du message. Notez que dans la section **[!UICONTROL Header]** de l’aperçu de la payload, de nombreuses valeurs sont renseignées automatiquement afin de vous faciliter la tâche.
1. Sélectionnez &quot;application/json&quot; comme type de corps.
1. Transmettez votre identifiant d’organisation IMS dans l’en-tête à l’aide de la clé « x-gw-ims-org-id ». Pour cette valeur, utilisez votre identifiant d’organisation IMS (« XXX@AdobeOrg »).

Voici un exemple d’événement d’API d’ingestion en flux continu :

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

Pour résoudre les problèmes liés aux API d’ingestion en flux continu, consultez cette [page](https://docs.adobe.com/content/help/fr-FR/experience-platform/ingestion/streaming/troubleshooting.html).
