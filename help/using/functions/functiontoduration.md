---
product: adobe campaign
solution: Journey Orchestration
title: toDuration
description: En savoir plus sur la fonction toDuration
feature: Parcours
role: Ingénieur de données
level: Expérience
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 98%

---


# toDuration {#toDuration}

Convertit une valeur d’argument en une durée. Pour plus d’informations sur les types de données, consultez [cette page](../expression/data-types.md).

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
