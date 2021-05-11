---
product: adobe campaign
solution: Journey Orchestration
title: setDays
description: En savoir plus sur la fonction setDays
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: eee7bf61-9101-4959-aa93-27d0f221c517
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '75'
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
