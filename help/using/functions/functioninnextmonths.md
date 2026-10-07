---
product: adobe campaign
title: inNextMonths
description: En savoir plus sur la fonction inNextMonths
feature: Journeys
role: Developer
level: Experienced
exl-id: b5e8d514-a24d-42a2-b422-ec5d6617048a
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
source-wordcount: '44'
ht-degree: 100%
---
# inNextMonths {#inNextMonths}

Renvoie « true » si une date ou une valeur dateTime donnée est comprise entre maintenant et maintenant + delta mois.

## Catégorie

Date

## Syntaxe de la fonction

`inNextMonths(<dateTime>,<delta>)`

## Paramètres

| Paramètre | Type |
|-----------|------------------|
| date et heure | dateTime |
| delta | entier |

## Signatures et type renvoyé

`inNextMonths(<dateTime>,<integer>)`

Renvoie une valeur booléenne.

## Exemples

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4)`

Renvoie true.
