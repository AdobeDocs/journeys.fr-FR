---
product: adobe campaign
solution: Journey Orchestration
title: Champs d’identité des événements journeyStep
description: Champs d’identité des événements journeyStep
feature: Parcours
role: Professionnel
level: Intermédiaire
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 96%

---


# Champs d’identité des événements journeyStep {#sharing-identity-fields}

Ce mixin est spécifique à journeyStepEvent : cet événement est en relation avec le parcours, et ne dispose pas de l’identityMap décrivant l’identité du profil, le cas échéant.

Pour un événement journeyStepEvent, nous devons également ajouter des champs liés à l’identité :

## profileID

Identifiant de profil

Type : chaîne

## profileNamespace

Espace de noms de l’identifiant de profil

Type : chaîne