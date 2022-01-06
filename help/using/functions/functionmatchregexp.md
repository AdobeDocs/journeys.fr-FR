---
product: adobe campaign
title: matchRegExp
description: En savoir plus sur la fonction matchRegExp
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 751fdcde-0af5-4f98-8cea-aae3ebefdb04
source-git-commit: a5d063784b278120b61f8d2641264baf40e34a90
workflow-type: ht
source-wordcount: '60'
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

Renvoie une valeur booléenne.

## Exemple

`matchRegExp("username@adobe.com", "*adobe")`

Renvoie true.
