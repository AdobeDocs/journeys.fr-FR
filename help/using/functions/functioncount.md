---
title: count
description: En savoir plus sur la fonction count
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: ht
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: ht
source-wordcount: '50'
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
| Liste | listString |
| Liste | listBoolean |
| Liste | listInteger |
| Liste | listDecimal |
| Liste | listDuration |
| Liste | listDateTime |
| Liste | listDateTimeOnly |

## Signatures et type renvoyé

`count(<listAny>)`

Renvoie un entier.

## Exemple

`count([10,2,10,null])`

Renvoie 3.
