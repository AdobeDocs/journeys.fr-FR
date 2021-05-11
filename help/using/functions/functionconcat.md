---
product: adobe campaign
solution: Journey Orchestration
title: concat
description: En savoir plus sur la fonction concat
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: 7a516705-2bbe-4b42-97fc-aeae11082002
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 100%

---

# concat {#concat}

Concatène deux paramètres de chaîne ou une liste de chaînes.

## Catégorie

Chaîne

## Syntaxe de la fonction

`concat(<parameters>)`

## Paramètres

| Paramètre | Type |
|-----------|------------------|
| Liste | listString |
| chaîne | chaîne |

## Signature et type renvoyé

`concat(<string>,<string>)`

`concat(<listString>)`

Renvoie une chaîne.

## Exemple

`concat("Hello","World")`

Renvoie « HelloWorld ».

`concat(["Hello"," ","World"])`

Renvoie « Hello World ».
