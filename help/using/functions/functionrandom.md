---
product: adobe campaign
solution: Journey Orchestration
title: random
description: En savoir plus sur la fonction random
translation-type: ht
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: ht
source-wordcount: '51'
ht-degree: 100%

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
