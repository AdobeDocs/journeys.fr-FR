---
product: adobe campaign
solution: Journey Orchestration
title: replaceAll
description: En savoir plus sur la fonction replaceAll
translation-type: ht
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: ht
source-wordcount: '75'
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
| cible | chaîne |
| remplacement | chaîne |

## Signature et type renvoyé

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

Renvoie une chaîne.

## Exemple

`replaceAll("Hello World", "l", "x")`

Renvoie « Hexxo Worxd ».
