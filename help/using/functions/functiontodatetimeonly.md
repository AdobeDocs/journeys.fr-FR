---
product: adobe campaign
title: toDateTimeOnly
description: En savoir plus sur la fonction toDateTime
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 100%

---

# toDateTimeOnly{#toDateTimeOnly}

Convertit une valeur d’argument en une date et une heure sans prise en compte du fuseau horaire.

## Catégorie

Conversion

## Syntaxe de la fonction

`toDateTimeOnly(<parameters>)`

## Paramètres

| Paramètre | Type |
|-----------|------------------|
| date et heure au format ISO-8601 | chaîne |
| date et heure | dateTime |

## Signatures et types renvoyés

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`-->

Renvoie une date et une heure sans prendre en compte le fuseau horaire.

## Exemples

`toDateTimeOnly ("2016-08-18T23:17:59.123Z")`

Renvoie 2016-08-18T23:17:59.123.

`toDateTimeOnly(now())`

<!--`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.-->
