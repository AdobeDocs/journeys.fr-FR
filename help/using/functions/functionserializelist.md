---
product: adobe campaign
solution: Journey Orchestration
title: serializeList
description: En savoir plus sur la fonction serializeList
translation-type: ht
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: ht
source-wordcount: '86'
ht-degree: 100%

---


# serializeList {#serializeList}

Convertit en chaîne la liste (tous types possibles) indiquée dans le premier paramètre. Le deuxième paramètre représente le séparateur à utiliser. Le troisième paramètre est une valeur booléenne indiquant si chaque élément de l’expression doit inclure des guillemets.

## Catégorie

Liste

## Syntaxe de la fonction

`serializeList(<parameters>)`

## Paramètres

| Paramètre | Type |
|-----------|------------------|
| Chaîne | Chaîne |
| Booléen | Booléen |
| DateTimeOnly | DateTimeOnly |
| Liste | listString |
| Liste | listBoolean |
| Liste | listPoint |
| Liste | listDecimal |
| Liste | listDuration |
| Liste | listDateTime |
| Liste | listDateTimeOnly |

## Signature et type renvoyé

`serializeList(<listInteger>,<string>,<boolean>)`

`serializeList(<listDecimal>,<string>,<boolean>)`

`serializeList(<listString>,<string>,<boolean>)`

`serializeList(<listBoolean>,<string>,<boolean>)`

`serializeList(<listDateTimeOnly>,<string>,<boolean>)`

`serializeList(<listDateTime>,<string>,<boolean>)`

`serializeList(<listDuration>,<string>,<boolean>)`

`serializeList(<listPoint>,<string>,<boolean>)`

Renvoie une chaîne.

## Exemple

`serializeList(["Hello","World"], " ", false)`

Renvoie « Hello World ».

`serializeList(["Hello", "World"], ",", true)`

Renvoie « Hello », « World ».
