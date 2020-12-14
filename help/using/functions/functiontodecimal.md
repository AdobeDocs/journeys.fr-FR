---
product: adobe campaign
solution: Journey Orchestration
title: toDecimal
description: En savoir plus sur la fonction toDecimal
translation-type: ht
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
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
