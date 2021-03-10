---
product: adobe campaign
solution: Journey Orchestration
title: setHours
description: En savoir plus sur la fonction setHours
feature: Parcours
role: Ingénieur de données
level: Expérience
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 96%

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
