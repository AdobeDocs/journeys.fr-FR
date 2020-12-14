---
product: adobe campaign
solution: Journey Orchestration
title: countOnlyNull
description: En savoir plus sur la fonction countOnlyNull
translation-type: ht
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: ht
source-wordcount: '46'
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

## Signature et type renvoyé

`countOnlyNull(<listAny>)`

Renvoie un entier.

## Exemple 

`count([10,2,10,null])`

Renvoie 1.
