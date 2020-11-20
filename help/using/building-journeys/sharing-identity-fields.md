---
product: adobe campaign
solution: Journey Orchestration
title: Champs d’identité des événements journeyStep
description: Champs d’identité des événements journeyStep
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 100%

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