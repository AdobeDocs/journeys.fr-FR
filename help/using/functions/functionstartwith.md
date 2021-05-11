---
product: adobe campaign
solution: Journey Orchestration
title: startWith
description: En savoir plus sur la fonction startWith
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: bf0e75d6-cc7c-4a76-b215-8735eb62163b
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 100%

---

# startWith {#startWith}

Renvoie « true » si le deuxième paramètre est un préfixe du premier.

## Catégorie

Chaîne

## Syntaxe de la fonction

`startWith(<parameters>)`

## Paramètres

| Paramètre | Type |
|-------------|--------|
| chaîne | chaîne |
| préfixe | chaîne |

## Signature et type renvoyé

`startWith(<string>,<string>)`

Renvoie une valeur booléenne.

## Exemple

`startWith("Hello World", "Hello")`

Renvoie true.

`startWith("Hello World", "World")`

Renvoie false.
