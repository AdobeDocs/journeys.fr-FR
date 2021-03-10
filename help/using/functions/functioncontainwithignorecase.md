---
product: adobe campaign
solution: Journey Orchestration
title: containWithIgnoreCase
description: En savoir plus sur la fonction containWithIgnoreCase
feature: Parcours
role: Ingénieur de données
level: Expérience
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 94%

---


# containWithIgnoreCase {#containWithIgnoreCase}

Vérifie si la chaîne du deuxième argument est contenue dans la chaîne du premier argument, sans tenir compte de la casse.

## Catégorie

Chaîne

## Syntaxe de la fonction

`containWithIgnoreCase(<parameters>)`

## Paramètres

| Paramètre | Type |
|-----------|------------------|
| chaîne | chaîne |
| chaîne recherchée | chaîne |

## Signature et type renvoyé

`containWithIgnoreCase(<string>,<string>)`

Renvoie une valeur booléenne.

## Exemple

`containWithIgnoreCase("rowing is great', "GREAT")`

Renvoie true.
