---
title: toInteger
description: En savoir plus sur la fonction toInteger
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: ht
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: ht
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
