---
product: adobe campaign
solution: Journey Orchestration
title: inLastMonths
description: En savoir plus sur la fonction inLastMonths
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: ff8effa9-404a-482b-8842-a276f029e2ed
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '45'
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
| delta | entier |

## Signatures et type renvoyé

`inLastMonths(<dateTime>,<integer>)`

Renvoie une valeur booléenne.

## Exemples

`inLastMonths(toDateTime('2010-12-12T01:11:00Z'), 4))`

Renvoie true.
