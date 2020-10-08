---
title: setDays
description: En savoir plus sur la fonction setDays
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 100%

---


# setDays {#setDays}

Définit le jour d’une date ou d’une date sans prise en compte du fuseau horaire. Par exemple, si vous voulez attendre jusqu’à un certain jour du mois, vous pouvez forcer le jour.

## Catégorie

Date

## Syntaxe de la fonction

`setDays(<parameter>)`

## Paramètres

| Paramètre | Type |
|--- |--- |
| date et heure | dateTime |
| date et heure sans prise en compte du fuseau horaire | dateTimeOnly |
| jours | entier |

## Signatures et type renvoyé

`setDays(<dateTime>,<days>)`

Renvoie une date et une heure.

`setDays(<dateTimeOnly>,<days>)`

Renvoie une date et une heure sans prendre en compte le fuseau horaire.

## Exemples

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

Renvoie 2010-12-25T01:11:00Z.

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
