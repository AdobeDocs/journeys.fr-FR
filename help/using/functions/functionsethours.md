---
title: setHours
description: En savoir plus sur la fonction setHours
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
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c

---


# setHours {#setHours}

Définit uniquement les heures d’une date ou d’une date. Par exemple, si vous voulez attendre une certaine heure demain, vous pouvez forcer l&#39;heure.

## Catégorie

Date

## Syntaxe de la fonction

`setHours(<parameter>)`

## Paramètres

| Paramètre | Type |
|--- |--- |
| heure de la date | dateTime |
| heure de la date sans tenir compte du fuseau horaire | dateTimeOnly |
| heures | integer |

## Signatures et type renvoyé

`setHours(<dateTime>,<hours>)`

Renvoie une date-time.

`setHours(<dateTimeOnly>,<hours>)`

Renvoie une date et une heure sans prendre en compte le fuseau horaire.

## Exemples

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4))`

Renvoie 2010-12-12T04:11:00Z.

`setHours(nowWithDelta(1, "days"), 20)`

Retourne demain à 20 heures.
