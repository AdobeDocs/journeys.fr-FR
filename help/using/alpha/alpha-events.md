---
title: événements basés sur des règles
description: En savoir plus sur les événements basés sur des règles.
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
source-git-commit: f146a22cec5ffbbc61b51f8fc3c875078b2ee6bf
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 8%

---


# événements basés sur des règles{#simplified-events}

Nous avons simplifié la configuration des événements d’expérience. Nous introduisons une nouvelle méthode qui ne nécessite pas l&#39;utilisation d&#39;un eventID. Lorsque vous configurez votre événement en Journey Orchestration, vous pouvez désormais définir un événement basé sur des règles.

Ce nouveau type de événement ne génère pas d’eventID. En utilisant l&#39;éditeur d&#39;expressions simple, vous définissez maintenant simplement une règle qui sera utilisée par le système pour identifier les événements pertinents qui déclencheront vos voyages. Cette règle peut être basée sur n’importe quel champ disponible dans la charge de événement, par exemple l’emplacement du profil ou le nombre d’éléments ajoutés au panier du profil.

Cette nouvelle méthode est principalement transparente pour les utilisateurs. La seule modification est un nouveau champ dans l’écran de définition de événement.

1. Dans le menu de gauche, cliquez sur l’icône **Admin** , puis sur **Événements**. La liste des événements s’affiche.

   ![](../assets/alpha-event1.png)

1. Cliquez sur le bouton **Ajouter** pour créer un événement. Le volet de configuration d’événement s’ouvre dans la partie droite de l’écran.

   ![](../assets/alpha-event2.png)

1. Entrez le nom de votre événement. Vous pouvez également ajouter une description.

   ![](../assets/alpha-event3.png)

1. Dans le nouveau champ **ID de type** de Événement, sélectionnez **Règle basée sur** des règles.

   ![](../assets/alpha-event4.png)

   >[!NOTE]
   >
   >Le type **System Generated** est la méthode existante qui requiert un eventID. Reportez-vous à [cette section](../event/about-events.md).

1. Définissez les **champs** de Schéma **et de charge utile**. Reportez-vous à [cette section](../event/defining-the-payload-fields.md).

   ![](../assets/alpha-event5.png)

   >[!NOTE]
   >
   >Lorsque vous sélectionnez le type **Généré par** système, seuls les schémas dont le mixin est de type eventID sont disponibles. Lorsque vous sélectionnez le type basé sur **les** règles, tous les schémas de Événement d’expérience sont disponibles.

1. Cliquez à l’intérieur du champ de condition **d’ID de** Événement. À l’aide de l’éditeur d’expressions simple, définissez la condition qui sera utilisée par le système pour identifier les événements qui déclencheront votre voyage.

   ![](../assets/alpha-event6.png)

   Dans notre exemple, nous avons écrit une condition basée sur la ville du profil. Cela signifie que chaque fois que le système reçoit un événement qui correspond à cette condition (champ **Ville** et valeur **Paris** ), il le transmet au Journey Orchestration.

1. Définissez l’ **Espace de nommage** et la **clé**. Voir [Sélection de l’espace de nommage](../event/selecting-the-namespace.md) et [Définition de la clé](../event/defining-the-event-key.md)de événement.

   ![](../assets/alpha-event7.png)

Les autres étapes pour la configuration du événement et la création du parcours restent inchangées.

Le événement est maintenant configuré et prêt à être déposé dans un voyage comme tout autre événement. Chaque fois qu&#39;un événement correspondant à la règle est envoyé au système, il est transmis au Journey Orchestration pour déclencher vos voyages.

