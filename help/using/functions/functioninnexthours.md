---
product: adobe campaign
solution: Journey Orchestration
title: inNextHours
description: En savoir plus sur la fonction inNextHours
translation-type: ht
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: ht
source-wordcount: '44'
ht-degree: 100%

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
