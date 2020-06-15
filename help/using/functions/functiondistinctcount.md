---
title: distinctCount
description: En savoir plus sur la fonction distinctCount
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '47'
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
