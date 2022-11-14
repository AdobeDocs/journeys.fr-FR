---
product: adobe campaign
title: sum
description: En savoir plus sur la fonction sum
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 04289d72-aade-4725-b1f5-47cf55e3a40b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 100%

---

# sum {#sum}

Renvoie la somme des valeurs d’un ensemble d’expressions. Les valeurs « null » sont ignorées.

## Catégorie

Agrégation

## Syntaxe de la fonction

`sum(<parameters>)`

## Paramètres

* listInteger
* listDecimal
* durée
* nombre entier
* décimal

## Signatures et types renvoyés

`sum(<listDecimal>)`

Renvoie une valeur décimale.

`sum(<listInteger>)`

Renvoie un entier.

`sum(<integer>,<integer>)`

Renvoie un entier.

`sum(<decimal>,<decimal>)`

Renvoie une valeur décimale.

## Exemples

`sum(@{BarBeacon.inventory},5)`

`sum([10,3,8])`

Renvoie 21.

`sum([10.5,null,8.1])`

Renvoie 18.6.
