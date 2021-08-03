---
product: adobe campaign
title: À propos du cas d’utilisation simple
description: En savoir plus sur le cas d’utilisation simple de parcours
feature: Parcours
role: User
level: Intermediate
exl-id: 11858c7a-fdb3-43a4-af28-0d5c23fa2468
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: ht
source-wordcount: '174'
ht-degree: 100%

---

# À propos du cas d’utilisation simple{#concept_grh_vby_w2b}

## Rôle {#purpose}

Prenons l’exemple d’une marque hôtelière appelée Marlton. Dans ces hôtels, des dispositifs de balises ont été positionnés à proximité de tous les espaces stratégiques : hall, étages, restaurant, salle de fitness, piscine, etc.

Dans ce cas d’utilisation, nous allons voir comment envoyer en temps réel un message personnalisé à une personne qui se déplace à proximité d’une balise proche du spa.

Nous ne voulons envoyer un message que si cette personne est une femme. Le message doit être reçu en quelques secondes.

![](../assets/journeyuc1_16.png)

## Prérequis {#prerequisites}

Pour notre cas pratique, nous avons conçu un modèle de message transactionnel e-mail dans Adobe Campaign Standard. Nous utilisons un modèle de message transactionnel basé sur un événement. Voir cette [page](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=fr).

Adobe Campaign Standard est configuré pour envoyer des e-mails.

Lorsque des clients sont détectés à proximité d’une balise, les événements sont envoyés à partir de leur téléphone mobile. Vous devez concevoir une application mobile pour envoyer des événements du téléphone mobile du client vers le kit de développement Mobile SDK.
