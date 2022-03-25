---
product: adobe campaign
title: toDateOnly
description: En savoir plus sur la fonction toDateOnly
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2d7b132e-5ee0-4fa0-bacc-ce4c6ec7e794
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 100%

---

# toDateOnly{#toDateOnly}

Convertit une valeur dʼargument en une valeur de date uniquement.

## Catégorie

Conversion

## Syntaxe de la fonction

`toDateOnly(<parameters>)`

## Paramètres

| Paramètre | Type |
|-----------|------------------|
| date au format ISO-8601 ou « AAAA-MM-JJ » (format de date XDM) | chaîne |
| date | date |

## Signatures et types renvoyés

`toDateOnly(<date>)`

`toDateOnly(<string>)`

Renvoie une date et une heure sans prendre en compte le fuseau horaire.

## Exemples

`toDateOnly("2016-08-18")`

renvoie un objet dateOnly représentant 2016-08-18.
