---
product: adobe campaign
solution: Journey Orchestration
title: countWithNull
description: En savoir plus sur la fonction countWithNull
feature: Parcours
role: Ingénieur de données
level: Expérience
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 94%

---


# countWithNull {#countWithNull}

Compte tous les éléments de la liste, y compris les valeurs « null ».

## Catégorie

Agrégation

## Syntaxe de la fonction

`countWithNull(<listAny>)`

## Paramètres

| Paramètre | Type |
|-----------|------------------|
| Liste | listString |
| Liste | listBoolean |
| Liste | listInteger |
| Liste | listDecimal |
| Liste | listDuration |
| Liste | listDateTime |
| Liste | listDateTimeOnly |

## Signature et type renvoyé

`countWithNull(<listAny>)`

Renvoie un entier.

## Exemple

`count([10,2,10,null])`

Renvoie 4.
