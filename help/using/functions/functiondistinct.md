---
product: adobe campaign
solution: Journey Orchestration
title: distinct
description: En savoir plus sur la fonction distinct
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: 034e4d77-2f0e-4117-9fd4-b9e35ef71a39
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 100%

---

# distinct {#distinct}

Renvoie les valeurs distinctes de la liste sans valeurs « null ».

## Catégorie

Liste

## Syntaxe de la fonction

`distinct(<parameter>)`

## Paramètres

| Paramètre | Type |
|-----------|------------------|
| Liste | listString |
| Liste | listBoolean |
| Liste | listInteger |
| Liste | listDecimal |
| Liste | listDuration |
| Liste | listDateTime |
| Liste | listDateTimeOnly |

## Signatures et types renvoyés

`distinct(<listInteger>)`

Renvoie une liste de nombres entiers.

`distinct(<listDecimal>)`

Renvoie une liste de nombres décimaux.

`distinct(<listString>)`

Renvoie une liste de chaînes.

`distinct(<listDateTimeOnly>)`

Renvoie une liste de dates et heures sans tenir compte du fuseau horaire.

`distinct(<listDateTime>)`

Renvoie une liste de dates et heures.

`distinct(<listBoolean>)`

Renvoie une liste de valeurs booléennes.

`distinct(<listDuration>)`

Renvoie une liste de durées.

## Exemples

`distinct([10,2,10,null])`

Renvoie `[10, 2]`.
