---
product: adobe campaign
solution: Journey Orchestration
title: À propos de la création de parcours
description: En tant qu’utilisateur professionnel, apprenez à combiner des activités d’événement, d’orchestration et d’action afin de créer un parcours.
feature: Parcours
role: Professionnel
level: Intermédiaire
translation-type: ht
source-git-commit: 409197458ba32f9fdb3e42e4b06eae2814eff9f8
workflow-type: ht
source-wordcount: '570'
ht-degree: 100%

---


# Création d’un parcours {#concept_gq5_sqt_52b}

Cette étape est effectuée par l’**utilisateur chargé de la conception de parcours**. C’est là que vous créez vos parcours. Combinez les différentes activités d’événement, d’orchestration et d’action afin de créer des scénarios cross-canal à plusieurs étapes.

L’interface de parcours vous permet de faire glisser facilement des activités de la palette vers la zone de travail. Vous pouvez également double-cliquer sur une activité pour l’ajouter dans la zone de travail à la prochaine étape disponible. Chaque activité possède un rôle et un emplacement précis dans le processus. Les activités sont séquencées. Cela signifie que lorsqu’une activité est terminée, le flux se poursuit et traite l’activité suivante, et ainsi de suite.

Un seul espace de noms est autorisé par parcours. Lorsque vous déposez le premier événement, ceux dont les espaces de noms sont différents sont grisés. Si le premier événement est dépourvu d’espace de noms, tous ceux qui en sont pourvus sont grisés. Voir [cette page](../event/selecting-the-namespace.md). En outre, les groupes de champs Adobe Experience Platform apparaissent en grisé si le parcours contient des événements sans espace de noms. Enfin, si vous utilisez plusieurs événements dans le même parcours, tous doivent utiliser le même espace de noms.

Lors du démarrage d’un nouveau parcours, les éléments qui ne peuvent pas être déposés dans la zone de travail comme première étape sont masqués. Cela concerne toutes les actions, l’activité de la condition, l’attente et la réaction.

## Démarrage rapide {#creating_journey}

Les principales étapes nécessaires pour créer et publier un parcours sont les suivantes :

1. Dans le menu supérieur, cliquez sur l’onglet **[!UICONTROL Accueil]**.

   La liste des parcours s’affiche. Consultez [cette page](../building-journeys/using-the-journey-designer.md) pour plus d’informations sur l’interface.

   ![](../assets/journey30.png)

1. Cliquez sur **[!UICONTROL Créer]** pour créer un parcours.

   ![](../assets/journey31.png)

1. Modifiez les propriétés du parcours dans le volet de configuration qui s’affiche dans la partie droite. Voir [cette page](../building-journeys/changing-properties.md).

   ![](../assets/journey32.png)

1. Commencez par faire glisser une activité d’événement de la palette vers la zone de travail. Vous pouvez également double-cliquer sur une activité pour l’ajouter à la zone de travail.

   ![](../assets/journey33.png)

1. Faites glisser vos autres activités et configurez-les. Reportez-vous aux pages [Activités d’événements](../building-journeys/event-activities.md), [À propos des activités d’orchestration](../building-journeys/about-orchestration-activities.md) et [À propos des activités d’action](../building-journeys/about-action-activities.md).

   ![](../assets/journey34.png)

1. Votre parcours est automatiquement enregistré. Testez-le et publiez-le. Voir [Test du parcours](../building-journeys/testing-the-journey.md) et [Publication du parcours](../building-journeys/publishing-the-journey.md).

   ![](../assets/journey36.png)

## Terminaison d’un parcours {#ending_a_journey}

Deux raisons peuvent entraîner la terminaison d’un parcours pour un individu :

* Le client arrive à la dernière activité d’un chemin. Il ne doit pas nécessairement s’agir d’une activité de fin. De plus, le chemin ne doit pas obligatoirement se terminer par une activité de fin. Voir [cette page](../building-journeys/end-activity.md).
* Le client arrive à une activité de condition (ou à une activité d’attente avec une condition) et ne répond à aucune des conditions.

Il peut alors rejoindre de nouveau le parcours si la rentrée est autorisée. Voir [cette page](../building-journeys/changing-properties.md).

Les raisons suivantes peuvent entraîner la fermeture d’un parcours :

* Le parcours est fermé manuellement par le biais du bouton **[!UICONTROL Fermer aux nouvelles entrées]**.
* La date de fin du parcours est atteinte.

Lorsqu’un parcours est fermé (pour l’une des raisons ci-dessus), le statut **[!UICONTROL Fermé (aucune entrée)]** lui est attribué. Le parcours n’est alors plus accessible aux nouveaux individus. En revanche, la procédure suit son cours normal pour les personnes qui ont déjà rejoint le parcours. Au-delà de la temporisation globale par défaut de 30 jours, le statut du parcours passe à **Terminé**. Consultez cette [section](../building-journeys/changing-properties.md#entrance).

Si nécessaire, il est possible d’arrêter la progression de tous les individus dans le parcours. L’arrêt du parcours entraîne la temporisation de tous les individus qui en font partie.

Pour savoir comment fermer ou arrêter manuellement un parcours, consultez cette [section](../building-journeys/terminating-a-journey.md).