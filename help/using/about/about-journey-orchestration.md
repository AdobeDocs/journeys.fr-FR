---
title: À propos de l'orchestration du voyage
description: En savoir plus sur l'orchestration de Journey
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: fed6fd8d8ee497ec47727f7297dc72f319fabe27

---


# À propos de l&#39;orchestration du voyage{#concept_nd3_mqt_52b}

Créez des cas d’utilisation d’orchestration en temps réel à l’aide de données contextuelles stockées dans des événements ou des sources de données.

Journey Orchestration est un service d’applications intégré à la plateforme Experience Platform.

![](../assets/journeydiagram.png)

L’orchestration du parcours permet une orchestration en temps réel basée sur des données contextuelles issues d’événements, des informations issues de la plateforme Adobe Experience Platform ou des données issues de services API tiers. Vous pouvez configurer une action personnalisée si vous utilisez un système tiers pour envoyer vos messages. Si vous disposez d’Adobe Campaign Standard, vous pourrez envoyer des courriers électroniques, des notifications Push et des SMS à l’aide des fonctionnalités [de messagerie](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)transactionnelle d’Adobe Campaign Standard.

Dans l’onglet Configuration de l’événement, un utilisateur **** technique configure les événements attendus dans les voyages. Les données des événements entrants sont normalisées à la suite du modèle de données d’expérience Adobe (XDM). Les événements proviennent des API de gestion en flux continu pour les événements authentifiés et non authentifiés (tels que les événements Adobe Mobile SDK).

Dans l’onglet de configuration de la source de données, un utilisateur **** technique configure :

* Les différents champs exposés à partir d’Adobe Experience Platform dans le concepteur du voyage à des fins de création de conditions et de personnalisation.
* Sources de données personnalisées supplémentaires que vous exploitez dans le concepteur du voyage. Les sources de données personnalisées sont des connexions entre l’orchestration de Journey et des systèmes ou services tiers via l’API. Vous pouvez connecter un système tiers, tel qu’un système de fidélité. Les services tiers peuvent être, par exemple, une API météorologique.

Avec le concepteur du voyage, un utilisateur **** professionnel peut facilement faire glisser un événement d’entrée, ajouter des conditions et spécifier l’action à exécuter.

Vous créez ensuite des conditions basées sur :

* time
* données provenant de la charge utile d’événement
* informations provenant de sources de données : Source de données Profil du client en temps réel ou sources de données personnalisées

Vous pouvez utiliser la condition de division pour envoyer les personnes dans le voyage dans différentes directions.

Les activités d’action vous permettent ensuite d’envoyer un message via un système tiers. Si vous disposez d’Adobe Campaign Standard, envoyez des SMS personnalisés en temps réel, des notifications Push ou des courriers électroniques.

Comme l&#39;orchestration du voyage est à plusieurs étapes, vous pouvez créer des scénarios avancés. Par exemple, après un premier événement et une première action, vous pouvez faire glisser d’autres événements. Ensuite, vous pouvez ajouter une seconde action, placer une activité d’attente pour attendre un certain temps, ajouter une condition de division pour pousser les personnes vers deux chemins différents, puis envoyer des messages différents.

>[!NOTE]
>
>Cette documentation est fréquemment mise à jour pour refléter les modifications récentes du produit. Cependant, certaines captures d’écran peuvent légèrement différer de l’interface du produit.

