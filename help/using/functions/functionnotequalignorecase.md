---
product: adobe campaign
solution: Journey Orchestration
title: notEqualWithIgnoreCase
description: En savoir plus sur la fonction notEqualWithIgnoreCase
feature: Parcours
role: Ingénieur de données
level: Expérience
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 92%

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
