---
product: adobe campaign
title: toDateOnly
description: En savoir plus sur la fonction toDateOnly
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
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
