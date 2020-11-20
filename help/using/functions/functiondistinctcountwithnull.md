---
product: adobe campaign
solution: Journey Orchestration
title: distinctCountWithNull
description: En savoir plus sur la fonction distinctCountWithNull
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '47'
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
