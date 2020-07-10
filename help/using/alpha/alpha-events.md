---
title: Événements basés sur des règles
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
ht-degree: 100%

---


# Événements basés sur des règles{#simplified-events}

Nous avons simplifié la configuration des événements d’expérience. Nous proposons une nouvelle méthode qui ne nécessite pas l’utilisation d’un identifiant d’événement. Lorsque vous configurez votre événement dans Journey Orchestration, vous pouvez désormais définir un événement basé sur des règles.

Ce nouveau type d’événement ne génère pas d’identifiant d’événement. En utilisant l’éditeur d’expression simple, vous définissez désormais simplement une règle qui sera utilisée par le système pour identifier les événements pertinents qui déclencheront vos parcours. Cette règle peut être basée sur n’importe quel champ disponible dans le payload, par exemple l’emplacement du profil ou le nombre d’éléments ajoutés au panier du profil.

Cette nouvelle méthode est majoritairement transparente pour les utilisateurs. La seule modification est un nouveau champ dans l’écran de définition de l’événement.

1. Dans le menu de gauche, cliquez sur l’icône **Administration**, puis sur **Événements**. La liste des événements s’affiche.

   ![](../assets/alpha-event1.png)

1. Cliquez sur le bouton **Ajouter** pour créer un événement. Le volet de configuration d’événement s’ouvre dans la partie droite de l’écran.

   ![](../assets/alpha-event2.png)

1. Saisissez le nom de votre événement. Vous pouvez également ajouter une description.

   ![](../assets/alpha-event3.png)

1. Dans le nouveau champ **Type d’identifiant d’événement**, sélectionnez **Basé sur des règles**.

   ![](../assets/alpha-event4.png)

   >[!NOTE]
   >
   >Le type **Généré par le système** est la méthode existante qui requiert un identifiant d’événement. Reportez-vous à [cette section](../event/about-events.md).

1. Définissez les champs **Schéma** et **Payload**. Reportez-vous à [cette section](../event/defining-the-payload-fields.md).

   ![](../assets/alpha-event5.png)

   >[!NOTE]
   >
   >Lorsque vous sélectionnez le type **Généré par le système**, seuls les schémas dont le mixin est de type Identifiant d’événement sont disponibles. Lorsque vous sélectionnez le type **Basé sur des règles**, tous les schémas Événement d’expérience sont disponibles.

1. Cliquez à l’intérieur du champ **Condition de l’identifiant d’événement**. À l’aide de l’éditeur d’expression simple, définissez la condition qui sera utilisée par le système pour identifier les événements qui déclencheront votre parcours.

   ![](../assets/alpha-event6.png)

   Dans notre exemple, nous avons écrit une condition basée sur la ville du profil. Cela signifie que chaque fois que le système reçoit un événement qui correspond à cette condition (champ **Ville** et valeur **Paris**), il le transmet à Journey Orchestration.

1. Définissez l’**espace de noms** et la **clé**. Voir [Sélection de l’espace de noms](../event/selecting-the-namespace.md) et [Définition de la clé de l’événement](../event/defining-the-event-key.md).

   ![](../assets/alpha-event7.png)

Les autres étapes pour la configuration d’événement et la création de parcours restent inchangées.

L’événement est maintenant configuré et prêt à être déposé dans un parcours comme n’importe quel autre événement. Chaque fois qu’un événement correspondant à la règle est envoyé au système, il est transmis à Journey Orchestration pour déclencher vos parcours.

