---
product: adobe campaign
title: toInteger
description: En savoir plus sur la fonction toInteger
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 3fcbf4dd-3ca5-4f4b-b774-af6ac3170768
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 100%

---

# toInteger {#toInteger}

Convertit une valeur d’argument en nombre entier.

## Catégorie

Conversion

## Syntaxe de la fonction

`toInteger(<parameter>)`

## Paramètres

| Paramètre | Description |
|--- |--- |
| chaîne | convertit la valeur de la chaîne en nombre entier |
| dateTime | convertit la date en millisecondes (nombre de millisecondes depuis le début de l’époque) |
| décimal | convertit la valeur d’argument en nombre entier en supprimant la partie décimale (exemple : 1,5 devient 1) |
| booléen | convertit la valeur booléenne en 1 si true, 0 si false |

## Signatures et type renvoyé

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

Renvoie un nombre entier.

## Exemples

`toInteger("4")`

Renvoie 4.
