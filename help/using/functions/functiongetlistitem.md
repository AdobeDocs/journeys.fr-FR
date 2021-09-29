---
product: adobe campaign
title: getListItem
description: En savoir plus sur la fonction gstListItem
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: a3b24f25-5f6d-44fe-b755-3734e4fab944
source-git-commit: 5e2af021f1c82063fcc0d4e4b5edf13c57cc6c72
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 98%

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
| list | listBoolean |
| list | listInteger |
| list | listDecimal |
| list | listDuration |
| list | listDateTime |
| list | listDateTimeOnly |
| list | listDateOnly |
| index | entier |

## Signatures et type renvoyé

`getListItem(<listInteger>,<index>)`

Renvoie un entier.

`getListItem(<listDecimal>,<index>)`

Renvoie une valeur décimale.

`getListItem(<listString>,<index>)`

Renvoie une chaîne.

`getListItem(<listDateTimeOnly>,<index>)`

Renvoie une date et une heure sans prendre en compte le fuseau horaire.

`getListItem(<listDateTime>,<index>)`

Renvoie une date et une heure.

`getListItem(<listBoolean>,<index>)`

Renvoie une valeur booléenne.

`getListItem(<listDuration>,<index>)`

Renvoie une durée.

## Exemple

`getListItem([10, 2, 3], 1)`

Renvoie « 2 »

`getListItem(["A", "B", "C"], 2)`
Renvoie « C »

Exemples avec un champ d’événement &#39;event.appVersion&#39; avec la valeur : « 20.45.2.3434 »

`split(@{event.appVersion}, "\\.")`

Retours `["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

Renvoie « 20 »
