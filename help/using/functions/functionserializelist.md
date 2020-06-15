---
title: serializeList
description: En savoir plus sur la fonction serializeList
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
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
