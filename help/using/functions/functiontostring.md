---
title: toString
description: En savoir plus sur la fonction toString
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


# toString {#toString}

Convertit une valeur d’argument en valeur de chaîne, selon son type. Pour plus d’informations sur les types de données, voir [](../expression/data-types.md).

## Catégorie

Conversion

## Syntaxe de la fonction

`toString(<parameter>)`

## Paramètres

| Paramètre | Description |
|--- |--- |
| dateTime | convertit la date au format de date UTC |
| dateTimeOnly | convertit la date au format de date UTC |
| duration | convertir en nombre de millisecondes correspondant sous forme de chaîne |
| fuseau horaire | convertir en représentation de chaîne d’ID de fuseau horaire (ID JODA) |
| integer | convertit en représentation sous forme de chaîne de la valeur (1 devient &quot;1&quot;) |
| décimal | convertit en représentation sous forme de chaîne de la valeur (1.5 devient &quot;1.5&quot;) |
| boolean | convertir la valeur booléenne en &quot;true&quot; si true, &quot;false&quot; si false |

## Signatures et type renvoyé

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<timeZone>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

Renvoie une chaîne.

## Exemple 

`toString(4)`

Renvoie &quot;4&quot;.
