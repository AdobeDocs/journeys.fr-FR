---
product: adobe campaign
title: inLastMonths
description: En savoir plus sur la fonction inLastMonths
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ff8effa9-404a-482b-8842-a276f029e2ed
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: ht
source-wordcount: '44'
ht-degree: 100%

---

# inLastMonths {#inLastMonths}

Renvoie « true » si une date ou une valeur dateTime donnée est comprise entre maintenant et maintenant - delta mois.

## Catégorie

Date

## Syntaxe de la fonction

`inLastMonths(<dateTime>,<delta>)`

## Paramètres

| Paramètre | Type |
|-----------|------------------|
| date et heure | dateTime |
| delta | integer |

## Signatures et type renvoyé

`inLastMonths(<dateTime>,<integer>)`

Renvoie une valeur booléenne.

## Exemples

`inLastMonths(toDateTime('2010-12-12T01:11:00Z'), 4)`

Renvoie true.
