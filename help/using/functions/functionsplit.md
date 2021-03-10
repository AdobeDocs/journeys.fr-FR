---
product: adobe campaign
solution: Journey Orchestration
title: split
description: En savoir plus sur la fonction split
feature: Parcours
role: Ingénieur de données
level: Expérience
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '67'
ht-degree: 95%

---


# split {#split}

Partage la première chaîne d’arguments avec une chaîne de séparateur (deuxième chaîne d’arguments, qui peut être une expression régulière) pour produire une liste de chaînes (jetons).

## Catégorie

Chaîne

## Syntaxe de la fonction

`split(<parameters>)`

## Paramètres

| Paramètre | Type |
|-----------|------------------|
| chaîne d’entrée | string |
| chaîne de séparateur | string |

## Signatures et type renvoyé

`split(<input string>, <separator string>)`

Renvoie une fonction listString.

## Exemple

`split(["A_B_C"], "_")`

Renvoie `["A","B","C"]`

Exemple avec un champ d’événement &#39;event.appVersion&#39; avec la valeur : « 20.45.2.3434 »

`split(@{event.appVersion}, "\\.")`

Renvoie `["20", "45", "2", "3434"]`
