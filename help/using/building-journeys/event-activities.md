---
product: adobe campaign
title: À propos des activités d’événement
description: En savoir plus sur les activités d’événement
feature: Journeys
role: User
level: Intermediate
exl-id: 3a4ff8b1-bbe7-47c8-9fba-defe4b1d5299
source-git-commit: fca24f7dd0f9170fa209474f270a4c0fb4080c03
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 74%

---

# À propos des activités d’événement {#concept_rws_1rt_52b}

Les événements configurés par l’utilisateur technique (voir [cette page](../event/about-events.md)) sont tous affichés dans la première catégorie de la palette, dans la partie gauche de l’écran.

![](../assets/journey43.png)

Commencez toujours votre parcours en faisant glisser une activité d’événement. Vous pouvez également double-cliquer sur celle-ci.

![](../assets/journey44.png)

Lorsque vous cliquez sur l’activité d’événement dans la zone de travail, le volet de configuration correspondant s’affiche. Par défaut, lorsque vous utilisez plusieurs fois un même événement, un nombre incrémenté est ajouté à son nom dans la zone de travail. Vous pouvez, en outre, utiliser le champ **[!UICONTROL Libellé]** pour ajouter au nom de l’événement un suffixe qui apparaîtra sous votre activité dans la zone de travail. Cela s’avère utile pour identifier vos événements dans la zone de travail, notamment si vous utilisez le même événement à plusieurs reprises. Cela facilite également le débogage lorsque des erreurs se produisent et permet une lecture plus facile des rapports.

![](../assets/journey33.png)

## Écoute des événements au cours d’une {#listening}

Une activité d&#39;événement située sur le parcours va écouter les événements indéfiniment. Pour écouter un événement uniquement pendant une certaine période, vous devez configurer une temporisation pour l&#39;événement.

Ce faisant, le parcours écoutera l&#39;événement au cours de la période définie dans la temporisation. Si un événement est reçu au cours de cette période, le client sera intégré dans le chemin de l&#39;événement. Si ce n’est pas le cas, le client va soit s’insérer dans le chemin d’accès au délai d’expiration s’il est défini, soit il va continuer ce parcours. Si aucun chemin de délai d’expiration n’est défini, le paramètre de délai d’expiration agit comme une activité d’attente, ce qui fait que le profil attend une période qui peut être arrêtée si un événement se produit avant la fin de cette attente. Si vous souhaitez que les profils soient exclus de ce parcours après expiration, vous devez définir un chemin d’accès au délai d’expiration.

Pour configurer une temporisation d&#39;événement, procédez comme suit :

1. Activez l&#39;option **[!UICONTROL Définir la temporisation de l&#39;événement]** dans les propriétés de l&#39;événement.

1. Définissez la durée pendant laquelle le parcours attendra l&#39;événement.

1. Si vous souhaitez orienter les individus vers un chemin de temporisation, alors qu&#39;aucun événement n&#39;est reçu au cours de la temporisation spécifiée, activez l&#39;option **[!UICONTROL Ajouter un itinéraire de temporisation]**. Si cette option n’est pas activée, le parcours se poursuit pour l’individu une fois le délai d’expiration atteint.

   ![](../assets/event-timeout.png)

Dans cet exemple, le parcours envoie un premier message de bienvenue à un client. Il n&#39;envoie ensuite un message d&#39;offre de réduction sur un repas que si le client entre dans le restaurant le lendemain. Nous avons donc configuré l&#39;événement « restaurant » avec une temporisation d&#39;un jour :

* Si l&#39;événement « restaurant » est reçu moins de 1 jour après la notification push de bienvenue, l&#39;activité push de remise sur un repas est envoyée.
* Si aucun événement « restaurant » n’est reçu dans la journée qui suit, le client ou la cliente suit le chemin de temporisation.

Notez que si vous souhaitez configurer une temporisation pour plusieurs événements placés après une activité **[!UICONTROL Attente]**, vous ne devez configurer ce délai que pour un seul de ces événements.

La temporisation s&#39;applique à tous les événements postérieurs à l&#39;activité **[!UICONTROL Attente]**. Si aucun événement n’est reçu avant le délai d’expiration spécifié, les individus s’engagent dans un seul chemin d’accès au délai d’expiration ou poursuivent ce parcours via la branche en quittant l’activité où ces paramètres d’expiration ont été définis.

![](../assets/event-timeout-group.png)
