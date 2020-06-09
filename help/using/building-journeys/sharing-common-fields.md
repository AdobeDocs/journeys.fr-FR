---
title: cheminement pas événements champs communs
description: cheminement pas événements champs communs
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
source-wordcount: '581'
ht-degree: 0%

---


# cheminement pas événements champs communs {#sharing-common-fields}

Ce mixin sera partagé par les variables voyageStepEvent et voyageStepProfileEvent.

Il s’agit des champs XDM courants qui [!DNL Journey Orchestration] sont envoyés à la plateforme de données Adobe. Des champs communs seront envoyés pour chaque étape traitée dans un parcours. Des champs plus spécifiques sont utilisés pour les actions et enrichissements personnalisés.

Certains de ces champs ne sont disponibles que dans des modèles de traitement spécifiques (exécution d’action, récupération de données, etc.) afin de limiter la taille des événements.

## entrée

Indique si l’utilisateur est entré dans le voyage. Si elle n’est pas présente, nous supposons que la valeur est false.

Type : booléen

Valeurs : true/false

## réadmission

Indique si l’utilisateur est revenu au voyage avec la même instance. Si elle n’est pas présente, nous supposons que la valeur est false.

Type : booléen

Valeurs : true/false

## instanceEnded

Indique si l’instance s’est terminée (avec succès ou non).

Type : booléen

## eventID

ID de Événement dans le traitement, pour le traitement de l’étape. Si le événement est externe, la valeur est son eventId. Si le événement est interne, la valeur est l’eventId interne (tel que scheduleNotificationReceived, executeAction, etc.).

Type : string

## nodeID

ID de noeud client (à partir du canevas).

Type : string

## stepID

Identifiant unique de l’étape en cours de traitement.

Type : string

## stepName

Nom de l’étape en cours de traitement.

Type : string

## stepType

Type de l’étape.

Type : string

Valeurs possibles :

* Condition
* Action
* Planificateur
* Retardateur

## stepStatus

Statut de l’étape, représentant l’état de l’étape, une fois son traitement terminé (et le événement de l’étape déclenché).

Type : string

L’état peut être :

* terminé : l&#39;étape n&#39;a aucune transition et son traitement s&#39;est terminé avec succès.
* erreur : le traitement de l&#39;étape a généré une erreur.
* transitions : l&#39;étape attend qu&#39;un événement transition à une autre étape.
* mis en cache : l&#39;étape a échoué en cas d&#39;erreur de plafonnement, surmontée pendant une action ou un enrichissement.
* timedout : l&#39;étape a échoué en cas d&#39;erreur de dépassement de délai, déclenchée lors d&#39;une action ou d&#39;un enrichissement.
* instanceTimedout : l’étape a arrêté son traitement, car l’instance a atteint son délai d’expiration.

## travelID

ID du voyage.

Type : string

## travelVersionID

ID de la version du voyage. Cet id représente la référence d&#39;identité du voyage, dans le cas de voyageStepEvent.

Type : string

## travelVersionName

Nom de la version du voyage.

Type : string

## travelVersion

Version du voyage.

Type : string

## instanceID

ID interne de l&#39;instance de voyage.

Type : string

## externalKey

Clé externe extraite du événement pour le traiter.

Type : string

## parentStepID

ID d’étape du parent de l’étape en cours de traitement dans l’instance.

Type : string

## parentStepName

Nom de l’étape parent de l’étape en cours.

Type : string

## parentTransitionID

Identifiant de la transition qui a conduit l&#39;instance à l&#39;étape de traitement.

Type : string

## parentTransitionName

Nom de la transition qui a conduit l&#39;instance à l&#39;étape de traitement.

Type : string

## inTest

Indique si ce voyage est en mode test ou non.

Type : booléen

## processingTime

Durée totale, en millisecondes, entre l’entrée de l’étape d’instance et la fin du traitement.

Type : long

## instanceType

Indique le type d’instance, s’il s’agit d’un lot ou d’une unité.

Type : string

Valeurs : lot/unitaire

## périorenceIndex

Indice de la périodicité si le parcours est batch et récurrent (la première exécution a périorenceIndex = 1).

Type : long

## isBatchToUninary

Indique si cette instance unitaire a été déclenchée à partir d’une instance de lot.

Type : booléen

## batchExternalKey

Clé externe pour le événement batch.

Type : string

## batchInstanceID

il s’agit de l’ID d’instance de lot.

Type : string

## batchUnitBranchID

si l&#39;instance a été déclenchée à partir d&#39;une instance de lot, ID de branche unitaire.

Type : string
