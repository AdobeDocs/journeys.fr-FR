---
product: adobe campaign
title: inLastHours
description: En savoir plus sur la fonction inLastHours
feature: Journeys
role: Developer
level: Experienced
exl-id: 9baeb836-e029-4e19-b08e-7b7b5f27ff8f
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '45'
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

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4)`

Renvoie true.

`inLastHours(@{MyEvent.timestamp}, 4)`

Renvoie true.
