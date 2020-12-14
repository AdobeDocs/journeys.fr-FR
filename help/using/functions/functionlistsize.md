---
product: adobe campaign
solution: Journey Orchestration
title: listSize
description: En savoir plus sur la fonction listSize
translation-type: ht
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: ht
source-wordcount: '45'
ht-degree: 100%

---


# listSize {#listSize}

Compte le nombre d’éléments dans la liste.

## Catégorie

Liste

## Syntaxe de la fonction

`listSize(<parameters>)`

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

## Signatures et type renvoyé

`listSize(<listInteger>)`

`listSize(<listDecimal>)`

`listSize(<listString>)`

`listSize(<listBoolean>)`

`listSize(<listDateTimeOnly>)`

`listSize(<listDateTime>)`

`listSize(<listDuration>)`

`listSize(<listPoint>)`

Renvoie un nombre entier.

## Exemple

`listSize([10,2,3])`

Renvoie 3.
