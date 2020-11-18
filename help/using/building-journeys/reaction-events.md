---
title: Événements de réaction
description: En savoir plus sur les événements de réaction
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: ht
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: ht
source-wordcount: '409'
ht-degree: 100%

---


# Événements de réaction {#section_dhx_gss_dgb}

Parmi les différentes activités d’événement disponibles dans la palette, vous trouverez l’événement **[!UICONTROL Réactions]** intégré. Cette activité vous permet de réagir aux données de suivi liées à un message envoyé avec des activités de type email, SMS ou Push au sein du même parcours. Ces informations proviennent de la messagerie transactionnelle d’Adobe Campaign Standard. Elles sont collectées en temps réel au moment de leur partage avec Adobe Experience Platform. Dans le cas des notifications push, vous pouvez réagir aux messages envoyés, aux messages en échec et à ceux sur lesquels un utilisateur a cliqué. Pour les SMS, vous pouvez réagir aux messages envoyés ou en échec. Dans le cas des emails, vous pouvez réagir aux messages envoyés, ouverts et en échec, ainsi qu’à ceux sur lesquels un utilisateur a cliqué.

Vous pouvez également utiliser ce mécanisme pour effectuer une action en l’absence de réaction à vos messages. Pour ce faire, créez un deuxième chemin parallèlement à l’activité de réaction et ajoutez une activité d’attente. En l’absence de réaction au cours de la période définie dans l’activité d’attente, ce deuxième chemin sera choisi. Vous pouvez opter, par exemple, pour l’envoi d’un message de relance.

Notez que vous ne pouvez utiliser une activité de réaction dans la zone de travail que s’il existe, au préalable, une activité de type email, Push ou SMS.

Voir [À propos des activités d’action](../building-journeys/about-action-activities.md).

![](../assets/journey45.png)

La procédure de configuration des événements de réaction comprend les étapes suivantes :

1. Ajoutez un **[!UICONTROL libellé]** à la réaction. Cette étape est facultative.
1. Dans la liste déroulante, sélectionnez l’activité d’action à laquelle vous souhaitez réagir. Vous pouvez sélectionner toute activité d’action figurant dans les étapes précédentes du chemin.
1. Choisissez l’événement auquel vous souhaitez réagir en fonction de l’action sélectionnée (un email, un SMS ou une notification push).
1. Vous pouvez définir une condition en tant qu’étape facultative. Par exemple, après une action de type email, vous pouvez choisir de créer deux chemins : l’un avec un événement de réaction pour effectuer uniquement le suivi des clics pour les clients VIP et un autre avec un événement de réaction pour effectuer le suivi des clics effectués par des femmes.

>[!NOTE]
>
>Les événements Réactions fonctionnent avec Adobe Campaign Standard, qu’il soit déployé sur des serveurs AWS ou Azure.
>
>Les événements de réaction ne peuvent pas effectuer le suivi des actions de type email, SMS ou Push qui se produisent dans un autre parcours.
>
>Ils effectuent le suivi des clics sur les liens de type « tracké » (pour plus d’informations, consultez cette [page](https://docs.adobe.com/content/help/fr-FR/campaign-standard/using/designing-content/links.html#about-tracked-urls)). Les liens de désabonnement et de page miroir ne sont pas pris en compte.

>[!IMPORTANT]
>
>Les clients de messagerie tels que Gmail autorisent le blocage d’images. Le suivi des ouvertures d’email est effectué à l’aide d’une image de 0 pixel incluse dans l’email. Si les images sont bloquées, les ouvertures d’email ne sont pas prises en compte.
