---
product: adobe campaign
solution: Journey Orchestration
title: containWithIgnoreCase
description: En savoir plus sur la fonction containWithIgnoreCase
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: ebec646e-9dbb-4432-a430-ab69fb7d75cf
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '49'
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
