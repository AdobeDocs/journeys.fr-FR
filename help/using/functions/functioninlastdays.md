---
product: adobe campaign
solution: Journey Orchestration
title: inLastDays
description: En savoir plus sur la fonction inLastDays
feature: Parcours
role: Ingénieur de données
level: Expérimenté
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 100%

---


# inLastDays {#inLastDays}

Renvoie « true » si une date ou une valeur dateTime donnée est comprise entre maintenant et maintenant - delta jours.

## Catégorie

Date

## Syntaxe de la fonction

`inLastDays(<dateTime>,<delta>)`

## Paramètres

| Paramètre | Type |
|-----------|------------------|
| date et heure | dateTime |
| delta | entier |

## Signatures et type renvoyé

`inLastDays(<dateTime>,<integer>)`

Renvoie une valeur booléenne.

## Exemples

`inLastDays(toDateTime('2019-12-12T01:11:00Z'), 4))`

Renvoie true.
