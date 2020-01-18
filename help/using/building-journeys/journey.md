---
title: A propos de la création de parcours
description: Découvrez comment construire un voyage
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



# Création d&#39;un voyage {#concept_gq5_sqt_52b}

Cette étape est effectuée par l’utilisateur **** professionnel. C&#39;est là que vous créez vos voyages. Combinez les différentes activités d’événement, d’orchestration et d’action pour créer vos scénarios multicanaux.

L’interface de voyage vous permet de faire glisser et déposer facilement des activités de la palette dans la zone de travail. Vous pouvez également cliquer deux fois sur une activité pour l’ajouter dans la trame à l’étape suivante disponible. Chaque activité a un rôle et une place spécifiques dans le processus. Les activités sont séquencées. Lorsqu’une activité est terminée, le flux continue et traite l’activité suivante, etc.

Un seul espace de noms est autorisé par voyage. Lorsque vous déposez le premier événement, les événements avec différents espaces de noms sont grisés. Si le premier événement n’a pas d’espace de noms, tous les événements avec un espace de noms sont grisés. Voir la section [](../event/selecting-the-namespace.md). En outre, les groupes de champs de la plateforme d’expérience sont grisés si le voyage comporte des événements sans espace de noms. Et finalement, si vous utilisez plusieurs événements dans le même parcours, ils doivent utiliser le même espace de noms.

## Démarrage rapide {#creating_journey}

Voici les étapes principales pour créer et publier un voyage.

1. Dans le menu supérieur, cliquez sur l’onglet **[!UICONTROL Accueil]**.

   La liste des voyages s’affiche. Voir [](../building-journeys/using-the-journey-designer.md) pour plus d’informations sur l’interface.

   ![](../assets/journey30.png)

1. Cliquez sur **[!UICONTROL Créer]**pour créer un nouveau voyage.

   ![](../assets/journey31.png)

1. Modifiez les propriétés du voyage dans le volet de configuration qui s’affiche sur le côté droit. Voir la section [](../building-journeys/changing-properties.md).

   ![](../assets/journey32.png)

1. Commencez par faire glisser une activité d’événement de la palette vers le canevas. Vous pouvez également cliquer deux fois sur une activité pour l’ajouter à la trame.


   ![](../assets/journey33.png)

1. Faites glisser et déposez vos autres activités et configurez-les. See [](../building-journeys/event-activities.md), [](../building-journeys/about-orchestration-activities.md) and [](../building-journeys/about-action-activities.md).

   ![](../assets/journey34.png)

1. Votre voyage est automatiquement enregistré. Testez votre voyage et publiez-le. Voir [](../building-journeys/testing-the-journey.md) et [](../building-journeys/publishing-the-journey.md).

   ![](../assets/journey36.png)

## Fin d&#39;un voyage{#ending_a_journey}

Il existe deux façons de terminer un voyage :

* La personne arrive à la dernière activité d&#39;un chemin. Cette dernière activité peut être une activité finale ou une autre activité. Il n’est pas obligatoire de terminer un chemin avec une activité finale. Voir la section [](../building-journeys/end-activity.md).
* La personne arrive à une activité de condition (ou à une activité d’attente avec une condition) et ne correspond à aucune des conditions.

La personne peut alors reprendre le voyage si le retour est autorisé. Voir la section [](../building-journeys/changing-properties.md).

