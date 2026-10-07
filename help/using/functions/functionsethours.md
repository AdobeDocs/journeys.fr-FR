---
product: adobe campaign
title: setHours
description: En savoir plus sur la fonction setHours
feature: Journeys
role: Developer
level: Experienced
exl-id: d4fe578f-c3be-4c8b-98b3-090dab0c41d1
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '106'
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

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

Renvoie 2010-12-12T04:11:00Z.

`setHours(nowWithDelta(1, "days"), 20)`

Renvoie demain à 20:XY h, XY représentant le nombre de minutes au moment de lʼévaluation de lʼheure en cours. Si lʼévaluation se produit à 02 h 45, lʼheure renvoyée sera 20 h 45.
