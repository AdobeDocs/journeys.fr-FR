---
title: random
description: En savoir plus sur la fonction random
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: ht
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608

---


# random {#random}

Génère un nombre aléatoire compris entre 0 et 1.

## Catégorie

Mathématique

## Syntaxe de la fonction

`random(<parameters>)`

## Signature et type renvoyé

`random()`

Renvoie une valeur décimale.

## Exemple

`#{MarltonReservation.statistics.successRatio, defaultValue : random() * 100}`

Explication : si le taux de succès n’a pas de valeur/contient une valeur « null », la valeur par défaut est appliquée et sera un nombre aléatoire compris entre 0 et 1 * 100 (donc de 0 à 100).
