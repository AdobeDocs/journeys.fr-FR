---
product: adobe campaign
solution: Journey Orchestration
title: inNextYears
description: En savoir plus sur la fonction inNextYears
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: 8aab6f60-feba-4be2-9a32-ba4ed7f3d7de
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 100%

---

# inNextYears {#inNextYears}

Renvoie « true » si une date ou une valeur dateTime donnée est comprise entre maintenant et maintenant + delta ans.

## Catégorie

Date

## Syntaxe de la fonction

`inNextYears(<dateTime>,<delta>)`

## Paramètres

| Paramètre | Type |
|-----------|------------------|
| date et heure | dateTime |
| delta | entier |

## Signatures et type renvoyé

`inNextYears(<dateTime>,<integer>)`

Renvoie une valeur booléenne.

## Exemples

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4))`

Renvoie true.
