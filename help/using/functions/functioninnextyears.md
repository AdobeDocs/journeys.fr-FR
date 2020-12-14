---
product: adobe campaign
solution: Journey Orchestration
title: inNextYears
description: En savoir plus sur la fonction inNextYears
translation-type: ht
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: ht
source-wordcount: '44'
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
