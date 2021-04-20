---
product: adobe campaign
solution: Journey Orchestration
title: endWithIgnoreCase
description: En savoir plus sur la fonction endWithIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 100%

---


# endWithIgnoreCase {#endWithIgnoreCase}

Vérifie si la chaîne du premier argument se termine par une chaîne spécifique (chaîne du deuxième argument), sans tenir compte de la casse.

## Catégorie

Chaîne

## Syntaxe de la fonction

`endWithIgnoreCase(<parameters>)`

## Paramètres

| Paramètre | Type |
|-----------|------------------|
| chaîne | chaîne |
| suffixe | chaîne |

## Signature et type renvoyé

`endWithIgnoreCase(<string>,<string>)`

Renvoie une valeur booléenne.

## Exemple

`endWithIgnoreCase("rowing is great', "AT")`

Renvoie true.
