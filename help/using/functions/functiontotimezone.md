---
title: toTimeZone
description: En savoir plus sur la fonction toTimeZone
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 100%

---


# toTimeZone {#toTimeZone}

Convertit une valeur de chaîne en fuseau horaire.

## Catégorie

Conversion

## Syntaxe de la fonction

`toTimeZone(<parameter>)`

## Paramètres

| Paramètre | Description |
|--- |--- |
| chaîne | La valeur de chaîne doit contenir l’identifiant de fuseau horaire. Il peut s’agir d’une référence de champ ou d’une expression |

## Signatures et types renvoyés

`toTimeZone(<string>)`

Renvoie un fuseau horaire.

## Exemples

`toTimeZone("UTC")`

Renvoie un fuseau horaire au format UTC.
