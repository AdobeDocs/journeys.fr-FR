---
product: adobe campaign
solution: Journey Orchestration
title: notEqualWithIgnoreCase
description: En savoir plus sur la fonction notEqualWithIgnoreCase
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '38'
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
