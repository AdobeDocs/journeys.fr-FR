---
product: adobe campaign
title: sort
description: En savoir plus sur la fonction sort
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 8e86b919-41f5-45f9-a6af-9fe290405095
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 95%

---

# sort {#sort}

Trie une liste de valeurs dans l’ordre naturel. Le premier argument est la liste des valeurs, le second est une valeur booléenne indiquant si le tri est croissant (true) ou décroissant (false).

## Catégorie

Liste

## Syntaxe de la fonction

`sort(<parameters>)`

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
| Liste | listDateOnly |
| Booléen | Booléen |

## Signature et type renvoyé

`sort(<listInteger>,<boolean>)`

Renvoie une liste de nombres entiers.

`sort(<listDecimal>,<boolean>)`

Renvoie une liste de nombres décimaux.

`sort(<listString>,<boolean>)`

Renvoie une liste de chaînes.

`sort(<listDateTimeOnly>,<boolean>)`

Renvoie une liste de dates et heures sans tenir compte du fuseau horaire.

`sort(<listDateTime>,<boolean>)`

Renvoie une liste de dates et heures.

`sort(<listDateOnly>,<boolean>)`

Renvoie une liste de dates.

`sort(<listBoolean>,<boolean>)`

Renvoie une liste de valeurs booléennes.

## Exemple

`sort(["A", "C", "B"], true)`

Renvoie `["A","B","C"]`.

`sort([1, 3, 2], false)`

Renvoie `[3, 2, 1]`.
