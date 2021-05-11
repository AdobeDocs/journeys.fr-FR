---
product: adobe campaign
solution: Journey Orchestration
title: toString
description: En savoir plus sur la fonction toString
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: 942e7a44-1cb1-4c99-abd6-e0b045c42c80
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 100%

---

# toString {#toString}

Convertit une valeur d’argument en valeur de chaîne, selon son type. Pour plus d’informations sur les types de données, consultez [cette page](../expression/data-types.md).

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
