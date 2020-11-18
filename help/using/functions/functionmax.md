---
title: max
description: En savoir plus sur la fonction max
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: ht
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: ht
source-wordcount: '88'
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
* décimal
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
