---
title: Utilisation des actions Adobe Campaign
description: En savoir plus sur les actions Adobe Campaign
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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# Utilisation des actions Adobe Campaign {#using_campaign_action}

Si vous disposez d’Adobe Campaign Standard, les activités d’action prêtes à l’emploi suivantes sont disponibles : **[!UICONTROL Courriel]**,**[!UICONTROL  Push]** et **[!UICONTROL SMS]**.

>[!NOTE]
>
>Pour cela, vous devez configurer l’action intégrée. Reportez-vous à [](../action/working-with-adobe-campaign.md).

Pour chacun de ces canaux, vous sélectionnez un **modèle** de messagerie transactionnelle Adobe Campaign Standard. En effet, l&#39;orchestration de Journey n&#39;est pas une solution d&#39;envoi de messages. Pour les canaux intégrés de messagerie, SMS et push, nous comptons sur la messagerie transactionnelle pour exécuter l&#39;envoi de messages. Cela signifie que si vous souhaitez utiliser un modèle de message spécifique dans vos voyages, vous devez le publier dans Adobe Campaign Standard. Reportez-vous à cette [page](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html) pour savoir comment utiliser cette fonctionnalité.

![](../assets/journey59.png)

Vous pouvez utiliser un modèle d’événement (également appelé en temps réel) ou de profil de messagerie transactionnelle.

>[!NOTE]
>
>Lorsque nous envoyons des messages transactionnels en temps réel (rtEvent) ou lorsque nous acheminons des messages avec un système tiers grâce à une action personnalisée, une configuration spécifique est requise pour la gestion de la fatigue, de la liste noire ou de la désabonnement. Par exemple, si un attribut &quot;liste noire&quot; ou &quot;désabonnement&quot; est stocké dans la plateforme ou dans un système tiers, une condition doit être ajoutée avant l’envoi du message pour vérifier cette condition.

Lorsque vous sélectionnez un modèle, tous les champs attendus dans la charge utile du message s’affichent dans le volet de configuration de l’activité sous **[!UICONTROL Adresse]**et Données**[!UICONTROL  de]**personnalisation. Vous devez mapper chacun de ces champs avec le champ que vous souhaitez utiliser, depuis l’événement ou la source de données. Vous pouvez également utiliser l’éditeur d’expression avancé pour transmettre une valeur manuellement, effectuer une manipulation des données sur les informations récupérées (par exemple, convertir une chaîne en majuscules) ou utiliser des fonctions telles que &quot;if, then, else&quot;. Voir la section [](../expression/expressionadvanced.md).

![](../assets/journey60.png)

## Email et SMS {#section_asc_51g_nhb}

Pour **[!UICONTROL Courriel]**et**[!UICONTROL  SMS]**, les paramètres sont identiques.

>[!NOTE]
>
>Pour les courriers électroniques, si vous utilisez un modèle de transaction de profils, le mécanisme de désabonnement est géré prêt à l’emploi par Campaign Standard. Vous ajoutez simplement un bloc de contenu de lien **[!UICONTROL de]**désabonnement dans le modèle ([en savoir plus](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)). Si vous utilisez un modèle basé sur un événement (rtEvent), vous devez ajouter, dans le message, un lien transmettant le courrier électronique de la personne dans le paramètre d’URL et pointant vers une page d’entrée de désabonnement. Vous devez créer cette page d’entrée et vous assurer que la décision de désabonnement de la personne est transmise à Adobe.

Tout d&#39;abord, vous devez choisir un modèle de messagerie transactionnelle. Voir la section [](../building-journeys/about-action-activities.md).

Deux catégories sont disponibles : **[!UICONTROL Adresse]**et Données**[!UICONTROL  de]**personnalisation.

