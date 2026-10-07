---
product: adobe campaign
title: toString
description: En savoir plus sur la fonction toString
feature: Journeys
role: Developer
level: Experienced
exl-id: 942e7a44-1cb1-4c99-abd6-e0b045c42c80
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '107'
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
| Entier | Convertit la valeur en représentation sous forme de chaîne (1 devient « 1 ») |
| décimal | Convertit la valeur en représentation sous forme de chaîne (1,5 devient « 1,5 ») |
| booléen | Convertit la valeur booléenne en chaîne « true » si true, en chaîne « false » si false |

## Signatures et type renvoyé

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

Renvoie une chaîne.

## Exemple

`toString(4)`

Renvoie « 4 ».
