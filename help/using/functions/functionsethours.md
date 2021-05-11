---
product: adobe campaign
solution: Journey Orchestration
title: setHours
description: En savoir plus sur la fonction setHours
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: d4fe578f-c3be-4c8b-98b3-090dab0c41d1
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 100%

---

# setHours {#setHours}

Définit les heures d’une date ou d’une date sans prise en compte du fuseau horaire. Par exemple, si vous voulez attendre jusqu’à une certaine heure demain, vous pouvez forcer l’heure.

## Catégorie

Date

## Syntaxe de la fonction

`setHours(<parameter>)`

## Paramètres

| Paramètre | Type |
|--- |--- |
| date et heure | dateTime |
| date et heure sans prise en compte du fuseau horaire | dateTimeOnly |
| heures | entier |

## Signatures et type renvoyé

`setHours(<dateTime>,<hours>)`

Renvoie une date et une heure.

`setHours(<dateTimeOnly>,<hours>)`

Renvoie une date et une heure sans prendre en compte le fuseau horaire.

## Exemples

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4))`

Renvoie 2010-12-12T04:11:00Z.

`setHours(nowWithDelta(1, "days"), 20)`

Renvoie la date de demain à 20 heures.
