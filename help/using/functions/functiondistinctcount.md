---
product: adobe campaign
solution: Journey Orchestration
title: distinctCount
description: En savoir plus sur la fonction distinctCount
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: b7844bce-1286-4d9e-b9e6-619c2d467c91
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 100%

---

# distinctCount{#distinctCount}

Compte le nombre de valeurs différentes en ignorant les valeurs « null ».

## Catégorie

Agrégation

## Syntaxe de la fonction

`distinctCount(<listAny>)`

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

`distinctCount(<listAny>)`

Renvoie un entier.

## Exemple

`distinctCount([10,2,10,null])`

Renvoie 2.
