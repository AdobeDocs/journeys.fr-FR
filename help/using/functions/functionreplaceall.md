---
title: replaceAll
description: En savoir plus sur la fonction replaceAll
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


# replaceAll {#replaceAll}

Remplace toutes les occurrences correspondant à la chaîne cible par la chaîne de remplacement dans la chaîne de base.

Le remplacement s’effectue du début de la chaîne à la fin, par exemple, le remplacement de &quot;aa&quot; par &quot;b&quot; dans la chaîne &quot;aaa&quot; entraînera &quot;ba&quot; plutôt que &quot;ab&quot;.

## Catégorie

Chaîne

## Syntaxe de la fonction

`replaceAll(<parameters>)`

## Paramètres

| Paramètre | Type |
|-----------|--------------|
| base | string |
| cible | string |
| remplacement | string |

## Signature et type renvoyé

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

Renvoie une chaîne.

## Exemple 

`replaceAll("Hello World", "l", "x")`

Renvoie &quot;Hexxo Worxd&quot;.
