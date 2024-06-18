---
product: adobe campaign
title: Événements de réaction
description: En savoir plus sur les événements de réaction
feature: Journeys
role: User
level: Intermediate
exl-id: 2f2a2905-1521-48d9-b593-9b31238282a5
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: ht
source-wordcount: '410'
ht-degree: 100%

---

# Événements de réaction {#section_dhx_gss_dgb}

Parmi les différentes activités d’événement disponibles dans la palette, vous trouverez l’événement **[!UICONTROL Réactions]** intégré. Cette activité vous permet de réagir aux données de suivi liées à un message envoyé avec des activités de type e-mail, SMS ou Push au sein du même parcours. Ces informations proviennent de la messagerie transactionnelle d’Adobe Campaign Standard. Elles sont collectées en temps réel au moment de leur partage avec Adobe Experience Platform. Dans le cas des notifications push, vous pouvez réagir aux messages envoyés, aux messages en échec et à ceux sur lesquels un utilisateur a cliqué. Pour les SMS, vous pouvez réagir aux messages envoyés ou en échec. Dans le cas des e-mails, vous pouvez réagir aux messages envoyés, ouverts et en échec, ainsi qu’à ceux sur lesquels un utilisateur a cliqué.

Vous pouvez également utiliser ce mécanisme pour effectuer une action en l’absence de réaction à vos messages. Pour ce faire, créez un deuxième chemin parallèlement à l’activité de réaction et ajoutez une activité d’attente. En l’absence de réaction au cours de la période définie dans l’activité d’attente, ce deuxième chemin sera choisi. Vous pouvez opter, par exemple, pour l’envoi d’un message de relance.

Notez que vous ne pouvez utiliser une activité de réaction dans la zone de travail que s’il existe, au préalable, une activité de type e-mail, Push ou SMS.

Voir [À propos des activités d’action](../building-journeys/about-action-activities.md).

![](../assets/journey45.png)

La procédure de configuration des événements de réaction comprend les étapes suivantes :

1. Ajoutez un **[!UICONTROL libellé]** à la réaction. Cette étape est facultative.
1. Dans la liste déroulante, sélectionnez l’activité d’action à laquelle vous souhaitez réagir. Vous pouvez sélectionner toute activité d’action figurant dans les étapes précédentes du chemin.
1. Choisissez l’événement auquel vous souhaitez réagir en fonction de l’action sélectionnée (un e-mail, un SMS ou une notification push).
1. Vous pouvez définir une temporisation de l’événement (entre 40 secondes et 30 jours), ainsi qu’un chemin de temporisation. Cette opération créera un deuxième chemin pour les personnes qui n’ont pas réagi pendant la durée définie. Lors du test d’un parcours qui a recours à un événement de réaction, la **[!UICONTROL Durée d’attente]** du mode test par défaut ainsi que sa valeur minimale sont de 40 secondes. Consultez [cette section](../building-journeys/testing-the-journey.md).

>[!NOTE]
>
>Les événements Réactions fonctionnent avec Adobe Campaign Standard, qu’il soit déployé sur des serveurs AWS ou Azure.
>
>Les événements de réaction ne peuvent pas effectuer le suivi des actions de type e-mail, SMS ou Push qui se produisent dans un autre parcours.
>
>Ils effectuent le suivi des clics sur les liens de type « tracké » (pour plus d’informations, consultez cette [page](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/links.html?lang=fr#about-tracked-urls)). Les liens de désabonnement et de page miroir ne sont pas pris en compte.

>[!IMPORTANT]
>
>Les clients de messagerie tels que Gmail autorisent le blocage d’images. Le suivi des ouvertures d’email est effectué à l’aide d’une image de 0 pixel incluse dans l’email. Si les images sont bloquées, les ouvertures d’email ne sont pas prises en compte.
