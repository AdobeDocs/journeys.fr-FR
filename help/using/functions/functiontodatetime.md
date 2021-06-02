---
product: adobe campaign
title: toDateTime
description: En savoir plus sur la fonction toDateTime
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: 0b8d1a82-a55a-4a4d-ad1b-35499d52b469
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 100%

---

# toDateTime {#toDateTime}

Convertit les paramètres en une valeur de date et d’heure, selon leurs types.

## Catégorie

Conversion

## Syntaxe de la fonction

`toDateTime(<parameters>)`

## Paramètres

| Paramètre | Type |
|-----------|------------------|
| date et heure au format ISO-8601 | chaîne |
| identifiant de fuseau horaire | chaîne |
| date et heure sans prise en compte du fuseau horaire | dateTimeOnly |
| valeur entière d’une époque en millisecondes | entier |

>[!NOTE]
>
>L’identifiant de fuseau horaire doit être une constante sous forme de chaîne. Il ne peut pas s’agir d’une référence de champ ni d’une expression. Pour plus d’informations sur les types de données, consultez [cette page](../expression/data-types.md).

## Signatures et types renvoyés

`toDateTime(<string>)`

`toDateTime(<dateTimeOnly>,<stringified time zone id>)`

`toDateTime(<integer>)`

Renvoie une valeur **dateTime**.

<!--`toDateTime(<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`

Returns a date time with default time zone UTC.

`toDateTime(<year>,<month>,<dayOfMonth>)`
`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>)`
`toDateTime(<timeZone>,<year>,<month>,<dayOfMonth>)`

Return a datetime where hour, minute and second set to 0.

`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`
`toDateTime(<string>)`
`toDateTime(<string>,<integer>)`
`toDateTime(<stringified timeZone>,<dateTimeOnly)`

`toDateTime(<timeZone>,<integer>)`

Return a datetime.

-->

## Exemples

`toDateTime ("2016-08-18T23:17:59.123Z")`

Renvoie 2016-08-18T23:17:59.123Z

`toDateTime(toDateTimeOnly("2016-08-18T23:17:59.123"),"UTC")`

Renvoie 2016-08-18T23:17:59.123Z

`toDateTime(1560762190189)`

Renvoie 2019-06-17T09:03:10.189Z

<!--`toDateTime ("2016-08-18T23:17:59.123", "UTC")`

Returns 2016-08-18T23:17:59.123Z.

`toDateTime("Z",2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000Z.

`toDateTime("Z",2016,8,18)`

Returns 2016-08-18T00:00:00.000Z.-->
