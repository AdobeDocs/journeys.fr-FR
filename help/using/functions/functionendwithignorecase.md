---
title: endWithIgnoreCase
description: En savoir plus sur la fonction endWithIgnoreCase
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
source-git-commit: a844adc1a073aebfb7fd8a719e52f305079260b7

---


# endWithIgnoreCase {#endWithIgnoreCase}

Vérifie si la première chaîne d’arguments se termine par une chaîne spécifique (deuxième chaîne d’arguments), sans tenir compte de la casse.

## Catégorie

Chaîne

## Syntaxe de la fonction

`endWithIgnoreCase(<parameters>)`

## Paramètres

| Paramètre | Type |
|-----------|------------------|
| string | string |
| suffixe | string |

## Signature et type renvoyé

`endWithIgnoreCase(<string>,<string>)`

Renvoie une valeur booléenne.

## Exemple 

`endWithIgnoreCase("rowing is great', "AT")`

Renvoie true.
