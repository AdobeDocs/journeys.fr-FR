---
title: À propos du cas d’utilisation avancé
description: En savoir plus sur le cas d’utilisation avancé de parcours
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
source-git-commit: 54b54a64ad2822eec96008ac4a2e16c208a4a3ab
workflow-type: tm+mt
source-wordcount: '413'
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

* Si cette personne n’est pas un membre du programme de fidélité, nous lui envoyons un email pour lui proposer l’offre d’adhésion au programme de fidélité.
* Si cette personne est déjà un membre du programme de fidélité, nous vérifions si elle a réservé une chambre :
   * Si ce n’est pas le cas, nous lui envoyons une notification push avec les tarifs des chambres.
   * Si elle a réservé une chambre, nous lui envoyons une notification push de bienvenue. En outre, si cette personne accède au restaurant dans les prochaines 6 heures, nous lui envoyons une notification push avec une remise sur un repas.

![](../assets/journeyuc2_29.png)

Dans ce cas d’utilisation, nous devrons créer deux événements (voir [](../usecase/configuring-the-events.md)) :

* L’événement de balise de hall d’entrée qui sera envoyé au système lorsqu’un client entre dans l’hôtel.
* L’événement de balise de restaurant qui sera envoyé au système lorsqu’un client entre dans le restaurant.

Nous devrons configurer une connexion à deux sources de données (voir [](../usecase/configuring-the-data-sources.md)) :

* La source de données Experience Platform intégrée, pour récupérer les informations de nos deux conditions (offre d’adhésion au programme de fidélité et date du dernier contact) ainsi que les informations de personnalisation du message.
* Le système de réservation de l’hôtel, pour récupérer les informations de statut de la réservation.

## Conditions requises    {#prerequisites}

Pour notre cas d’utilisation, nous avons conçu trois modèles de messages transactionnels Adobe Campaign Standard. Nous utilisons des modèles de messages transactionnels basés sur un événement. À ce propos, consultez cette [page](https://docs.adobe.com/content/help/fr-FR/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

Adobe Campaign Standard est configuré pour envoyer des emails et des notifications push.

L’Experience Cloud ID est utilisé comme clé pour identifier le client dans le système de réservation de l’hôtel.

Lorsque des clients sont détectés à proximité d’une balise, les événements sont envoyés à partir de leur téléphone mobile. Vous devez concevoir une application mobile pour envoyer les événements du téléphone mobile du client vers le kit de développement Mobile SDK.

Le champ personnalisé Loyalty member a été ajouté dans XDM pour notre ID d’organisation spécifique.
