---
title: Activité Déclencheur de segment
description: Découvrir xxxx
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 74%

---


# Activité Déclencheur de segment {#segment-trigger-activity}

## À propos de l’activité Déclencheur de segment {#about-segment-trigger-actvitiy}

L’activité Déclencheur de segment vous permet de faire entrer dans un voyage toutes les personnes appartenant à un segment d’Adobe Experience Platform. L’entrée dans un parcours peut être effectuée une fois, ou régulièrement.

Supposons que vous ayez un segment client Gold sur l&#39;Adobe Experience Platform. Avec l’activité Déclencheur de segment, vous pouvez faire en sorte que toutes les personnes appartenant au segment client Gold entrent dans un parcours puis se dirigent vers des parcours personnalisés qui exploiteront toutes les fonctionnalités des parcours : conditions, minuteurs, événements, actions.

>[!NOTE]
>
>En raison des latences d’exportation de segments, il n’est pas possible de déclencher un parcours basé sur les segments dans un délai inférieur à 1 heure.

## Configurer l’activité {#configuring-segment-trigger-activity}

1. Développez la catégorie **[!UICONTROL Orchestration]** et déposez une activité **[!UICONTROL Déclencheur de segment]** dans votre zone de travail.

   L’activité doit être la première étape d’un parcours.

1. Configurez le **[!UICONTROL type de planificateur]** de l’activité.

   Par défaut, le segment entre dans le parcours **[!UICONTROL Dès que possible]**, c’est-à-dire 1 heure après la publication du parcours. Si vous souhaitez que le segment entre dans le parcours à une date/heure spécifique ou sur une base récurrente, sélectionnez l’option de votre choix dans la liste.

   En cas de parcours récurrents, vous pouvez également définir le début et la fin du parcours.

   ![](../assets/segment-trigger-schedule.png)

1. In the **[!UICONTROL Segment]** field, choose the Adobe Experience Platform segment that will enter the journey, then click **[!UICONTROL Save]**.

   ![](../assets/segment-trigger-segment-selection.png)

1. Dans le champ **[!UICONTROL Espace de noms]**, choisissez l’espace de noms à utiliser pour identifier les personnes. Pour plus d’informations sur les espaces de noms, consultez [cette section](../event/selecting-the-namespace.md).

   >[!NOTE]
   >
   >Les personnes appartenant à un segment qui n&#39;a pas l&#39;identité sélectionnée (espace de nommage) parmi leurs différentes identités ne peuvent pas entrer dans le voyage.

1. Cliquez sur **[!UICONTROL Ok]** pour confirmer. Vous pouvez ensuite exploiter les activités disponibles pour créer votre parcours.

1. Une fois le parcours prêt, vous pouvez potentiellement le tester (voir [Test du parcours](../building-journeys/testing-the-journey.md)).

   Lorsque le mode test est activé sur un parcours commençant par une activité **[!UICONTROL Déclencheur de segment]**, 100 profils de test sont sélectionnés de manière aléatoire parmi les profils qualifiés pour le segment sélectionné. Les journaux de test vous permettront de voir le chemin des personnes dans le parcours et les erreurs potentielles rencontrées (voir [Affichage des journaux](../building-journeys/testing-the-journey.md#viewing_logs)).

   >[!NOTE]
   >
   >Veuillez noter que vous ne pourrez pas voir les 100 personnes qui suivent le parcours à l’aide de la fonction de flux visuel qui existe dans les parcours unitaires.

1. Vous pouvez ensuite publier votre parcours (voir [Publication du parcours](../building-journeys/publishing-the-journey.md)). Les personnes appartenant au segment entreront dans le parcours à la date/heure spécifiée dans le planificateur d’activité Déclencheur de segment.

   >[!IMPORTANT]
   >
   >Keep in mind that Adobe Experience Platform segments are calculated either once a day (**batch** segments) or in real-time (**streamed** segments).
   >
   >Si le segment sélectionné est en flux continu, les individus appartenant à ce segment peuvent éventuellement entrer dans le parcours en temps réel. Si le segment est par lot, les personnes nouvellement qualifiées pour ce segment peuvent éventuellement entrer dans le parcours lorsque le calcul du segment est exécuté sur l’Adobe Experience Platform.
