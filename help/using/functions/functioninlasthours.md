---
product: adobe campaign
title: inLastHours
description: En savoir plus sur la fonction inLastHours
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: 9baeb836-e029-4e19-b08e-7b7b5f27ff8f
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: ht
source-wordcount: '46'
ht-degree: 100%

---

# inLastHours {#inLastHours}

Renvoie « true » si une date et une heure données sont comprises entre maintenant et maintenant - delta heures.

## Catégorie

Date

## Syntaxe de la fonction

`inLastHours(<dateTime>,<delta>)`

## Paramètres

| Paramètre | Type |
|-----------|------------------|
| date et heure | dateTime |
| delta | entier |

## Signatures et type renvoyé

`inLastHours(<dateTime>,<integer>)`

Renvoie une valeur booléenne.

## Exemples

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4))`

Renvoie true.

`inLastHours(@{MyEvent.timestamp}, 4)`

Renvoie true.
