---
product: adobe campaign
solution: Journey Orchestration
title: Champs communs des événements journeysteps
description: Champs communs des événements journeysteps
translation-type: ht
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: ht
source-wordcount: '581'
ht-degree: 100%

---


# Champs communs des événements journeysteps {#sharing-common-fields}

Ce mixin sera partagé par les variables journeyStepEvent et journeyStepProfileEvent.

Il s’agit des champs XDM communs que [!DNL Journey Orchestration] envoie à Adobe Experience Platform. Des champs communs seront envoyés pour chaque étape traitée dans un parcours. Des champs plus spécifiques sont utilisés pour les actions et enrichissements personnalisés.

Certains de ces champs ne sont disponibles que dans des modèles de traitement spécifiques (exécution d’une action, récupération de données, etc.) pour limiter la taille des événements.

## entrance

Indique si l’utilisateur est entré dans le parcours. S’il n’est pas présent, nous supposons que la valeur est false.

Type : booléen

Valeurs : true/false

## reentrance

Indique si l’utilisateur est entré de nouveau dans le parcours avec la même instance. S’il n’est pas présent, nous supposons que la valeur est false.

Type : booléen

Valeurs : true/false

## instanceEnded

Indique si l’instance s’est terminée (avec succès ou non).

Type : booléen

## eventID

ID de l’événement traité, pour le traitement de l’étape. Si l’événement est externe, la valeur est son eventId. Si l’événement est interne, la valeur est l’eventId interne (tel que scheduledNotificationReceived, executedAction, etc.).

Type : chaîne

## nodeID

ID de nœud client (à partir de la zone de travail).

Type : chaîne

## stepID

Identifiant unique de l’étape en cours de traitement.

Type : chaîne

## stepName

Nom de l’étape en cours de traitement.

Type : chaîne

## stepType

Type de l’étape.

Type : chaîne

Valeurs possibles :

* Condition
* Action
* Planificateur
* Retardateur

## stepStatus

Statut de l’étape, représentant l’état de l’étape, une fois son traitement terminé (et l’événement de l’étape déclenché).

Type : chaîne

Le statut peut être :

* terminée : l’étape n’a aucune transition et son traitement s’est terminé avec succès.
* erreur : le traitement de l’étape a généré une erreur.
* transitions : l’étape attend qu’un événement effectue une transition vers une autre étape.
* limitée : l’étape a échoué avec une erreur de limitation survenue pendant une action ou un enrichissement.
* dépassement de délai : l’étape a échoué avec une erreur de dépassement de délai survenue pendant une action ou un enrichissement.
* instanceTimedout : l’étape a arrêté son traitement, car l’instance a atteint son délai d’expiration.

## journeyID

ID du parcours.

Type : chaîne

## journeyVersionID

ID de la version du parcours. Cet identifiant représente la référence d’identité du parcours, dans le cas du journeyStepEvent.

Type : chaîne

## journeyVersionName

Nom de la version du parcours.

Type : chaîne

## journeyVersion

Nom de la version du parcours.

Type : chaîne

## instanceID

ID interne de l’instance de parcours.

Type : chaîne

## externalKey

Clé externe extraite de l’événement pour le traiter.

Type : chaîne

## parentStepID

ID d’étape du parent de l’étape en cours de traitement dans l’instance.

Type : chaîne

## parentStepName

Nom de l’étape du parent de l’étape en cours.

Type : chaîne

## parentTransitionID

Identifiant de la transition qui a conduit l’instance à l’étape de traitement.

Type : chaîne

## parentTransitionName

Nom de la transition qui a conduit l’instance à l’étape de traitement.

Type : chaîne

## inTest

Indique si ce parcours est en mode test ou non.

Type : booléen

## processingTime

Durée totale, en millisecondes, entre l’entrée de l’étape d’instance et la fin du traitement.

Type : long

## instanceType

Indique le type d’instance, s’il s’agit d’un lot ou d’une unité.

Type : chaîne

Valeurs : batch/unitary

## recurrenceIndex

Indice de la récurrence si le parcours est &quot;batch&quot; et récurrent (pour la première exécution, recurrenceIndex = 1).

Type : long

## isBatchToUnitary

Indique si cette instance unitaire a été déclenchée à partir d’une instance de lot.

Type : booléen

## batchExternalKey

Clé externe pour un événement batch.

Type : chaîne

## batchInstanceID

Il s’agit de l’ID d’instance de lot.

Type : chaîne

## batchUnitaryBranchID

si l’instance a été déclenchée à partir d’une instance de lot, ID de branche unitaire.

Type : chaîne
