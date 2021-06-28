---
product: adobe campaign
title: Utilisation d’Adobe Campaign
description: En savoir plus sur les actions Adobe Campaign
feature: Parcours
role: Business Practitioner
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
source-git-commit: c17808a4cae7ebbd1129f6b28ad2ea945098f826
workflow-type: ht
source-wordcount: '314'
ht-degree: 100%

---

# Utilisation d’Adobe Campaign Standard {#using_adobe_campaign_standard}

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
