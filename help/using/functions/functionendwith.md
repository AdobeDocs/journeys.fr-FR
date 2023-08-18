---
product: adobe campaign
title: endWith
description: En savoir plus sur la fonction endWith
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 6eee6057-1daf-4b9d-ae94-2b35843e3a49
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
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
| Suffixe | chaîne |

## Signature et type renvoyé

`endWith(<string>,<string>)`

Renvoie une valeur booléenne.

## Exemple

`endWith("Hello World", "World")`

Renvoie true.

`endWith("Hello World", "Hello")`

Renvoie false.
