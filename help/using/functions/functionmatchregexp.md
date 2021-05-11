---
product: adobe campaign
solution: Journey Orchestration
title: matchRegExp
description: En savoir plus sur la fonction matchRegExp
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: 751fdcde-0af5-4f98-8cea-aae3ebefdb04
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
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

Explication :

Vous pouvez vérifier ici si la chaîne satisfait à l’expression régulière (syntaxe java) : commence par « Hello », puis tout type de chaîne et se termine par « World ».
