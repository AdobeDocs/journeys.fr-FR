---
title: Champs d’identité des événements journeyStep
description: Champs d’identité des événements journeyStep
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: ht
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: ht
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