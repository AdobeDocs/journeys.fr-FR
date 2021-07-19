---
product: adobe campaign
title: max
description: En savoir plus sur la fonction max
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: 116713e0-7bbd-4150-8495-f87034eafb5f
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 100%

---

# max{#max}

Renvoie la valeur maximale d’un ensemble d’expressions, exprimée sous la forme d’une liste ou de deux expressions. Les valeurs « null » sont ignorées.

## Catégorie

Agrégation

## Syntaxe de la fonction

`max(<parameter>)`

## Paramètres

* listDuration
* listInteger
* listDecimal
* listDateTime
* listDateTimeOnly
* durée
* entier
* decimal
* dateTime
* dateTimeOnly

## Signatures et types renvoyés

`max(<listDuration>)`

Renvoie une durée.

`max(<listInteger>)`

Renvoie une durée.

`max(<listDateTimeOnly>)`

Renvoie une date et une heure sans prendre en compte le fuseau horaire.

`max(<listDateTime>)`

Renvoie une date et une heure.

`max(<listDecimal>)`

Renvoie une valeur décimale.

`max(<decimal>,<decimal>)`

Renvoie une valeur décimale.

`max(<duration>,<duration>)`

Renvoie une durée.

`max(<dateTime>,<dateTime>)`

Renvoie une date et une heure.

`max(<dateTimeOnly>,<dateTimeOnly>)`

Renvoie une date et une heure sans prendre en compte le fuseau horaire.

`max(<integer>,<integer>)`

Renvoie un entier.

## Exemples

`max(@{BarBeacon.inventory},5)`

`max([10,3,8])`

Renvoie 10.

`max([10,null,8])`

Renvoie 10.
