---
product: adobe campaign
title: À propos de la création de parcours
description: En tant qu’utilisateur professionnel, apprenez à combiner des activités d’événement, d’orchestration et d’action afin de créer un parcours.
feature: Journeys
role: User
level: Intermediate
exl-id: 540b5142-9323-4cc1-9b5a-3fa20a5945bf
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 92%

---

# Création d’un parcours {#concept_gq5_sqt_52b}


>[!CAUTION]
>
>**Vous recherchez Adobe Journey Optimizer** ? Cliquez [ici](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/ajo-home){target="_blank"} pour accéder à la documentation de Journey Optimizer.
>
>
>_Cette documentation se rapporte aux anciens contenus de Journey Orchestration qui ont été remplacés par Journey Optimizer. Pour toute question concernant votre accès à Journey Orchestration ou Journey Optimizer, veuillez contacter votre équipe de compte._


Cette étape est effectuée par l&#39;**utilisateur chargé de la conception de parcours**. C&#39;est là que vous créez vos parcours. Combinez les différentes activités d&#39;événement, d&#39;orchestration et d&#39;action afin de créer des scénarios cross-canal à plusieurs étapes.

L&#39;interface de parcours vous permet de faire glisser facilement des activités de la palette vers la zone de travail. Vous pouvez également double-cliquer sur une activité pour l&#39;ajouter dans la zone de travail à la prochaine étape disponible. Chaque activité possède un rôle et un emplacement précis dans le processus. Les activités sont séquencées. Cela signifie que lorsqu&#39;une activité est terminée, le flux se poursuit et traite l&#39;activité suivante, et ainsi de suite.

Un seul espace de noms est autorisé par parcours. Lorsque vous déposez le premier événement, ceux dont les espaces de noms sont différents sont grisés. Si le premier événement est dépourvu d’espace de noms, tous ceux qui en sont pourvus sont grisés. Voir [cette page](../event/selecting-the-namespace.md). En outre, les groupes de champs Adobe Experience Platform apparaissent en grisé si le parcours contient des événements sans espace de noms. Enfin, si vous utilisez plusieurs événements dans le même parcours, tous doivent utiliser le même espace de noms.

Lors du démarrage d&#39;un nouveau parcours, les éléments qui ne peuvent pas être déposés dans la zone de travail comme première étape sont masqués. Cela concerne toutes les actions, l&#39;activité de la condition, l&#39;attente et la réaction.

## Démarrage rapide {#creating_journey}

Les principales étapes nécessaires pour créer et publier un parcours sont les suivantes :

1. Dans le menu supérieur, cliquez sur l’onglet **[!UICONTROL Accueil]**.

   La liste des parcours s&#39;affiche. Consultez [cette page](../building-journeys/using-the-journey-designer.md) pour plus d’informations sur l’interface.

   ![](../assets/journey30.png)

1. Cliquez sur **[!UICONTROL Créer]** pour créer un parcours.

   ![](../assets/journey31.png)

1. Modifiez les propriétés du parcours dans le volet de configuration qui s&#39;affiche dans la partie droite. Voir [cette page](../building-journeys/changing-properties.md).

   ![](../assets/journey32.png)

1. Commencez par faire glisser une activité d’événement de la palette vers la zone de travail. Vous pouvez également double-cliquer sur une activité pour l’ajouter à la zone de travail.

   ![](../assets/journey33.png)

1. Faites glisser vos autres activités et configurez-les. Reportez-vous aux pages [Activités d’événements](../building-journeys/event-activities.md), [À propos des activités d’orchestration](../building-journeys/about-orchestration-activities.md) et [À propos des activités d’action](../building-journeys/about-action-activities.md).

   ![](../assets/journey34.png)

1. Votre parcours est automatiquement enregistré. Testez-le et publiez-le. Voir [Test du parcours](../building-journeys/testing-the-journey.md) et [Publication du parcours](../building-journeys/publishing-the-journey.md).

   ![](../assets/journey36.png)

## Terminaison d&#39;un parcours {#ending_a_journey}

Deux raisons peuvent entraîner la terminaison d&#39;un parcours pour un individu :

* Le client arrive à la dernière activité d&#39;un chemin. Il ne doit pas nécessairement s&#39;agir d&#39;une activité de fin. De plus, le chemin ne doit pas obligatoirement se terminer par une activité de fin. Voir [cette page](../building-journeys/end-activity.md).
* Le client ou la cliente arrive à une activité de condition (ou à une activité d&#39;attente avec une condition) et ne répond à aucune des conditions.

La personne peut alors rejoindre de nouveau le parcours si la reprise est autorisée. Voir [cette page](../building-journeys/changing-properties.md).

Les raisons suivantes peuvent entraîner la fermeture d&#39;un parcours :

* Le parcours est fermé manuellement par le biais du bouton **[!UICONTROL Fermer aux nouvelles entrées]**.
* La date de fin du parcours est atteinte.

Lorsqu&#39;un parcours est fermé (pour l&#39;une des raisons ci-dessus), le statut **[!UICONTROL Fermé]** lui est attribué. Il n&#39;est alors plus accessible aux nouveaux individus. En revanche, la procédure suit son cours normal pour les personnes qui ont déjà rejoint le parcours. Au-delà de la temporisation globale par défaut de 30 jours, le statut du parcours passe à **Terminé**. Consultez cette [section](../building-journeys/changing-properties.md#entrance).

Si nécessaire, il est possible d&#39;arrêter la progression de tous les individus dans le parcours. L&#39;arrêt du parcours entraîne la temporisation de tous les individus qui en font partie.

Pour savoir comment fermer ou arrêter manuellement un parcours, consultez cette [section](../building-journeys/terminating-a-journey.md).
