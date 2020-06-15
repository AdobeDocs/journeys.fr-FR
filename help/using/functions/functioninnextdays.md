---
title: inNextDays
description: En savoir plus sur la fonction inNextDays
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0e06abf518445ce145d2d042b16daaa2dfd9603e
workflow-type: tm+mt
source-wordcount: '44'
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
