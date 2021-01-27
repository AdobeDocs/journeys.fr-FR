---
product: adobe campaign
solution: Journey Orchestration
title: updateTimeZone
description: En savoir plus sur la fonction updateTimeZone
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 100%

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

## Exemple

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

Renvoie 2019-08-28T17:15:30.123+02:00.

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`

Returns "2019-08-28T17:15:30.123+02:00".-->
