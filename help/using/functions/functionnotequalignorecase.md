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
translation-type: ht
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: ht
source-wordcount: '37'
ht-degree: 100%

---


# notEqualWithIgnoreCase {#notEqualWithIgnoreCase}

Vérifie si la chaîne du premier argument est différente de la chaîne du deuxième argument, en ignorant les considérations de casse.

## Catégorie

Chaîne

## Syntaxe de la fonction

`notEqualWithIgnoreCase(<parameters>)`

## Paramètres

* chaîne

## Signature et type renvoyé

`notEqualWithIgnoreCase(<string>,<string>)`

Renvoie une valeur booléenne.

## Exemple

`notEqualWithIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad"))`
