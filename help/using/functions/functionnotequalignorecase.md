---
product: adobe campaign
title: notEqualIgnoreCase
description: En savoir plus sur la fonction notEqualIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 100%

---

# notEqualIgnoreCase {#notEqualIgnoreCase}

Vérifie si la chaîne du premier argument est différente de la chaîne du deuxième argument, en ignorant les considérations de casse.

## Catégorie

Chaîne

## Syntaxe de la fonction

`notEqualIgnoreCase(<parameters>)`

## Paramètres

* Chaîne

## Signature et type renvoyé

`notEqualIgnoreCase(<string>,<string>)`

Renvoie une valeur booléenne.

## Exemple

`notEqualIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad")`
