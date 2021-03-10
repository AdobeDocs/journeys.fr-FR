---
product: adobe campaign
solution: Journey Orchestration
title: distinctWithNull
description: En savoir plus sur la fonction distinctWithNull
feature: Parcours
role: Ingénieur de données
level: Expérience
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 97%

---


# distinctWithNull {#distinctWithNull}

Renvoie les valeurs distinctes de la liste. Si la liste comporte au moins une valeur « null », une valeur « null » est incluse dans la liste renvoyée.

## Catégorie

Liste

## Syntaxe de la fonction

`distinctWithNull(<parameter>)`

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

`distinctWithNull(<listInteger>)`

Renvoie une liste de nombres entiers.

`distinctWithNull(<listDecimal>)`

Renvoie une liste de nombres décimaux.

`distinctWithNull(<listString>)`

Renvoie une liste de chaînes.

`distinctWithNull(<listDateTimeOnly>)`

Renvoie une liste de dates et heures sans tenir compte du fuseau horaire.

`distinctWithNull(<listDateTime>)`

Renvoie une liste de dates et heures.

`distinctWithNull(<listBoolean>)`

Renvoie une liste de valeurs booléennes.

`distinctWithNull(<listDuration>)`

Renvoie une liste de durées.

## Exemples

`distinctWithNull([10,2,10,null])`

Renvoie [10, 2, null]
