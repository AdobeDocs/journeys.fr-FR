---
title: maintenant
description: En savoir plus sur la fonction maintenant
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
source-git-commit: 654888ee62a7b9b6e3d34fc3963fb83cac719003

---


# maintenant {#now}

Renvoie la date actuelle au format d’heure de la date. Pour plus d’informations sur les types de données, voir [](../expression/data-types.md).

## Catégorie

Date

## Syntaxe de la fonction

`now(<parameter>)`

## Paramètres

| Paramètre | Description |
|--- |--- |
| string |  |

## Signatures et type renvoyé

`now()`

`"now(<timeZone id>")`

Renvoie une dateTime.

## Exemples

`now()`

Renvoie 2019-06-03T06:30Z.

`toString(now())`

Renvoie &quot;2019-06-03T06:30Z&quot;

`now("Europe/Paris")`

Renvoie 2019-06-03T08:30+02:00.