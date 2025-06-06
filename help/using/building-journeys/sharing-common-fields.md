---
product: adobe campaign
title: Champs communs des événements journeysteps
description: Champs communs des événements journeysteps
feature: Journeys
role: User
level: Intermediate
exl-id: 5cf8e6b5-2162-4aa3-b071-96ede31948e6
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '627'
ht-degree: 100%

---

# Champs communs des événements journeysteps {#sharing-common-fields}


>[!CAUTION]
>
>**Vous recherchez Adobe Journey Optimizer** ? Cliquez [ici](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/ajo-home){target="_blank"} pour consulter la documentation de Journey Optimizer.
>
>
>_Cette documentation se rapporte aux anciens contenus de Journey Orchestration qui ont été remplacés par Journey Optimizer. Pour toute question concernant votre accès à Journey Orchestration ou Journey Optimizer, contactez votre équipe en charge des comptes._


Ce mixin sera partagé par les variables journeyStepEvent et journeyStepProfileEvent.

Il s’agit des champs XDM communs que [!DNL Journey Orchestration] envoie à Adobe Experience Platform. Des champs communs seront envoyés pour chaque étape traitée dans un parcours. Des champs plus spécifiques sont utilisés pour les actions et enrichissements personnalisés.

Certains de ces champs ne sont disponibles que dans des modèles de traitement spécifiques (exécution d’action, récupération de données, etc.) afin de limiter la taille des événements.

## entrance

Indique si l’utilisateur est entré dans le parcours. S’il n’est pas présent, nous supposons que la valeur est false.

Type : booléen

Valeurs : Vrai/Faux

## reentrance

Indique si l’utilisateur est entré de nouveau dans le parcours avec la même instance. S’il n’est pas présent, nous supposons que la valeur est false.

Type : booléen

Valeurs : Vrai/Faux

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

Identifiant de la version du parcours. Cet identifiant représente la référence d’identité du parcours, dans le cas du journeyStepEvent.

Type : Chaîne

## journeyVersionName

Nom de la version du parcours.

Type : Chaîne

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

Type : Chaîne
