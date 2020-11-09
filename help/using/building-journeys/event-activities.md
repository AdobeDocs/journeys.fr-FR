---
title: À propos des activités d’événement
description: En savoir plus sur les activités d’événement
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
source-wordcount: '457'
ht-degree: 33%

---


# À propos des activités d’événement {#concept_rws_1rt_52b}

The events configured by the technical user (see [this page](../event/about-events.md)) are all displayed in the first category of the palette, on the left side of the screen.

![](../assets/journey43.png)

Commencez toujours votre parcours en faisant glisser une activité d’événement. Vous pouvez également double-cliquer sur celle-ci.

![](../assets/journey44.png)

Lorsque vous cliquez sur l’activité d’événement dans la zone de travail, le volet de configuration correspondant s’affiche. Par défaut, lorsque vous utilisez plusieurs fois un même événement, un nombre incrémenté est ajouté à son nom dans la zone de travail. Vous pouvez, en outre, utiliser le champ **[!UICONTROL Libellé]** pour ajouter au nom de l’événement un suffixe qui apparaîtra sous votre activité dans la zone de travail. Cela s’avère utile pour identifier vos événements dans la zone de travail, notamment si vous utilisez le même événement à plusieurs reprises. Cela facilite également le débogage lorsque des erreurs se produisent et permet une lecture plus facile des rapports.

![](../assets/journey33.png)

## Écoute des événements pendant une période spécifique

Une activité d’événement située dans le parcours « écoute » les événements pendant une durée indéterminée. Pour écouter un événement uniquement pendant une certaine période, vous devez configurer un délai d’expiration pour le événement.

Le parcours écoute ensuite le événement pendant le délai d’attente spécifié. Si un événement est reçu au cours de cette période, le client sera intégré dans le chemin de l’événement. Si ce n&#39;est pas le cas, le client va soit suivre un délai d&#39;attente, soit terminer son voyage.

Pour configurer un délai d’expiration pour un événement, procédez comme suit :

1. Activez l’option **[!UICONTROL Activer le délai d’expiration]** du événement à partir des propriétés du événement.

1. Indiquez la durée d’attente du événement pour le parcours.

1. Si vous souhaitez envoyer les individus dans un chemin de temporisation lorsqu’aucun événement n’est reçu dans le délai d’attente spécifié, activez l’option **[!UICONTROL Définir le chemin]** de temporisation. Si cette option n&#39;est pas activée, le parcours se termine pour l&#39;individu une fois le délai dépassé.

   ![](../assets/event-timeout.png)

Dans cet exemple, le voyage envoie un premier message de bienvenue à un client. Il envoie alors une remise de repas uniquement si le client entre dans le restaurant le lendemain. Nous avons donc configuré le événement de restaurant avec un délai d&#39;attente d&#39;un jour :

* Si le événement du restaurant est reçu moins d&#39;une journée après la poussée de bienvenue, l&#39;activité de remise de repas est envoyée.
* Si aucun événement de restaurant n’est reçu le lendemain, la personne passe par le chemin du délai d’attente.

Notez que si vous souhaitez configurer un délai d’attente sur plusieurs événements positionnés après une activité d’ **[!UICONTROL attente]** , vous devez configurer le délai d’attente sur un seul de ces événements uniquement.

Le délai d’attente s’applique à tous les événements postérieurs à l’activité d’ **[!UICONTROL attente]** . Si aucun événement n’est reçu après le délai d’attente spécifié, les individus s’enchaînent dans un seul chemin d’expiration ou terminent leur voyage.

![](../assets/event-timeout-group.png)
