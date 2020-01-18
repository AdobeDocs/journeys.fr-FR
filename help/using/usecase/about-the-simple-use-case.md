---
title: A propos du cas d’utilisation simple
description: En savoir plus sur le voyage, simple cas d'utilisation
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

---


# A propos du cas d’utilisation simple{#concept_grh_vby_w2b}

## Intérêt {#purpose}

Prenons l&#39;exemple d&#39;une marque d&#39;hôtel nommée Marlton. Dans leurs hôtels, ils ont positionné des dispositifs de balises à proximité de tous les espaces stratégiques : hall, étages, restaurant, salle de fitness, piscine, etc.

Dans ce cas d&#39;utilisation, nous verrons comment envoyer un message personnalisé en temps réel à une personne qui marche à côté d&#39;une balise située près du spa.

Nous ne voulons envoyer un message que si la personne est une femme. Le message doit être reçu en quelques secondes.

![](../assets/journeyuc1_16.png)

## Conditions requises {#prerequisites}

Pour notre cas d’utilisation, nous avons conçu un modèle de messagerie transactionnelle par courrier électronique dans Adobe Campaign Standard. Nous utilisons un modèle de messagerie transactionnelle d’événement. Refer to this [page](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

Adobe Campaign Standard est configuré pour envoyer des courriers électroniques.

Les événements sont envoyés depuis le téléphone mobile du client lorsqu’ils sont détectés près d’une balise. Vous devez concevoir une application mobile pour envoyer des événements du téléphone mobile du client au kit SDK mobile.