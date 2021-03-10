---
product: adobe campaign
solution: Journey Orchestration
title: random
description: En savoir plus sur la fonction random
feature: Parcours
role: Ingénieur de données
level: Expérience
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 94%

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
