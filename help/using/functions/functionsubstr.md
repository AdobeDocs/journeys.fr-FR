---
product: adobe campaign
title: substr
description: En savoir plus sur la fonction substr
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: dda01de5-b865-4323-ac36-2e3d90d213ee
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: ht
source-wordcount: '64'
ht-degree: 100%

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
| beginIndex | nombre entier |
| endIndex | nombre entier |

## Signature et type renvoyé

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

Renvoie une chaîne.

## Exemple

`substr("Hello World",6)`

Renvoie « World ».

`substr("Hello World", 0, 5)`

Renvoie « Hello ».
