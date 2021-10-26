---
product: adobe campaign
title: filter
description: En savoir plus sur la fonction filter
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 729ee71e063ae73c7c10f20bb3a410c43cb75faf
workflow-type: ht
source-wordcount: '109'
ht-degree: 100%

---

# filter{#filter}

Renvoie une valeur listObject avec les objets dont lʼattribut clé correspond à lʼune des valeurs clés données.

## Catégorie

Liste

## Syntaxe de la fonction

`filter(<parameters>)`

## Paramètres

| Paramètre | Type | Description |
|-----------|------------------|------------------|
| listToFilter | listObject | liste dʼobjects à filtrer. Il doit être une référence de champ. |
| keyAttributeName | chaîne | nom de lʼattribut dans les objets de la liste donnée, utilisé comme clé pour le filtrage |
| keyValueList | list | tableau de valeurs clés pour le filtrage |

## Signatures et types renvoyés

`filter(listObject, string, listString)`

`filter(listObject, string, listInteger)`

`filter(listObject, string, listDecimal)`

`filter(listObject, string, listDateTime)`

`filter(listObject, string, listDateTimeOnly)`

`filter(listObject, string, listDateOnly)`

`filter(listObject, string, listDuration)`

`filter(listObject, string, listBoolean)`

Renvoie une valeur listObject.

## Exemples

Voici un exemple dʼune payload transmise dans un événement entrant « myevent » :

```
"productListItems": [{
   "id": "product1",
   "name": "the product 1",
   "price": 20
},{
   "id": "product2",
   "name": "the product 2",
   "price": 30
},{
   "id": "product3",
   "name": "the product 3",
   "price": 50
}]
```

Vous pouvez utiliser lʼexpression suivante :

```
filter(
 @{myevent.productListItems},
 id", 
 ["product2", "product3", "product4"]
)
```

Renvoie une valeur listObject contenant les deux objets avec « product2 » et « product3 » comme id.
