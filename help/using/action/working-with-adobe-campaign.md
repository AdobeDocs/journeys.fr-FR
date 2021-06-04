---
product: adobe campaign
title: Utilisation d’Adobe Campaign
description: En savoir plus sur les actions Adobe Campaign
feature: Parcours
role: Business Practitioner
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
source-git-commit: c49908d36ecbc68ae11b5621305f39dd59c67871
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 74%

---

# Utilisation d’Adobe Campaign {#using_adobe_campaign}

## Utilisation d’Adobe Campaign Standard {#using_adobe_campaign_standard}

Vous pouvez envoyer des e-mails, des notifications push et des SMS à l’aide des fonctionnalités de messagerie transactionnelle d’Adobe Campaign Standard.

[!DNL Journey Orchestration] est fourni avec une action d’usine qui permet de se connecter à Adobe Campaign Standard.

Le message transactionnel Campaign Standard et son événement associé doivent être publiés pour être utilisés dans Journey Orchestration. Si l’événement est publié mais que le message ne l’est pas, il ne sera pas visible dans l’interface de Journey Orchestration. Si le message est publié mais que son événement associé ne l’est pas, il sera visible dans l’interface de Journey Orchestration, mais il ne sera pas utilisable.

>[!NOTE]
>
>Une règle de limitation de 13 appels par seconde est automatiquement définie pour les actions Adobe Campaign Standard dès que l’intégration Adobe Campaign Standard est configurée. Cela correspond à l’échelle officielle des messages transactionnels d’Adobe Campaign Standard.
>
>Pour en savoir plus sur les SLA de messagerie transactionnelle, consultez la [description du produit Adobe Campaign Standard](https://helpx.adobe.com/fr/legal/product-descriptions/campaign-standard.html).

La procédure de configuration est la suivante :

1. Dans la liste **[!UICONTROL Actions]**, cliquez sur l’action **[!UICONTROL AdobeCampaignStandard]** intégrée. Le volet de configuration des actions s’ouvre dans la partie droite de l’écran.

   ![](../assets/actioncampaign.png)

1. Copiez l’URL de votre instance Adobe Campaign Standard et collez-la dans le champ **[!UICONTROL URL]**.

1. Cliquez sur **[!UICONTROL Tester l’URL d’instance]** pour tester la validité de l’instance.

   >[!NOTE]
   >
   >Ce test vérifie que les conditions suivantes sont remplies :
   >
   >L’hôte est « .campaign.adobe.com », « .campaign-sandbox.adobe.com », « .campaign-demo.adobe.com », « .ats.adobe.com » ou « .adls.adobe.com ».
   >
   >L’URL commence par https.
   >
   >L’organisation associée à cette instance d’Adobe Campaign Standard est identique à l’organisation de Journey Orchestration.

Lors de la conception de votre parcours, trois actions sont disponibles dans la catégorie **[!UICONTROL Action]** : **[!UICONTROL E-mail]**, **[!UICONTROL Push]** et **[!UICONTROL SMS]** (voir [Utilisation d’actions Adobe Campaign](../building-journeys/using-adobe-campaign-actions.md)). L’**événement Réactions** vous permet également de réagir sur les clics, les ouvertures des messages, etc. (Voir [Événements Réactions](../building-journeys/reaction-events.md)).

![](../assets/journey58.png)

Si vous utilisez un système tiers pour l’envoi de messages, vous devez ajouter et configurer une action personnalisée. Voir [À propos de la configuration d’actions personnalisées](../action/about-custom-action-configuration.md).

## Utilisation d’Adobe Campaign v7/v8 {#using_adobe_campaign_v7_v8}

Cette intégration est disponible pour Adobe Campaign Classic v7 à partir de la version 21.1 et Adobe Campaign v8. Il vous permet d’envoyer des emails, des notifications push et des SMS à l’aide des fonctionnalités de messagerie transactionnelle Adobe Campaign.

La connexion entre les instances Journey Orchestration et Campaign est configurée par Adobe au moment de l’approvisionnement.

Un cas pratique de bout en bout est présenté dans cette [section](../usecase/campaign-v7-v8-use-case.md).

Pour chaque action configurée, une activité d’action est disponible dans la palette du concepteur de parcours. Reportez-vous à cette [section](../building-journeys/using-adobe-campaign-actions.md).

### Remarques importantes

* Il n’y a pas de limitation des messages. Nous limitons le nombre de messages pouvant être envoyés à 50 000/heure en nous basant sur le contrat de niveau de service Campaign actuel. C’est la raison pour laquelle Journey Orchestration ne devrait être utilisé que dans des cas d’utilisation unitaire (des événements individuels, et non des segments).

* Vous devez configurer une action sur la zone de travail pour chaque modèle à utiliser. Vous devez configurer une action dans Journey Orchestration pour chaque modèle que vous souhaitez utiliser à partir d’Adobe Campaign.

* Nous vous recommandons d’utiliser une instance Message Center dédiée et hébergée pour cette intégration afin d’éviter d’impacter les autres opérations de Campaign en cours. Le serveur marketing peut être hébergé ou On-Premise. La version requise est 21.1 ou supérieure.

* Il n’existe aucune validation indiquant le caractère correct du message Campaign ou de la payload.

* Vous ne pouvez pas utiliser une action Campaign avec un événement de qualification de segment.

### Conditions préalables requises

Dans Campaign, vous devez créer et publier un message transactionnel et son événement associé. Reportez-vous à la [documentation d’Adobe Campaign ](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html?lang=fr#transactional-messaging).

Vous pouvez créer la charge utile JSON correspondant à chaque message selon le modèle ci-dessous. Il vous faudra ensuite coller cette payload lors de la configuration de l’action dans Journey Orchestration (voir ci-dessous)

Voici un exemple :

```
{
    "channel": "email",
    "eventType": "welcome",
    "email": "example@adobe.com",
    "ctx": {
        "firstName": "John"
    }
}
```

* **channel** : le canal défini pour votre modèle transactionnel Campaign
* **eventType** : le nom interne de votre événement Campaign
* **ctx** : en fonction de la personnalisation de votre message.

### Configuration de l’action

Dans Journey Orchestration, vous devez configurer une action par message transactionnel. Procédez comme suit :

1. Créez une nouvelle action. Reportez-vous à cette [section](../action/action.md).
1. Entrez un nom et une description.
1. Dans le champ **Type d’action**, sélectionnez **Adobe Campaign Classic**.
1. Cliquez dans le champ **Payload** et collez un exemple de payload JSON correspondant au message Campaign Contactez Adobe pour obtenir cette payload.
1. Ajustez les différents champs de sorte qu’ils soient statiques ou variables selon que vous souhaitez les mapper sur la zone de travail du Parcours. Certains champs, tels que les paramètres de canal pour l’adresse email et les champs de personnalisation (ctx), doivent probablement être définis comme des variables pour le mappage dans le contexte du parcours.
1. Cliquez sur **Enregistrer**.

![](../assets/accintegration1.png)


