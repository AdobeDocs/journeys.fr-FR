---
title: distinct
description: Découvrez la fonction distincte
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608

---


# distinct {#distinct}

Renvoie les valeurs distinctes de la liste sans valeurs nulles.

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

Renvoie une liste de décimales.

`distinct(<listString>)`

Renvoie une liste de chaînes.

`distinct(<listDateTimeOnly>)`

Renvoie une liste des datetimes sans tenir compte du fuseau horaire.

`distinct(<listDateTime>)`

Renvoie une liste des datetimes.

`distinct(<listBoolean>)`

Renvoie une liste de booléens.

`distinct(<listDuration>)`

Renvoie une liste de durées.

## Exemples

`distinct([10,2,10,null])`

Returns `[10, 2]`.
