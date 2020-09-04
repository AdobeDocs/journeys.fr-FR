---
title: in
description: En savoir plus sur la fonction in
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: ht
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: ht
source-wordcount: '111'
ht-degree: 100%

---


# in {#in}

Vérifie si la valeur du premier argument figure dans la liste. La vérification est effectuée par l’intermédiaire d’un opérateur Equal sur chaque valeur d’argument. Elle renvoie true si la valeur de l’argument est trouvée, false dans le cas contraire.

Le type de l’`<expression>` doit correspondre aux éléments de la liste. Pour mémoire, les types d’éléments de la liste doivent correspondre les uns aux autres.

## Catégorie

Liste

## Syntaxe de la fonction

`in(<parameters>)`

## Paramètres

| Paramètre | Type |
|-----------|------------------|
| Chaîne | Chaîne |
| Booléen | Booléen |
| Entier | Entier |
| Décimal | Décimal |
| Durée | Durée |
| DateTime | DateTime |
| DateTimeOnly | DateTimeOnly |
| Liste | listString |
| Liste | listBoolean |
| Liste | listInteger |
| Liste | listDecimal |
| Liste | listDuration |
| Liste | listDateTime |
| Liste | listDateTimeOnly |

## Signature et type renvoyé

`in(<integer>,<listInteger>)`

`in(<decimal>,<listDecimal>)`

`in(<string>,<listString>)`

`in(<boolean>,<listBoolean>)`

`in(<dateTimeOnly>,<listDateTimeOnly>)`

`in(<dateTime>,<listDateTime>)`

`in(<duration>,<listDuration>)`

Renvoie une valeur booléenne.

## Exemple

`in(4,[4,5,3,4])`

Renvoie true.

`in(8,[4,5,3,4])`

Renvoie false.

`in(#{ExperiencePlatform.ProfileFieldGroup.profile.person.gender}, ["male"])`
