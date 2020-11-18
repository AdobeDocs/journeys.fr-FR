---
title: inNextMonths
description: En savoir plus sur la fonction inNextMonths
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: ht
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: ht
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

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4))`

Renvoie true.
