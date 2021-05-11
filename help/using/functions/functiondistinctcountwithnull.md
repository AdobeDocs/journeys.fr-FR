---
product: adobe campaign
solution: Journey Orchestration
title: distinctCountWithNull
description: En savoir plus sur la fonction distinctCountWithNull
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: b8380d30-160e-45c2-b187-34eb42845923
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 100%

---

# distinctCountWithNull {#distinctCountWithNull}

Compte le nombre de valeurs différentes, y compris les valeurs « null ».

## Catégorie

Agrégation

## Syntaxe de la fonction

`distinctCountWithNull(<listAny>)`

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

`distinctCountwithNull(<listAny>)`

Renvoie un entier.

## Exemple

`distinctCountWithNull([10,2,10,null])`

Renvoie 3.
