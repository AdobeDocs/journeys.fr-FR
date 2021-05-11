---
product: adobe campaign
solution: Journey Orchestration
title: random
description: En savoir plus sur la fonction random
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: c47dc5f0-ea69-4814-863b-e0e483ba7770
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 100%

---

# random {#random}

Génère un nombre aléatoire compris entre 0 et 1.

## Catégorie

Mathématique

## Syntaxe de la fonction

`random(<parameters>)`

## Signature et type renvoyé

`random()`

Renvoie une valeur décimale.

## Exemple

`#{MarltonReservation.statistics.successRatio, defaultValue : random() * 100}`

Explication : si le taux de succès n’a pas de valeur/contient une valeur « null », la valeur par défaut est appliquée et sera un nombre aléatoire compris entre 0 et 1 * 100 (donc de 0 à 100).
