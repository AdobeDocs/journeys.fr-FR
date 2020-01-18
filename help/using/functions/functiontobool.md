---
title: toBool
description: En savoir plus sur la fonction toBool
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

---


# toBool {#toBool}

Convertit une valeur d’argument en valeur booléenne, selon son type.

* De la chaîne : essayez de convertir la valeur de chaîne en valeur booléenne, de &quot;true&quot; si la valeur de chaîne est &quot;true&quot;, de &quot;false&quot; dans le cas contraire.
* Numérique : true si la valeur numérique n’est pas égale à 0, false dans le cas contraire

## Catégorie

Conversion

## Syntaxe de la fonction

`toBool(<parameter>)`

## Paramètres

* décimal
* boolean
* string
* integer

## Signatures et types renvoyés

`toBool(<decimal>)`

`toBool(<boolean>)`

`toBool(<string>)`

`toBool(<integer>)`

Renvoie une valeur booléenne.

## Exemples

`toBool("true")`

`toBool(1)`

Renvoie true.

`toBool("this is not a boolean")`

Renvoie false.
