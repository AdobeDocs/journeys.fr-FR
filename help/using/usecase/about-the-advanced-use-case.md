---
product: adobe campaign
solution: Journey Orchestration
title: À propos du cas d’utilisation avancé
description: En savoir plus sur le cas d’utilisation avancé de parcours
feature: Parcours
role: Business Practitioner
level: Intermediate
exl-id: 43435aee-572d-4db2-88d5-6124ce074285
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 100%

---

# À propos du cas d’utilisation avancé{#concept_vzy_ncy_w2b}

## Objectif {#purpose}

Prenons l’exemple d’une marque hôtelière appelée Marlton. Dans ces hôtels, des dispositifs de balises ont été positionnés à proximité de tous les espaces stratégiques : hall, étages, restaurant, salle de fitness, piscine, etc.

>[!NOTE]
>
>Dans ce cas d’utilisation, nous employons Adobe Campaign Standard pour envoyer des messages.

Nous allons voir comment envoyer en temps réel des messages personnalisés aux clients lorsqu’ils se rapprochent d’une balise spécifique.

Tout d’abord, nous voulons envoyer un message dès qu’une personne entre dans un hôtel Marlton. Ce message ne sera envoyé que si la personne n’a reçu aucune communication de notre part au cours des dernières 24 heures.

Nous vérifions ensuite deux conditions :

* Si cette personne n’est pas membre du programme de fidélité, nous lui envoyons un e-mail pour lui proposer d’y adhérer.
* Si cette personne est déjà un membre du programme de fidélité, nous vérifions si elle a réservé une chambre :
   * Si ce n’est pas le cas, nous lui envoyons une notification push avec les tarifs des chambres.
   * Si elle a réservé une chambre, nous lui envoyons une notification push de bienvenue. En outre, si cette personne accède au restaurant dans les 6 heures qui suivent, nous lui envoyons une notification push avec une remise sur un repas.

![](../assets/journeyuc2_29.png)

Dans ce cas pratique, nous devrons créer deux événements (voir [cette page](../usecase/configuring-the-events.md)) :

* L’événement de balise de hall d’entrée qui sera envoyé au système lorsqu’un client entre dans l’hôtel.
* L’événement de balise de restaurant qui sera envoyé au système lorsqu’un client entre dans le restaurant.

Nous devrons configurer une connexion à deux sources de données (voir [cette page](../usecase/configuring-the-data-sources.md)) :

* La source de données Adobe Experience Platform intégrée, pour récupérer les informations de nos deux conditions (offre d’adhésion au programme de fidélité et date du dernier contact) ainsi que les informations de personnalisation du message.
* Le système de réservation de l’hôtel, pour récupérer les informations de statut de la réservation.

## Conditions requises         {#prerequisites}

Pour notre cas d’utilisation, nous avons conçu trois modèles de messages transactionnels Adobe Campaign Standard. Nous utilisons des modèles de messages transactionnels basés sur un événement. Voir cette [page](https://docs.adobe.com/content/help/fr-FR/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

Adobe Campaign Standard est configuré pour envoyer des e-mails et des notifications push.

L’Experience Cloud ID est utilisé comme clé pour identifier le client dans le système de réservation de l’hôtel.

Lorsque des clients sont détectés à proximité d’une balise, les événements sont envoyés à partir de leur téléphone mobile. Vous devez concevoir une application mobile pour envoyer les événements du téléphone mobile du client vers le kit de développement Mobile SDK.

Le champ personnalisé Loyalty member (Membre du programme de fidélité) a été ajouté dans XDM pour notre ID d’organisation spécifique.
