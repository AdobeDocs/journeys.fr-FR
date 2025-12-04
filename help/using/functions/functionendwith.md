---
product: adobe campaign
title: endWith
description: En savoir plus sur la fonction endWith
feature: Journeys
role: Developer
level: Experienced
exl-id: 6eee6057-1daf-4b9d-ae94-2b35843e3a49
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 100%

---

# endWith {#endWith}

Renvoie « true » si le deuxième paramètre est un suffixe du premier.

## Catégorie

Chaîne

## Syntaxe de la fonction

`endWith(<parameters>)`

## Paramètres

| Paramètre | Type |
|-----------|------------------|
| chaîne | chaîne |
| suffixe | chaîne |

## Signature et type renvoyé

`endWith(<string>,<string>)`

Renvoie une valeur booléenne.

## Exemple

`endWith("Hello World", "World")`

Renvoie true.

`endWith("Hello World", "Hello")`

Renvoie false.
