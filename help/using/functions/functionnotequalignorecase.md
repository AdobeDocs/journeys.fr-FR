---
product: adobe campaign
solution: Journey Orchestration
title: notEqualWithIgnoreCase
description: En savoir plus sur la fonction notEqualWithIgnoreCase
translation-type: ht
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
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
