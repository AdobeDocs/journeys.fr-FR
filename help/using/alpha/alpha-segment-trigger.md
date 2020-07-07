---
title: activité du déclencheur de segment
description: Apprendre xxxx
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
source-git-commit: c8d28b51f14ba511a860874e45d341a6977c58fa
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 0%

---


# activité du déclencheur de segment {#segment-trigger-activity}

## A propos de l&#39;activité du déclencheur de segment {#about-segment-trigger-actvitiy}

L’activité Déclencheur de segment vous permet de faire entrer dans un voyage toutes les personnes appartenant à un segment Experience Platform. L&#39;entrée dans un voyage peut être effectuée une seule fois, ou sur une base régulière.

Supposons que vous ayez un segment client Gold sur Experience Platform. Avec l’activité Déclencheur de segment, vous pouvez faire entrer toutes les personnes appartenant au segment Client Or dans un voyage et les faire s’enchaîner dans des voyages personnalisés qui exploiteront toutes les fonctionnalités du voyage : conditions, minuteries, événements, actions.

>[!NOTE]
>
>En raison des latences d’exportation de segments, il n’est pas possible de déclencher un parcours par segment dans une période plus courte que 1 heure.

## Configuring the activity {#configuring-segment-trigger-activity}

1. Unfold the **[!UICONTROL Orchestration]** category and drop a **[!UICONTROL Segment Trigger]** activity into your canvas.

   L&#39;activité doit être placée comme la première étape d&#39;un voyage.

1. Configurez le type **[!UICONTROL de]** Planificateur d&#39;activité.

   Par défaut, le segment entre dans le parcours **[!UICONTROL Dès que possible]**, c’est-à-dire 1 heure après la publication du parcours. Si vous souhaitez que le segment entre dans le parcours à une date/heure spécifique ou sur une base récurrente, sélectionnez l’option de votre choix dans la liste.

   En cas de voyages récurrents, vous pouvez également définir le début et la fin du voyage.

   ![](../assets/segment-trigger-schedule.png)

1. Dans le champ **[!UICONTROL Segment]** , sélectionnez le segment Experience Platform qui va entrer dans le parcours, puis cliquez sur **[!UICONTROL Enregistrer]**.

   ![](../assets/segment-trigger-segment-selection.png)

1. Dans le champ **[!UICONTROL Espace de nommage]** , choisissez l’espace de nommage à utiliser pour identifier les individus. For more on namespaces, refer to [this section](../event/selecting-the-namespace.md).

   >[!NOTE]
   >
   >Les personnes appartenant à un segment qui n&#39;a pas l&#39;identité sélectionnée (espace de nommage) parmi leurs différentes identités ne peuvent pas entrer dans le voyage.

1. Click **[!UICONTROL Ok]** to confirm. Vous pouvez ensuite exploiter les activités disponibles pour construire votre parcours.

1. Une fois le voyage prêt, vous pouvez potentiellement le tester (voir [Test du voyage](../building-journeys/testing-the-journey.md)).

   Lorsque le mode test est activé sur un parcours commençant par une activité Déclencheur **[!UICONTROL de]** segment, 100 profils de test sont sélectionnés de manière aléatoire parmi les profils qualifiés pour le segment sélectionné. Les journaux de test vous permettront de voir le chemin des personnes dans le parcours et les erreurs potentielles rencontrées (voir [Affichage des journaux](../building-journeys/testing-the-journey.md#viewing_logs)).

   >[!NOTE]
   >
   >Notez que vous ne pourrez pas voir les 100 personnes qui suivent le voyage à l&#39;aide de la fonction de flux visuel qui existe dans les trajets unitaires.

1. Vous pouvez ensuite publier votre parcours (voir [Publication du parcours](../building-journeys/publishing-the-journey.md)). Les personnes appartenant au segment entreront dans le voyage à la date et à l&#39;heure spécifiées dans le Planificateur d&#39;activité du déclencheur de segment.

   >[!IMPORTANT]
   >
   >Gardez à l’esprit que les segments Experience Platform sont calculés une fois par jour (segments **par lot** ) ou en temps réel (segments **diffusés** ).
   >
   >Si le segment sélectionné est diffusé en continu, les individus appartenant à ce segment peuvent éventuellement entrer dans le voyage en temps réel. Si le segment est par lot, les personnes nouvellement qualifiées pour ce segment peuvent éventuellement entrer dans le parcours lorsque le calcul du segment est exécuté sur l’Experience Platform.
