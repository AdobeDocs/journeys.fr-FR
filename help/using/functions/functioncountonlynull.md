---
product: adobe campaign
title: countOnlyNull
description: En savoir plus sur la fonction countOnlyNull
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: e6170a21-0418-4311-a43b-fd4f323cd020
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 100%

---

# countOnlyNull {#countOnlyNull}

Compte le nombre de valeurs « null » dans la liste.

## Catégorie

Agrégation

## Syntaxe de la fonction

`countOnlyNull(<listAny>)`

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

## Signature et type renvoyé

`countOnlyNull(<listAny>)`

Renvoie un entier.

## Exemple

`count([10,2,10,null])`

Renvoie 1.
