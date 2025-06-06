---
product: adobe campaign
title: Champs d'exécution d'action des événements journeyStep
description: Champs d'exécution d'action des événements journeyStep
feature: Journeys
role: User
level: Intermediate
exl-id: 9af66037-63d7-41a8-86d1-b03c655dfb82
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '367'
ht-degree: 100%

---

# Champs d&#39;exécution d&#39;action des événements journeyStep {#sharing-execution-fields}


>[!CAUTION]
>
>**Vous recherchez Adobe Journey Optimizer** ? Cliquez [ici](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/ajo-home){target="_blank"} pour consulter la documentation de Journey Optimizer.
>
>
>_Cette documentation se rapporte aux anciens contenus de Journey Orchestration qui ont été remplacés par Journey Optimizer. Pour toute question concernant votre accès à Journey Orchestration ou Journey Optimizer, contactez votre équipe en charge des comptes._


Ce mixin sera partagé par les éléments journeyStepEvent et journeyStepProfileEvent.

Si l’étape comporte une action à traiter, ces champs sont ajoutés à la payload de l’événement.

## actionID

ID de l’action en cours d’exécution.

Type : chaîne

## actionName

Nom de l’action Si aucun nom n’a été défini, stepName est exécuté.

Type : chaîne

## actionType

Type de l’action.

Type : chaîne

## actionParameterized

Indique si l’action est paramétrée ou non.

Type : booléen

## actionExecutionTime

Durée (en millisecondes) d’exécution d’une action en cours.

Type : long

## actionExecutionError

Type d’erreur se produisant lors de l’appel de l’action.

Type : chaîne

Valeurs :
* http
* capping
* timeout
* error

## actionExecutionErrorCode

Code d’erreur d’exécution d’action. Présent si l’erreur comporte un code, par exemple HTTP.

Type : chaîne

## actionExecutionOriginError

Un dépassement de délai peut se produire dans deux cas :

* Lors de la première tentative d’exécution d’une action. Dans ce cas, l’exécution n’est pas terminée, il n’y a donc pas d’erreur associée.
* Lors d’une nouvelle tentative : dans ce cas, le code actionExecOrigError/actionExecOrigErrorCode décrit l’erreur rencontrée lors de la tentative, et avant la nouvelle tentative.

Par exemple, un e-mail est envoyé et une erreur HTTP 500 est renvoyée lors de la première tentative. La récupération est de nouveau tentée, mais la durée des deux tentatives excède le délai d’attente. L’exécution de l’action est ensuite balisée pour indiquer un dépassement de délai. La partie action se présente comme suit :

```
    ...
    "actionId": "myActionId",
    "actionName": "My mail sending",
    "actionType": "acsRestAction",
    "actionParameterized": true,
    "actionExecError": "timedout",
    "actionExecOrigError": "http",
    "actionExecOrigErrorCode": "500"
```

Type : chaîne

## actionExecutionOriginCode

Code d’erreur d’actionExecOrigError.

Type : chaîne

## actionBusinessType

Indique le type d’action.

Valeurs :

* builtin
* ACS E-mail
* ACS SMS
* ACS Push
* client ou cliente
* Epsilon
* ...

Type : chaîne

## deliveryJobID

Cette section décrit l’ID de traitement de diffusion pour le parcours par lot.

Type : chaîne

## batchDeliveryID

Cette section décrit l’ID de diffusion pour le parcours par lot.

Type : chaîne

## fromSegmentTrigger

Cette section décrit si le parcours par lot est déclenché à partir du segment d’audience.

Type : booléen

## actionSchedulerCount

Nombre de demandes de notification de Planificateur envoyées au service Planificateur au cours du traitement de l’étape.

Type : long
