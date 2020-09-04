---
title: distinctWithNull
description: En savoir plus sur la fonction distinctWithNull
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: ht
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: ht
source-wordcount: '99'
ht-degree: 100%

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
