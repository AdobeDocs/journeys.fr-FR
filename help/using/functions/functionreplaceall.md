---
product: adobe campaign
title: replaceAll
description: En savoir plus sur la fonction replaceAll
feature: Journeys
role: Developer
level: Experienced
exl-id: d60059e5-6bf8-4a57-88a4-5323d5f0fa0b
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 100%
---
# replaceAll {#replaceAll}

Remplace toutes les occurrences correspondant à la chaîne cible par la chaîne de remplacement dans la chaîne de base.

Le remplacement s’effectue du début à la fin de la chaîne. Par exemple, le remplacement de « aa » par « b » dans la chaîne « aaa » donnera « ba » et non « ab ».

## Catégorie

Chaîne

## Syntaxe de la fonction

`replaceAll(<parameters>)`

## Paramètres

| Paramètre | Type |
|-----------|--------------|
| base | chaîne |
| cible | string (RegExp) |
| remplacement | chaîne |

## Signature et type renvoyé

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

Renvoie une chaîne.

## Exemple{#example}

`replaceAll("Hello World", "l", "x")`

Renvoie « Hexxo Worxd ».

Comme le paramètre cible est un RegExp, selon la chaîne que vous souhaitez remplacer, vous devrez peut-être ajouter une séquence d’échappement à certains caractères. Reportez-vous à l’exemple de [cette page](../functions/functionreplace.md#example_2).
