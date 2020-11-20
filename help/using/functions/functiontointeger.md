---
product: adobe campaign
solution: Journey Orchestration
title: toInteger
description: En savoir plus sur la fonction toInteger
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
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

`toInteger(4)`

Renvoie 4.
