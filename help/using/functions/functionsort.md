---
product: adobe campaign
title: sort
description: En savoir plus sur la fonction sort
feature: Journeys
role: Developer
level: Experienced
exl-id: 8e86b919-41f5-45f9-a6af-9fe290405095
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

