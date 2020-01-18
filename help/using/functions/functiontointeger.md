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
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608

---


# toInteger {#toInteger}

Convertit une valeur d’argument en entier.

## Catégorie

Conversion

## Syntaxe de la fonction

`toInteger(<parameter>)`

## Paramètres

| Paramètre | Description |
|--- |--- |
| string | convertit la valeur de chaîne en entier |
| dateTime | convertit la date en millisecondes (quelques millisecondes) |
| décimal | convertit en entier en supprimant la partie décimale (exemple : 1.5 devient 1) |
| boolean | convertit la valeur booléenne en 1 si true, 0 si false |

## Signatures et type renvoyé

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

Renvoie un entier.

## Exemples

`toInteger(4)`

Renvoie 4.
