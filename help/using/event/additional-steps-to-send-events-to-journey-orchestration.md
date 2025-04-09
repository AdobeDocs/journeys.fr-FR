---
product: adobe campaign
title: Étapes supplémentaires pour l’envoi d’événements à Journey Orchestration
description: En savoir plus sur les étapes supplémentaires pour l’envoi d’événements à Journey Orchestration
feature: Journeys
role: User
level: Intermediate
exl-id: 11e337c6-5e05-4898-9953-b6b821af8fd1
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 87%

---

# Étapes supplémentaires pour l’envoi d’événements à [!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}



>[!CAUTION]
>
>**Vous recherchez Adobe Journey Optimizer** ? Cliquez [ici](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/ajo-home){target="_blank"} pour accéder à la documentation de Journey Optimizer.
>
>
>_Cette documentation fait référence aux matériaux de Journey Orchestration hérités qui ont été remplacés par Journey Optimizer. Veuillez contacter votre équipe de compte si vous avez des questions concernant votre accès à Journey Orchestration ou à Journey Optimizer._


>[!NOTE]
>
>Lors de la création d’un événement, [!DNL Journey Orchestration] génère automatiquement un identifiant qui lui correspond. Le système à l&#39;origine de l&#39;envoi de l&#39;événement ne doit pas générer d&#39;identifiant, mais plutôt utiliser celui indiqué dans l&#39;aperçu de la payload. Voir [cette page](../event/previewing-the-payload.md).

Pour configurer les événements qui doivent être envoyés aux **[!UICONTROL API d’ingestion en flux continu]** et utilisés dans [!DNL Journey Orchestration], procédez comme suit :

1. Récupérez l’URL d’inlet à partir des API d’Adobe Experience Platform (voir [API d’ingestion en flux continu](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=fr)).
1. Copiez la payload depuis son aperçu dans le menu **[!UICONTROL Événement]**. Voir [cette page](../event/defining-the-payload-fields.md).

Vous devez ensuite configurer le système de données qui envoie les événements vers les API d’ingestion en flux continu à l’aide de la payload que vous avez copiée :

1. Configurez un appel d’API POST à l’URL des API d’ingestion en flux continu (désignée sous le nom « inlet »).
1. Utilisez la payload que vous avez copiée depuis [!DNL Journey Orchestration], dans le corps (« section de données ») de l’appel d’API, vers les API d’ingestion en flux continu. Reportez-vous à l’exemple ci-dessous.
1. Déterminez où obtenir toutes les variables présentes dans la payload. Exemple : si l’événement est censé transmettre l’adresse, la payload collée indique &quot;address&quot;: &quot;string&quot;. &quot;string&quot; doit être remplacé par la variable qui renseigne automatiquement la valeur appropriée, c’est-à-dire l’adresse e-mail du destinataire du message. Notez que dans la section **[!UICONTROL En-tête]** de l’aperçu de la payload, de nombreuses valeurs sont renseignées automatiquement afin de vous faciliter la tâche.
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

Pour résoudre les problèmes liés aux API d’ingestion en flux continu, consultez cette [page](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html?lang=fr).
