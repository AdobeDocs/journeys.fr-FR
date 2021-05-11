---
product: adobe campaign
solution: Journey Orchestration
title: endWithIgnoreCase
description: En savoir plus sur la fonction endWithIgnoreCase
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: 3d14fe82-e287-4474-8d78-10efbf55d338
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '49'
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
