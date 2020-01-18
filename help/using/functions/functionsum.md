---
title: sum
description: En savoir plus sur la somme des fonctions
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
source-git-commit: 654888ee62a7b9b6e3d34fc3963fb83cac719003

---


# sum {#sum}

Renvoie la somme des valeurs d’un ensemble d’expressions. Les valeurs nulles sont ignorées.

## Catégorie

Agrégation

## Syntaxe de la fonction

`sum(<parameters>)`

## Paramètres

* listInteger
* listDecimal
* duration
* integer
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
