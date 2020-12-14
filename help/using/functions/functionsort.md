---
product: adobe campaign
solution: Journey Orchestration
title: sort
description: En savoir plus sur la fonction sort
translation-type: ht
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: ht
source-wordcount: '104'
ht-degree: 100%

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

`sort(<listBoolean>,<boolean>)`

Renvoie une liste de valeurs booléennes.

## Exemple

`sort(["A", "C", "B"], true)`

Renvoie `["A","B","C"]`.

`sort([1, 3, 2], false)`

Renvoie `[3, 2, 1]`.
