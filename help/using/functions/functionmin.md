---
product: adobe campaign
solution: Journey Orchestration
title: min
description: En savoir plus sur la fonction min
feature: Parcours
role: Ingénieur de données
level: Expérience
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 96%

---


# min {#min}

Renvoie la valeur minimale d’un ensemble d’expressions, exprimée sous la forme d’une liste ou de deux expressions. Les valeurs « null » sont ignorées.

## Catégorie

Agrégation

## Syntaxe de la fonction

`min(<parameters>)`

## Paramètres

* listDuration
* listInteger
* listDecimal
* listDateTime
* listDateTimeOnly
* durée
* entier
* décimal
* dateTime
* dateTimeOnly

## Signatures et types renvoyés

`min(<listDuration>)`

Renvoie une durée.

`min(<listInteger>)`

Renvoie une durée.

`min(<listDateTimeOnly>)`

Renvoie une date et une heure sans prendre en compte le fuseau horaire.

`min(<listDateTime>)`

Renvoie une date et une heure.

`min(<listDecimal>)`

Renvoie une valeur décimale.

`min(<decimal>,<decimal>)`

Renvoie une valeur décimale.

`min(<duration>,<duration>)`

Renvoie une durée.

`min(<dateTime>,<dateTime>)`

Renvoie une date et une heure.

`min(<dateTimeOnly>,<dateTimeOnly>)`

Renvoie une date et une heure sans prendre en compte le fuseau horaire.

`min(<integer>,<integer>)`

Renvoie un entier.

## Exemples

`min(@{BarBeacon.inventory},5)`

`min([10,3,8])`

Renvoie 3.

`min([10,null,8])`

Renvoie 8.
