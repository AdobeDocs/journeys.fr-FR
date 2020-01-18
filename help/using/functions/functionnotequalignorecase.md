---
title: notEqualWithIgnoreCase
description: En savoir plus sur la fonction notEqualWithIgnoreCase
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

---


# notEqualWithIgnoreCase {#notEqualWithIgnoreCase}

Vérifiez si la première chaîne d’arguments avec la seconde chaîne d’arguments est différente, en ignorant les considérations de casse.

## Catégorie

Chaîne

## Syntaxe de la fonction

`notEqualWithIgnoreCase(<parameters>)`

## Paramètres

* string

## Signature et type renvoyé

`notEqualWithIgnoreCase(<string>,<string>)`

Renvoie une valeur booléenne.

## Exemple 

`notEqualWithIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad"))`
