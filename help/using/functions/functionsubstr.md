---
product: adobe campaign
solution: Journey Orchestration
title: substr
description: En savoir plus sur la fonction substr
feature: Parcours
role: Ingénieur de données
level: Expérience
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 95%

---


# substr {#substr}

Renvoie la sous-chaîne de l’expression sous forme de chaîne entre l’index de début et l’index de fin. Si l’index de fin n’est pas défini, il se trouve entre l’index de début et la fin.

## Catégorie

Chaîne

## Syntaxe de la fonction

`substr(<parameters>)`

## Paramètres

| Paramètre | type |
|-------------|----------|
| chaîne | chaîne |
| beginIndex | entier |
| endIndex | entier |

## Signature et type renvoyé

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

Renvoie une chaîne.

## Exemple

`substr("Hello World",6)`

Renvoie « World ».

`substr("Hello World", 0, 5)`

Renvoie « Hello ».