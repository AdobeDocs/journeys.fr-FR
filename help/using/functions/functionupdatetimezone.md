---
product: adobe campaign
title: updateTimeZone
description: En savoir plus sur la fonction updateTimeZone
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: a5d063784b278120b61f8d2641264baf40e34a90
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 73%

---

# updateTimeZone {#updateTimeZone}

Renvoie une nouvelle valeur de date et heure, avec un nouveau fuseau horaire au même instant.

## Catégorie

Date

## Syntaxe de la fonction

`updateTimeZone(<parameters>)`

## Paramètres

* identifiant de fuseau horaire : chaîne
* dateTime

## Signature et type renvoyé

`updateTimeZone(<dateTime>,<timeZone id>)`

Renvoie une date et une heure.

## Exemples

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

Renvoie 2019-08-28T17:15:30.123+02:00.

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`
Returns "2019-08-28T17:15:30.123+02:00".-->

`updateTimeZone(@{MyExpEvent.timestamp}, "Australia/Sydney")`

Si la valeur du champ d’horodatage est `2021-11-16T16:55:12.939318+01:00`, la fonction renvoie `2021-11-17T02:55:12.942115+11:00`.
