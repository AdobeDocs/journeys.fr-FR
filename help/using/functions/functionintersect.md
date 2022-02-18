---
product: adobe campaign
title: intersect
description: En savoir plus sur la fonction intersect
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 2195ee3863b38ead504eb6785ceb3c37735fade9
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# intersection{#intersect}

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
