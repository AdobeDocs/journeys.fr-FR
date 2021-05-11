---
product: adobe campaign
solution: Journey Orchestration
title: now
description: En savoir plus sur la fonction now
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: ab1f9efe-cbb7-4e3a-ace0-24f2fb6165cb
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 100%

---

# now {#now}

Renvoie la date actuelle au format date et heure. Pour plus d’informations sur les types de données, consultez [cette page](../expression/data-types.md).

## Catégorie

Date

## Syntaxe de la fonction

`now(<parameter>)`

## Paramètres

| Paramètre | Description |
|--- |--- |
| chaîne |  |

## Signatures et type renvoyé

`now()`

`now("<timeZone id>")`

Renvoie une valeur dateTime.

## Exemples

`now()`

Renvoie 2019-06-03T06:30Z.

`toString(now())`

Renvoie « 2019-06-03T06:30Z »

`now("Europe/Paris")`

Renvoie 2019-06-03T08:30+02:00.
