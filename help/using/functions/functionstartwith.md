---
product: adobe campaign
title: startWith
description: En savoir plus sur la fonction startWith
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: bf0e75d6-cc7c-4a76-b215-8735eb62163b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: ht
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
