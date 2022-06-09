---
product: adobe campaign
title: limit
description: En savoir plus sur la fonction limit
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7e006660-1206-4b8a-9e5b-c6fbeee9cc8f
source-git-commit: 9f5ef0497227a370e2e1f4a62450611ae2e336b9
workflow-type: ht
source-wordcount: '135'
ht-degree: 100%

---

# limit {#limit}

Renvoie les N premiers ou derniers éléments d’une liste.

## Catégorie

Liste

## Syntaxe de la fonction

`limit(<parameters>)`

## Paramètres

| Paramètre | Type | Description |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly, or listObject | Liste à trier. Pour listObject, il doit s’agir d’une référence de champ. |
| numberOfItems | nombre entier | Nombre d’éléments à renvoyer à partir de la liste donnée. |
| firstOrLastItems | booléen | Ce paramètre est facultatif (true par défaut). true renvoie les premiers éléments. false renvoie les derniers éléments. |

## Signature et type renvoyé

`limit(<listString>,<integer>)`
`limit(<listString>,<integer>,<boolean>)`

Renvoie une liste de chaînes.

`limit(<listInteger>,<integer>)`
`limit(<listInteger>,<integer>,<boolean>)`

Renvoie une liste de nombres entiers.

`limit(<listDecimal>,<integer>)`
`limit(<listDecimal>,<integer>,<boolean>)`

Renvoie une liste de nombres décimaux.

`limit(<listBoolean>,<integer>)`
`limit(<listBoolean>,<integer>,<boolean>)`

Renvoie une liste de valeurs booléennes.

`limit(<listDateOnly>,<integer>)`
`limit(<listDateOnly>,<integer>,<boolean>)`

Renvoie une liste de dates.

`limit(<listDateTimeOnly>,<integer>)`
`limit(<listDateTimeOnly>,<integer>,<boolean>)`

Renvoie une liste de dates et heures sans tenir compte du fuseau horaire.

`limit(<listDateTime>,integer>)`
`limit(<listDateTime>,<integer>,<boolean>)`

Renvoie une liste de dates et heures.

`limit(<listDuration>,<integer>)`
`limit(<listDuration>,<integer>,<boolean>)`

Renvoie une liste de durées.

`limit(<listObject>,<integer>)`
`limit(<listObject>,<integer>,<boolean>)`

Renvoie une liste d’objets.

## Exemple

`limit(["A", "B", "C", "D", "E"], 3)`

Renvoie `["A","B","C"]`.

`limit(["A", "B", "C", "D", "E"], 3, false)`

Renvoie `["C","D","E"]`.
