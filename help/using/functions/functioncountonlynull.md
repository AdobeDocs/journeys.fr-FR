---
product: adobe campaign
title: countOnlyNull
description: En savoir plus sur la fonction countOnlyNull
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: e6170a21-0418-4311-a43b-fd4f323cd020
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: ht
source-wordcount: '49'
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
| Liste | listString |
| Liste | listBoolean |
| Liste | listInteger |
| Liste | listDecimal |
| Liste | listDuration |
| Liste | listDateTime |
| Liste | listDateTimeOnly |
| Liste | listDateOnly |

## Signature et type renvoyé

`countOnlyNull(<listAny>)`

Renvoie un entier.

## Exemple

`countOnlyNull([10,2,10,null])`

Renvoie 1.
