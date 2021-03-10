---
product: adobe campaign
solution: Journey Orchestration
title: sum
description: En savoir plus sur la fonction sum
feature: Parcours
role: Ingénieur de données
level: Expérience
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 94%

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
* entier
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

Renvoie 18,6.
