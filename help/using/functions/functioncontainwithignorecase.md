---
product: adobe campaign
solution: Journey Orchestration
title: containWithIgnoreCase
description: En savoir plus sur la fonction containWithIgnoreCase
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 100%

---


# containWithIgnoreCase {#containWithIgnoreCase}

Vérifie si la chaîne du deuxième argument est contenue dans la chaîne du premier argument, sans tenir compte de la casse.

## Catégorie

Chaîne

## Syntaxe de la fonction

`containWithIgnoreCase(<parameters>)`

## Paramètres

| Paramètre | Type |
|-----------|------------------|
| chaîne | chaîne |
| chaîne recherchée | chaîne |

## Signature et type renvoyé

`containWithIgnoreCase(<string>,<string>)`

Renvoie une valeur booléenne.

## Exemple

`containWithIgnoreCase("rowing is great', "GREAT")`

Renvoie true.
