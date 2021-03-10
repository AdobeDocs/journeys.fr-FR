---
product: adobe campaign
solution: Journey Orchestration
title: Champs de récupération des données des événements journeyStep
description: Champs de récupération des données des événements journeyStep
feature: Parcours
role: Professionnel
level: Intermédiaire
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 99%

---


# Champs de récupération des données des événements journeyStep {#sharing-fetch-fields}

Ce mixin sera partagé par les variables journeyStepEvent et journeyStepProfileEvent.

Lors du traitement d’une étape, il est possible de récupérer un nombre quelconque de données dans les groupes de champs.

## fetchTotalTime

Laps de temps total, en millisecondes, consacré à la récupération des données lors du traitement d’une étape.

Type : long

## fetchTypeInError

Définit si la récupération en erreur se trouve sur Adobe Experience Platform ou sur une source de données personnalisée.

Type : chaîne

Valeurs :
* aep
* custom

## fetchError

Type d’erreur se produisant lors du traitement de la récupération des données.

Type : chaîne

Valeurs :
* http
* capping
* timedout
* error

## fetchErrorCode

Code de l’erreur de récupération. Présent si l’erreur comporte un code, par exemple HTTP. Par exemple, si actionExecError contient http, le code 404 représente l’erreur HTTP 404.

Type : chaîne

## fetchOriginError

Un dépassement de délai peut se produire dans deux cas :

* Lors de la première tentative d’exécution de l’action. Dans ce cas, l’exécution n’est pas terminée, il n’y a donc pas d’erreur associée.
* Lors d’une nouvelle tentative : dans ce cas, le code actionExecOrigError/actionExecOrigErrorCode décrit l’erreur rencontrée lors de la tentative, et avant la nouvelle tentative.

Par exemple, les données sont extraites du service Profil unifié et une erreur HTTP 500 est renvoyée lors de la première tentative. La récupération est de nouveau tentée, mais la durée des deux tentatives excède le délai d’attente. L’exécution de l’action est ensuite balisée pour indiquer un dépassement de délai. La partie action se présente comme suit :

```
    ...
    "fetchTypeInError": "aep",
    "fieldgroupIdInError": "MyProfileFieldgroup",
    "fetchError": "timedout",
    "fetchOrigError": "http",
    "fetchOrigErrorCode": "500"
```

Type : chaîne

## fetchOriginErrorCode

Code d’erreur fourni par le système interrogé par [!DNL Journey Orchestration]. Il peut s’agir par exemple d’un code 404, 500, etc.

Type : chaîne

## fetchCount

Nombre de récupérations de données, quel que soit le type de source.

Type : long

## fetchPlatformTotalTime

Laps de temps total en millisecondes consacré à la récupération des données sur Adobe Experience Platform. Remarque : ce laps de temps est calculé à partir du moment où le moteur envoie l’événement d’enrichissement au service d’enrichissement et reçoit la réponse.

Type : long

## fetchPlatformCount

Nombre de récupérations de données sur Adobe Experience Platform.

Type : long

## fetchCustomTotalTime

Laps de temps consacré à la récupération des données personnalisées en millisecondes. Remarque : ce laps de temps est calculé à partir du moment où le moteur envoie l’événement d’enrichissement au service d’enrichissement et reçoit la réponse

Type : long

## fetchCustomCount

Nombre de récupérations de données personnalisées depuis les systèmes externes.

Type : long
