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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 239efa9592b011c70e2fc331df8f33820301253d

---


# toDuration {#toDuration}

Convertit une valeur d’argument en une durée. For more information on data types, refer to [](../expression/data-types.md).

## Catégorie

Conversion

## Syntaxe de la fonction

`toDuration(<parameter>)`

## Paramètres

| Paramètre | Description |
|--- |--- |
| string | formats basés sur le format de durée ISO-8601 PnDTnHnMn.nS avec des jours considérés comme exactement 24 heures |
| integer | nombre de millisecondes |

Expression de chaîne if : les formats acceptés sont basés sur le format de durée ISO-8601 PnDTnHnMn.nS avec des jours considérés comme exactement 24 heures.

La chaîne commence par un signe facultatif, signalé par le symbole négatif ou positif ASCII. Si elle est négative, toute la période est annulée. La lettre ASCII &quot;P&quot; est placée en majuscules ou en minuscules. Il y a alors quatre sections, chacune composée d&#39;un nombre et d&#39;un suffixe. Les sections ont des suffixes en ASCII de &quot;D&quot;, &quot;H&quot;, &quot;M&quot; et &quot;S&quot; pour les jours, heures, minutes et secondes, acceptés en majuscules ou en minuscules. Les suffixes doivent se produire dans l’ordre. La lettre ASCII &quot;T&quot; doit se produire avant la première occurrence, le cas échéant, d’une heure, d’une minute ou d’une seconde section. Au moins l&#39;une des quatre sections doit être présente, et si &quot;T&quot; est présent, il doit y avoir au moins une section après &quot;T&quot;. La partie numérique de chaque section doit comprendre un ou plusieurs chiffres ASCII. Le nombre peut être précédé du symbole négatif ou positif ASCII. Le nombre de jours, heures et minutes doit être analysé. Le nombre de secondes doit être analysé avec la fraction facultative. La virgule peut être un point ou une virgule. La partie fractionnaire peut comporter de zéro à 9 chiffres.

## Signatures et type renvoyé

`toDuration(<string>)`

`toDuration(<integer>)`

Renvoie une durée.

## Exemples

`toDuration("PT10H")`

Renvoie une durée de 10 heures.

`toDuration("PT4S")`

Renvoie la durée de 4 s.

`toDuration(4000)`

Renvoie la durée de 4 s.
