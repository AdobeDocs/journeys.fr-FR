---
product: adobe campaign
title: matchRegExp
description: En savoir plus sur la fonction matchRegExp
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: 751fdcde-0af5-4f98-8cea-aae3ebefdb04
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 100%

---

# matchRegExp {#matchRegExp}

Renvoie « true » si la chaîne du premier paramètre correspond à l’expression régulière du second paramètre. Pour plus d’informations, consultez cette [page](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

## Catégorie

Chaîne

## Syntaxe de la fonction

`matchRegExp(<parameters>)`

## Paramètres

| Paramètre | Type |
|--- |--- |
| chaîne | chaîne |
| regexp | chaîne |

## Signature et type renvoyé

`matchRegExp(<string>,<string>)`

Renvoie true.

## Exemple

`matchRegExp("Hello World", "Hello\s+World")`

Renvoie true.

Explication:

Vous pouvez vérifier ici si la chaîne satisfait à l’expression régulière (syntaxe java) : commence par « Hello », puis tout type de chaîne et se termine par « World ».
