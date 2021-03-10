---
product: adobe campaign
solution: Journey Orchestration
title: inNextHours
description: En savoir plus sur la fonction inNextHours
feature: Parcours
role: Ingénieur de données
level: Expérience
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 93%

---


# inNextHours {#inNextHours}

Renvoie « true » si une date ou une valeur dateTime donnée est comprise entre maintenant et maintenant + delta heures.

## Catégorie

Date

## Syntaxe de la fonction

`inNextHours(<dateTime>,<delta>)`

## Paramètres

| Paramètre | Type |
|-----------|------------------|
| date et heure | dateTime |
| delta | entier |

## Signatures et type renvoyé

`inNextHours(<dateTime>,<integer>)`

Renvoie une valeur booléenne.

## Exemples

`inNextHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

Renvoie true.
