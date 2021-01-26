---
product: adobe campaign
solution: Journey Orchestration
title: scinder
description: En savoir plus sur la division de fonction
translation-type: tm+mt
source-git-commit: 135485c097f99483c2ddb3d03e0552f9ac134b44
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 25%

---


# fractionner {#split}

Scinde la première chaîne d’arguments avec une chaîne de séparateur (deuxième chaîne d’arguments, qui peut être une expression régulière) pour produire une liste de chaînes (jetons).

## Catégorie

Chaîne

## Syntaxe de la fonction

`split(<parameters>)`

## Paramètres

| Paramètre | Type |
|-----------|------------------|
| chaîne d’entrée | string |
| chaîne de séparateur | chaîne |

## Signatures et type renvoyé

`split(<input string>, <separator string>)`

Renvoie une listString.

## Exemple

`split(["A_B_C"], "_")`

Renvoie `["A","B","C"]`

Exemple avec un champ de événement &quot;événement.appVersion&quot; avec la valeur : &quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

Renvoie `["20", "45", "2", "3434"]`
