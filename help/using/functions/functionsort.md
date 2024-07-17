---
product: adobe campaign
title: sort
description: En savoir plus sur la fonction sort
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 8e86b919-41f5-45f9-a6af-9fe290405095
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 100%

---

# sort {#sort}

Trie une liste de valeurs ou d’objets dans l’ordre naturel.

## Catégorie

Liste

## Syntaxe de la fonction

`sort(<parameters>)`

## Paramètres

| Paramètre | Type | Description |
|-----------|------------------|------------------|
| listToSort | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly, or listObject | Liste à trier. Pour listObject, il doit s’agir d’une référence de champ. |
| keyAttributeName | Chaîne | Ce paramètre est uniquement destiné à listObject. Le nom de lʼattribut dans les objets de la liste donnée, utilisé comme clé pour le tri. |
| sortingOrder | Booléen | ascendant (true) ou descendant (false) |

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

`sort(<listObject>,<string>,<boolean>)`

Renvoie une liste d’objets.

## Exemple

`sort(["A", "C", "B"], true)`

Renvoie `["A","B","C"]`.

`sort([1, 3, 2], false)`

Renvoie `[3, 2, 1]`.

