---
product: adobe campaign
solution: Journey Orchestration
title: countWithNull
description: En savoir plus sur la fonction countWithNull
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: ea72dc20-8183-4661-8e08-ddb4f3727d3d
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 100%

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
