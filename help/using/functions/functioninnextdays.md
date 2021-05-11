---
product: adobe campaign
solution: Journey Orchestration
title: inNextDays
description: En savoir plus sur la fonction inNextDays
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: 47d31b56-b0ed-426d-bd79-3db3e441454b
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 100%

---

# inNextDays {#inNextDays}

Renvoie « true » si une date ou une valeur dateTime donnée est comprise entre maintenant et maintenant + delta jours.

## Catégorie

Date

## Syntaxe de la fonction

`inNextDays(<dateTime>,<delta>)`

## Paramètres

| Paramètre | Type |
|-----------|------------------|
| date et heure | dateTime |
| delta | entier |

## Signatures et type renvoyé

`inNextDays(<dateTime>,<integer>)`

Renvoie une valeur booléenne.

## Exemples

`inNextDays(toDateTime('2010-12-12T01:11:00Z'), 4)`

Renvoie true.