Vous pouvez facilement définir où récupérer l’ **[!UICONTROL adresse]**ou les données**[!UICONTROL  de]** personnalisation à l’aide de l’interface. Vous pouvez parcourir les événements et les champs de source de données disponibles. Vous pouvez également utiliser l’éditeur d’expression avancé pour des cas d’utilisation plus avancés, tels que l’utilisation d’une source de données qui nécessite le transfert de paramètres ou des manipulations. Voir la section [](../expression/expressionadvanced.md).

**[!UICONTROL Son adresse]**

>[!NOTE]
>
>Cette catégorie n’est visible que si vous sélectionnez un message transactionnel &quot;événement&quot;. Pour les messages de profil, le champ **[!UICONTROL Adresse]**est automatiquement récupéré d’Adobe Campaign Standard par le système.

Il s’agit des champs dont le système a besoin pour savoir où envoyer le message. Pour un modèle de courrier électronique, il s’agit de l’adresse électronique. Pour un SMS, c&#39;est le numéro de téléphone mobile.

![](../assets/journey61.png)

**[!UICONTROL Données de personnalisation]**

>[!NOTE]
>
>Vous ne pouvez pas transmettre une collection dans les données de personnalisation. Si le courriel ou le SMS transactionnel attend des collections, il ne fonctionnera pas. Notez également que les données de personnalisation ont un format attendu (par exemple : string, decimal, etc.). Vous devez veiller à respecter ces formats.

Il s’agit des champs attendus par le message Adobe Campaign Standard. Ces champs peuvent être utilisés pour personnaliser le message, appliquer une mise en forme conditionnelle ou sélectionner une variante de message spécifique.

![](../assets/journey62.png)

## Push {#section_im3_hvf_nhb}

Avant d’utiliser l’activité Push, votre application mobile doit être configurée avec Campaign Standard pour envoyer des notifications Push. Utilisez cet [article](https://helpx.adobe.com/campaign/kb/integrate-mobile-sdk.html) pour effectuer les étapes de mise en oeuvre nécessaires pour les dispositifs portables.

Tout d’abord, vous devez choisir une application mobile dans la liste déroulante et un message transactionnel. Voir la section [](../building-journeys/about-action-activities.md).

![](../assets/journey62bis.png)

Deux catégories sont disponibles : Données **[!UICONTROL Target]**et**[!UICONTROL  personnalisation]**.

**[!UICONTROL Cible]**

>[!NOTE]
>
>Cette catégorie n’est visible que si vous sélectionnez un message d’événement. Pour les messages de profil, les champs **[!UICONTROL Target]**sont automatiquement récupérés par le système à l’aide du rapprochement effectué par Adobe Campaign Standard.

Dans cette section, vous devez définir la plateforme **[!UICONTROL Push]**. La liste déroulante vous permet de sélectionner**[!UICONTROL  Apple Push Notification Server]** (iOS) ou **[!UICONTROL Firebase Cloud Messaging]**(Android). Vous pouvez également sélectionner un champ spécifique à partir d’un événement ou d’une source de données ou définir une expression avancée.

Vous devez également définir le jeton **[!UICONTROL d’enregistrement]**. L’expression dépend de la manière dont le jeton est défini dans la charge utile de l’événement ou dans d’autres informations d’orchestration du voyage. Il peut s’agir d’un champ simple ou d’une expression plus complexe au cas où le jeton serait défini dans une collection, par exemple :

```
@{Event_push._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
```

**[!UICONTROL Données de personnalisation]**

>[!NOTE]
>
>Vous ne pouvez pas transmettre une collection dans les données de personnalisation. Si le push transactionnel attend des collections, il ne fonctionnera pas. Notez également que les données de personnalisation ont un format attendu (par exemple : string, decimal, etc.). Vous devez veiller à respecter ces formats.

Il s’agit des champs attendus par le modèle transactionnel utilisé dans votre message Adobe Campaign Standard. Ces champs peuvent être utilisés pour personnaliser votre message, appliquer une mise en forme conditionnelle ou sélectionner une variante de message spécifique.
