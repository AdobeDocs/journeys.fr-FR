---
title: toDuration
description: En savoir plus sur la fonction toDuration
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: bcb8a71a27e2b9e37af7d0260cec04ed0fda24ee
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 96%

---


# toDuration {#toDuration}

Convertit une valeur d’argument en une durée. For more information on data types, refer to [this page](../expression/data-types.md).

## Catégorie

Conversion

## Syntaxe de la fonction

`toDuration(<parameter>)`

## Paramètres

| Paramètre | Description |
|--- |--- |
| chaîne | Formats basés sur le format de durée ISO-8601 PnDTnHnMn.nS pour une durée du jour considérée comme durant exactement 24 heures |
| entier | nombre de millisecondes |

Si l’expression contient une chaîne : les formats acceptés sont basés sur le format de durée ISO-8601 PnDTnHnMn.nS pour une durée du jour considérée comme durant exactement 24 heures.

La chaîne commence par un signe facultatif, indiqué par le symbole ASCII négatif ou positif. S’il est négatif, toute la période est annulée. Vient ensuite la lettre ASCII « P », en majuscule ou en minuscule. Viennent ensuite quatre sections, chacune constituée d’un nombre et d’un suffixe. Les sections contiennent les suffixes en ASCII « D », « H », « M » et « S » pour les jours, heures, minutes et secondes, acceptés en majuscules ou en minuscules. Les suffixes doivent se succéder dans l’ordre. La lettre ASCII « T » doit apparaître avant la première occurrence, le cas échéant, d’une section d’heure, de minute ou de seconde. L’une au moins des quatre sections doit être présente, et si la lettre « T » est présente, elle doit être suivie d’au moins une section. La partie numérique de chaque section doit contenir un ou plusieurs chiffres ASCII. Le nombre peut être précédé du symbole ASCII négatif ou positif. Le nombre de jours, heures et minutes doit être converti en nombre long. Le nombre de secondes doit être converti en nombre long avec la fraction facultative. La virgule peut être un point ou une virgule. La partie fractionnaire peut comporter de zéro à 9 chiffres.

## Signatures et type renvoyé

`toDuration(<string>)`

`toDuration(<integer>)`

Renvoie une durée.

## Exemples

`toDuration("PT10H")`

Renvoie une durée de 10 heures.

`toDuration("PT4S")`

Renvoie une durée de 4 s.

`toDuration(4000)`

Renvoie une durée de 4 s.
