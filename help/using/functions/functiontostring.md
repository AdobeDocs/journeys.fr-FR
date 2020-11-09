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
translation-type: tm+mt
source-git-commit: bcb8a71a27e2b9e37af7d0260cec04ed0fda24ee
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 91%

---


# toString {#toString}

Convertit une valeur d’argument en valeur de chaîne, selon son type. For more information on data types, refer to [this page](../expression/data-types.md).

## Catégorie

Conversion

## Syntaxe de la fonction

`toString(<parameter>)`

## Paramètres

| Paramètre | Description |
|--- |--- |
| dateTime | Convertit la date au format UTC |
| dateTimeOnly | Convertit la date au format UTC |
| durée | Convertit le paramètre dans le nombre de millisecondes correspondant sous forme de chaîne |
| fuseau horaire | Convertit le paramètre en représentation sous forme de chaîne de l’identifiant de fuseau horaire (id JODA) |
| entier | Convertit la valeur en représentation sous forme de chaîne (1 devient « 1 ») |
| décimal | Convertit la valeur en représentation sous forme de chaîne (1,5 devient « 1,5 ») |
| booléen | Convertit la valeur booléenne en chaîne « true » si true, en chaîne « false » si false |

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

Renvoie « 4 ».
