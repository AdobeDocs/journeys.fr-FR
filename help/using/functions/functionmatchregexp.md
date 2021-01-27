---
product: adobe campaign
solution: Journey Orchestration
title: matchRegExp
description: En savoir plus sur la fonction matchRegExp
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '85'
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
