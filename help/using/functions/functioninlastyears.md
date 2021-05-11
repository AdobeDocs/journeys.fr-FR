---
product: adobe campaign
solution: Journey Orchestration
title: inLastYears
description: En savoir plus sur la fonction inLastYears
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: 95ca3d7d-2340-4378-9af4-aa1188bed614
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '45'
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
| delta | entier |

## Signatures et type renvoyé

`inLastYears(<dateTime>,<integer>)`

Renvoie une valeur booléenne.

## Exemples

`inLastYears(toDateTime('2010-12-12T01:11:00Z'), 4))`

Renvoie true.
