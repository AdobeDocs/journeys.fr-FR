---
product: adobe campaign
solution: Journey Orchestration
title: now
description: En savoir plus sur la fonction now
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '49'
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