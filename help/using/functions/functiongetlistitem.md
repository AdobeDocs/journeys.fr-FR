---
product: adobe campaign
solution: Journey Orchestration
title: getListItem
description: En savoir plus sur la fonction gstListItem
translation-type: tm+mt
source-git-commit: 5539ea0e8f124896f5599dba63babaa3e5b0229b
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 100%

---


# getListItem {#gestListItem}

Renvoie l’élément de la liste à l’index donné.

## Catégorie

Liste

## Syntaxe de la fonction

`getListItem(<parameters>)`

## Paramètres

| Paramètre | Type |
|-----------|------------------|
| list | listString |
| liste | listBoolean |
| liste | listInteger |
| liste | listDecimal |
| liste | listDuration |
| liste | listDateTime |
| liste | listDateTimeOnly |
| index | entier |

## Signatures et type renvoyé

`getListItem(<listInteger>,<index>)`

Renvoie une liste de nombres entiers.

`getListItem(<listDecimal>,<index>)`

Renvoie une liste de nombres décimaux.

`getListItem(<listString>,<index>)`

Renvoie une liste de chaînes.

`getListItem(<listDateTimeOnly>,<index>)`

Renvoie une liste de dates et heures sans tenir compte du fuseau horaire.

`getListItem(<listDateTime>,<index>)`

Renvoie une liste de dates et heures.

`getListItem(<listBoolean>,<index>)`

Renvoie une liste de valeurs booléennes.

`getListItem(<listDuration>,<index>)`

Renvoie une liste de durées.

## Exemple

`getListItem([10, 2, 3], 1)`

Renvoie « 2 »

`getListItem(["A", "B", "C"], 3)`
Renvoie « C »

Exemples avec un champ d’événement &#39;event.appVersion&#39; avec la valeur : « 20.45.2.3434 »

`split(@{event.appVersion}, "\\.")`

Renvoie `["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

Renvoie « 20 »