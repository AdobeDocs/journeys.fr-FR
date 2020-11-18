---
title: toDecimal
description: En savoir plus sur la fonction toDecimal
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
source-wordcount: '71'
ht-degree: 100%

---


# toDecimal {#toDecimal}

Convertit une valeur d’argument en valeur décimale, selon son type.

## Catégorie

Conversion

## Syntaxe de la fonction

`toDecimal(<parameter>)`

## Paramètres

| Paramètre | Description |
|--- |--- |
| chaîne | convertit la valeur de la chaîne en valeur décimale |
| dateTime | convertit la date en millisecondes (nombre de millisecondes depuis le début de l’époque) |
| booléen | convertit la valeur booléenne en 1 si true, 0 si false |
| entier | convertit en valeur décimale (exemple :1 devient 1,0) |

## Signatures et types renvoyés

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

Renvoie une valeur décimale.

## Exemples

`toDecimal("4.0")`

Renvoie 4,0.
