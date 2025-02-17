---
product: adobe campaign
title: toDecimal
description: En savoir plus sur la fonction toDecimal
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 11d7013c-2190-4654-8466-920861c836f5
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: ht
source-wordcount: '76'
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
| nombre entier | convertit en valeur décimale (exemple :1 devient 1,0) |

## Signatures et types renvoyés

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

Renvoie une valeur décimale.

## Exemples

`toDecimal("4.0")`

Renvoie 4.0.
