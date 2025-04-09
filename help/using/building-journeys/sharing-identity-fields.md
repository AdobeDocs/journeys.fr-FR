---
product: adobe campaign
title: Champs d’identité des événements journeyStep
description: Champs d’identité des événements journeyStep
feature: Journeys
role: User
level: Intermediate
exl-id: 9c0ff38f-51dd-40bd-8c19-d142b9c23308
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 57%

---

# Champs d’identité des événements journeyStep {#sharing-identity-fields}


>[!CAUTION]
>
>**Vous recherchez Adobe Journey Optimizer** ? Cliquez [ici](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/ajo-home){target="_blank"} pour accéder à la documentation de Journey Optimizer.
>
>
>_Cette documentation se rapporte aux anciens contenus de Journey Orchestration qui ont été remplacés par Journey Optimizer. Pour toute question concernant votre accès à Journey Orchestration ou Journey Optimizer, veuillez contacter votre équipe de compte._


Ce mixin est spécifique à journeyStepEvent : cet événement est en relation avec le parcours, et ne dispose pas de l’identityMap décrivant l’identité du profil, le cas échéant.

Pour journeyStepEvent, nous devons également ajouter des champs liés à l’identité :

## profileID

Identifiant de profil

Type : Chaîne

## profileNamespace

Espace de noms de l’identifiant de profil

Type : Chaîne
