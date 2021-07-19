---
product: adobe campaign
title: count
description: En savoir plus sur la fonction count
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: 46528642-18d5-4ca9-a344-de2c7f939d00
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 100%

---

# count {#count}

Compte les éléments de la liste sans tenir compte des valeurs « null ».

## Catégorie

Agrégation

## Syntaxe de la fonction

`count(<listAny>)`

## Paramètres

| Paramètre | Type |
|-----------|------------------|
| Liste  | listString |
| Liste  | listBoolean |
| Liste  | listInteger |
| Liste  | listDecimal |
| Liste  | listDuration |
| Liste  | listDateTime |
| Liste  | listDateTimeOnly |

## Signatures et type renvoyé

`count(<listAny>)`

Renvoie un entier.

## Exemple

`count([10,2,10,null])`

Renvoie 3.
