---
product: adobe campaign
title: inLastYears
description: En savoir plus sur la fonction inLastYears
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 95ca3d7d-2340-4378-9af4-aa1188bed614
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: ht
source-wordcount: '44'
ht-degree: 100%

---

# inLastYears {#inLastYears}

Renvoie « true » si une date ou une valeur dateTime donnée est comprise entre maintenant et maintenant - delta ans.

## Catégorie

Date

## Syntaxe de la fonction

`inLastYears(<dateTime>,<delta>)`

## Paramètres

| Paramètre | Type |
|-----------|------------------|
| date et heure | dateTime |
| delta | integer |

## Signatures et type renvoyé

`inLastYears(<dateTime>,<integer>)`

Renvoie une valeur booléenne.

## Exemples

`inLastYears(toDateTime('2010-12-12T01:11:00Z'), 4)`

Renvoie true.
