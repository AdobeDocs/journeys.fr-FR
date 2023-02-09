---
product: adobe campaign
title: intersect
description: En savoir plus sur la fonction intersect
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 100%

---

# intersect{#intersect}

Renvoie les valeurs communes dans les deux listes dʼentrée. Si lʼune des deux listes est nulle, elle renvoie une liste vide.

## Catégorie

Liste

## Syntaxe de la fonction

`intersect(<parameters>)`

## Paramètres

| Paramètre | Type |
|-----------|------------------|
| list 1 | list |
| list 2 | list |

## Signatures et types renvoyés

`intersect(listString,listString)` : listString
`intersect(listDecimal,listDecimal)` : listDecimal
`intersect(listInteger,listInteger)` : listInteger
`intersect(listDateTime,listDateTime)` : listDateTime
`intersect(listDateTimeOnly,listDateTimeOnly)` : listDateTimeOnly
`intersect(listDateOnly,listDateOnly)` : listDateOnly
`intersect(listDuration,listDuration)` : listDuration
`intersect(listBoolean,listBoolean)` : listBoolean

Renvoie une liste.

## Exemples

```json
intersect(
    ["sports", "news", "documentary"],
    ["sports", "movies", "documentary"]
)
```

Renvoie [« sports », « news »]

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
    ["sports", "news", "documentary"]
)
```

Renvoie les éléments communs entre les attributs du profil et la liste de catégories donnée.

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
        @{myEvent.sport_interests}
)
```

Renvoie les éléments communs entre les attributs du profil et le champ dʼévénement donné.
