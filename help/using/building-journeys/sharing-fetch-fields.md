---
title: Champs de récupération des données des événements travelStep
description: Champs de récupération des données des événements travelStep
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
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 0%

---


# Champs de récupération des données des événements travelStep {#sharing-fetch-fields}

Ce mixin sera partagé par les variables voyageStepEvent et voyageStepProfileEvent.

Au cours d’un traitement par étape, aucune donnée ne peut être récupérée sur les groupes de champs.

## fetchTotalTime

Durée totale de la récupération des données pendant des millis pendant le traitement de l’étape.

Type : long

## fetchTypeInError

Définit si la récupération par erreur se trouve sur la plateforme ou sur une source de données personnalisée.

Type : string

Valeurs:
* aep
* personnalisé

## fetchError

Type d’erreur survenant lors du traitement de la récupération des données.

Type : string

Valeurs:
* http
* recouvrement
* timedout
* error

## fetchErrorCode

Code de l&#39;erreur de récupération. Présente si l’erreur comporte un code, par exemple HTTP. Par exemple, si actionExecError est http, le code 404 représente l’erreur HTTP 404.

Type : string

## fetchOriginError

Un dépassement de délai peut se produire dans deux cas :

* lors de la première tentative, l&#39;action est exécutée. Dans ce cas, l’exécution n’est pas terminée, il n’y a donc pas d’erreur sous-jacente.
* sur une nouvelle tentative : dans ce cas, actionExecOrigError/actionExecOrigErrorCode décrit l&#39;erreur rencontrée lors de la tentative avant la nouvelle tentative.

Par exemple, les données sont extraites du service de Profil unifié et une erreur HTTP 500 est renvoyée lors de la première tentative. La récupération est refaite, mais la durée des deux tentatives dépasse le délai d&#39;attente. Ensuite, l’exécution de l’action est balisée en tant que délai d’expiration. La partie action se présente comme suit :

```
    ...
    "fetchTypeInError": "aep",
    "fieldgroupIdInError": "MyProfileFieldgroup",
    "fetchError": "timedout",
    "fetchOrigError": "http",
    "fetchOrigErrorCode": "500"
```

Type : string

## fetchOriginErrorCode

Le code d&#39;erreur fourni par le système [!DNL Journey Orchestration] interroge. Par exemple, il peut s’agir de 404, 500, etc.

Type : string

## fetchCount

Combien de fois les données sont extraites, quel que soit le type de source.

Type : long

## fetchPlatformTotalTime

Durée totale de récupération des données de la plateforme de données en millions. Remarque : cette durée est calculée à partir du moment où le moteur envoie le événement d&#39;enrichissement au service d&#39;enrichissement et reçoit la réponse.

Type : long

## fetchPlatformCount

Combien de fois les données sont extraites de la plate-forme.

Type : long

## fetchCustomTotalTime

Durée de récupération des données personnalisées en millions. Remarque : cette durée est calculée à partir du moment où le moteur envoie le événement d&#39;enrichissement au service d&#39;enrichissement et reçoit la réponse

Type : long

## fetchCustomCount

Nombre de fois où les données personnalisées sont extraites de systèmes externes.

Type : long
