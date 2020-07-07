---
title: Utilisation d’Adobe Campaign
description: En savoir plus sur les actions Adobe Campaign
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
source-git-commit: 6685565797a6cdc43b9c8fc39c9354ae6d213f1f
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 39%

---


# Utilisation d’Adobe Campaign {#using_adobe_campaign_standard}

Vous pouvez envoyer des emails, des notifications push et des SMS à l’aide des fonctionnalités de messagerie transactionnelle d’Adobe Campaign Standard.

[!DNL Journey Orchestration] est fourni avec une action d’usine qui permet de se connecter à Adobe Campaign Standard.

Le message transactionnel Campaign Standard et son événement associé doivent être publiés pour être utilisés en Journey Orchestration. Si le événement est publié mais que le message ne l’est pas, il ne sera pas visible dans l’interface du Journey Orchestration. Si le message est publié mais que son événement associé ne l’est pas, il sera visible dans l’interface du Journey Orchestration, mais il ne sera pas utilisable.

>[!NOTE]
>
>Pour éviter de surcharger les messages transactionnels d’Adobe Campaign Standard, il est recommandé de configurer une règle **de** plafonnement pour l’intégration du Campaign Standard.
>
>Pour en savoir plus sur les contrats SLA de messagerie transactionnelle, consultez la description [du produit](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)Adobe Campaign Standard.

La procédure de configuration est la suivante :

1. Dans la liste **[!UICONTROL Actions]**, cliquez sur l’action **[!UICONTROL AdobeCampaignStandard]** intégrée. Le volet de configuration des actions s’ouvre dans la partie droite de l’écran.

   ![](../assets/actioncampaign.png)

1. Copiez l’URL de votre instance Adobe Campaign Standard et collez-la dans le champ **[!UICONTROL URL]**.

1. Cliquez sur **[!UICONTROL Tester l’URL d’instance]** pour tester la validité de l’instance.

   >[!NOTE]
   >
   >Ce test vérifie que :
   >
   >* L’hôte est &quot;.campaign.adobe.com&quot; ou &quot;.campaign-sandbox.adobe.com&quot;,
   >* L&#39;URL début avec https,
   >* L&#39;ORG associé à cette instance d&#39;Adobe Campaign Standard est identique à l&#39;ORG du Journey Orchestration.


When designing your journey, three actions will be available in the **[!UICONTROL Action]** category: **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (see [Using Adobe Campaign actions](../building-journeys/using-adobe-campaign-actions.md)). **Le événement** Réactions vous permet également de réagir sur les clics sur les messages, les ouvertures, etc. (voir événements [](../building-journeys/event-activities.md#section_dhx_gss_dgb)de réactions).

![](../assets/journey58.png)

Si vous utilisez un système tiers pour l’envoi de messages, vous devez ajouter et configurer une action personnalisée. See [About custom action configuration](../action/about-custom-action-configuration.md).
