---
product: adobe campaign
title: intersection
description: En savoir plus sur la fonction intersecte
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: f2f5cc29f5079419662439f1cb1dee8fcb1b1ab9
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 17%

---

# intersection{#intersect}

Renvoie les valeurs communes des deux listes de saisie. Si l’une des deux listes est nulle, renvoie une liste vide.

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

`intersect(listString,listString)`: listString 
`intersect(listDecimal,listDecimal)`: listDecimal 
`intersect(listInteger,listInteger)`: listInteger 
`intersect(listDateTime,listDateTime)`: listDateTime 
`intersect(listDateTimeOnly,listDateTimeOnly)`: listDateTimeOnly 
`intersect(listDateOnly,listDateOnly)`: listDateOnly 
`intersect(listDuration,listDuration)`: listDuration 
`intersect(listBoolean,listBoolean)`: listBoolean

Renvoie une liste.

## Exemples

```
intersect(
    ["sports", "news", "documentary"],
    ["sports", "movies", "documentary"]
)
```

Renvoie [&quot;sports&quot;, &quot;news&quot;]

```
intersect(
    #{ExperienceDataPlatform.profile.interests},
    ["sports", "news", "documentary"]
)
```

Renvoie les éléments communs entre les attributs de profil et une liste donnée de catégories.

```
intersect(
        	#{ExperienceDataPlatform.profile.interests},
            @{myEvent.sport_interests}
)
```

Renvoie les éléments communs entre les attributs de profil et le champ d’événement donné.