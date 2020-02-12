---
title: substr
description: En savoir plus sur la fonction substr
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: ht
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c

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
| beginIndex | entier |
| endIndex | entier |

## Signature et type renvoyé

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

Renvoie une chaîne.

## Exemple

`substr("Hello World",6)`

Renvoie « World ».

`substr("Hello World", 0, 5)`

Renvoie « Hello ».