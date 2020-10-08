---
title: Utilisation d’actions Adobe Campaign
description: En savoir plus sur les actions Adobe Campaign
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 100%

---


# Utilisation d’actions Adobe Campaign {#using_campaign_action}

Si vous utilisez Adobe Campaign Standard, les activités d’action d’usine suivantes sont disponibles : **[!UICONTROL Email]**, **[!UICONTROL Push]** et **[!UICONTROL SMS]**.

>[!NOTE]
>
>Pour cela, vous devez configurer l’action intégrée. Voir [](../action/working-with-adobe-campaign.md).

Pour chacun de ces canaux, vous sélectionnez un **modèle** de message transactionnel Adobe Campaign Standard. En effet, [!DNL Journey Orchestration] n’est pas une solution d’envoi de messages. Pour les canaux Email, SMS et Push intégrés, l’envoi de messages est confié à la messagerie transactionnelle. Cela signifie que si vous souhaitez utiliser un modèle de message spécifique dans vos parcours, vous devez le publier dans Adobe Campaign Standard. Reportez-vous à cette [page](https://docs.adobe.com/content/help/fr-FR/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html) pour en savoir plus sur l’utilisation de cette fonctionnalité.

>[!NOTE]
>
>Le message transactionnel Campaign Standard et son événement associé doivent être publiés pour être utilisés dans Journey Orchestration. Si l’événement est publié mais que le message ne l’est pas, il ne sera pas visible dans l’interface de Journey Orchestration. Si le message est publié mais que son événement associé ne l’est pas, il sera visible dans l’interface de Journey Orchestration, mais il ne sera pas utilisable.

![](../assets/journey59.png)

Vous pouvez utiliser un modèle de message transactionnel basé sur un événement (appelé également en temps réel) ou sur un profil.

>[!NOTE]
>
>Lorsque nous envoyons des messages transactionnels en temps réel (rtEvent) ou acheminons des messages à l’aide d’un système tiers par le biais d’une action personnalisée, une configuration spécifique est requise pour la gestion de la fatigue, des listes bloquées ou des désabonnements. Par exemple, si un attribut « unsubscribe » est stocké dans Adobe Experience Platform ou dans un système tiers, une condition doit être ajoutée avant l’envoi du message pour vérifier cette condition.

Lorsque vous sélectionnez un modèle, tous les champs attendus dans la payload du message sont affichés dans le volet de configuration des activités sous **[!UICONTROL Adresse]** et **[!UICONTROL Données de personnalisation]**. Vous devez faire correspondre chacun de ces champs avec celui que vous souhaitez utiliser, et ce, depuis l’événement ou la source de données. Vous pouvez également utiliser l’éditeur d’expression avancé pour transmettre une valeur manuellement, effectuer une manipulation de données sur les informations récupérées (convertir une chaîne en majuscules, par exemple) ou utiliser des fonctions telles que « if, then, else ». Voir [](../expression/expressionadvanced.md).

![](../assets/journey60.png)

## Email et SMS {#section_asc_51g_nhb}

Les paramètres sont identiques pour **[!UICONTROL Email]** et **[!UICONTROL SMS]**.

>[!NOTE]
>
>Dans le cas des emails, si vous utilisez un modèle de transaction basé sur les profils, le mécanisme de désabonnement est géré, en standard, par Campaign Standard. Il vous suffit d’ajouter un bloc de contenu **[!UICONTROL Lien de désabonnement]** dans le modèle ([en savoir plus](https://docs.adobe.com/content/help/fr-FR/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)). Si vous utilisez un modèle basé sur des événements (rtEvent), vous devez ajouter, dans le message, un lien qui transmet l’email de la personne dans le paramètre d’URL et qui pointe vers une landing page de désabonnement. Vous devez créer cette landing page et vous assurer que la décision de désabonnement de la personne est bien transmise à Adobe.

Vous devez, tout d’abord, choisir un modèle de message transactionnel. Voir [](../building-journeys/about-action-activities.md).

Deux catégories sont disponibles : **[!UICONTROL Adresse]** et **[!UICONTROL Données de personnalisation]**.

Vous pouvez utiliser l’interface pour définir facilement l’emplacement de récupération de l’**[!UICONTROL adresse]** ou des **[!UICONTROL données de personnalisation]**. Vous pouvez parcourir les événements et les champs de la source de données disponible. Vous pouvez également utiliser l’éditeur d’expression avancé pour gérer des cas d’utilisation plus complexes, tels que l’utilisation d’une source de données nécessitant la transmission de paramètres ou l’exécution de manipulations. Voir [](../expression/expressionadvanced.md).

**[!UICONTROL Adresse]**

>[!NOTE]
>
>Cette catégorie n’est visible que si vous sélectionnez un message transactionnel basé sur un « événement ». Pour les messages basés sur un « profil », le système récupère automatiquement le champ **[!UICONTROL Adresse]** dans Adobe Campaign Standard.

Il s’agit des champs dont le système a besoin pour connaître la destination du message. Pour un modèle d’email, il s’agit de l’adresse email. Pour un SMS, il s’agit du numéro de téléphone mobile.

![](../assets/journey61.png)

**[!UICONTROL Données de personnalisation]**

>[!NOTE]
>
>Vous ne pouvez pas transmettre de collection dans les données de personnalisation. Si le SMS ou l’email transactionnel attend des collections, il ne fonctionnera pas. Notez également qu’un format spécifique est attendu pour les données de personnalisation (par exemple : chaîne, décimal, etc.). Vous devez veiller au respect de cette exigence.

Il s’agit des champs attendus par le message Adobe Campaign Standard. Ils peuvent être utilisés pour personnaliser le message, appliquer une mise en forme conditionnelle ou sélectionner une variante de message spécifique.

![](../assets/journey62.png)

## Push {#section_im3_hvf_nhb}

Avant d’utiliser l’activité Push, votre application mobile doit être configurée avec Campaign Standard afin d’envoyer des notifications de ce type. Consultez cet [article](https://helpx.adobe.com/fr/campaign/kb/integrate-mobile-sdk.html) pour effectuer les étapes de mise en œuvre nécessaires pour les appareils mobiles.

Vous devez, tout d’abord, choisir une application mobile dans la liste déroulante, ainsi qu’un message transactionnel. Voir [](../building-journeys/about-action-activities.md).

![](../assets/journey62bis.png)

Deux catégories sont disponibles : **[!UICONTROL Cible]** et **[!UICONTROL Données de personnalisation]**.

**[!UICONTROL Cible]**

>[!NOTE]
>
>Cette catégorie n’est visible que si vous sélectionnez un message basé sur événement. Pour les messages basés sur un profil, les champs **[!UICONTROL Cible]** sont automatiquement récupérés par le système à l’aide de la réconciliation effectuée par Adobe Campaign Standard.

Dans cette section, vous devez définir la **[!UICONTROL plateforme push]**. La liste déroulante vous permet de sélectionner **[!UICONTROL Apple Push Notification Server]** (iOS) ou **[!UICONTROL Firebase Cloud Messaging]** (Android). Vous avez aussi la possibilité de sélectionner un champ spécifique à partir d’un événement ou d’une source de données, ou de définir une expression avancée.

Vous devez également définir le **[!UICONTROL jeton d’enregistrement]**. L’expression dépend de la manière dont le jeton est défini dans la payload de l’événement ou dans d’autres informations de [!DNL Journey Orchestration]. Il peut s’agir d’un champ simple ou d’une expression plus complexe au cas où le jeton serait défini dans une collection, par exemple :

```
@{Event_push._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
```

**[!UICONTROL Données de personnalisation]**

>[!NOTE]
>
>Vous ne pouvez pas transmettre de collection dans les données de personnalisation. Si la notification push transactionnelle attend des collections, elle ne fonctionnera pas. Notez également qu’un format spécifique est attendu pour les données de personnalisation (par exemple : chaîne, décimal, etc.). Vous devez veiller au respect de cette exigence.

Il s’agit des champs attendus par le modèle transactionnel utilisé dans votre message Adobe Campaign Standard. Ils peuvent être utilisés pour personnaliser votre message, appliquer une mise en forme conditionnelle ou sélectionner une variante de message spécifique.
