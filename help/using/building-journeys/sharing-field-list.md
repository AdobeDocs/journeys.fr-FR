---
title: Liste des champs d’événement d’étape
description: Liste des champs d’événement d’étape
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 177b4a97-c757-40ca-a190-fbd88169e5e2
source-git-commit: 4291dfc91c2fb29d294416ceed022ee00842c870
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 32%

---

# Liste des champs d’événement d’étape {#sharing-field-list}

Les champs d’événement d’étape sont organisés par catégorie.

* Champs d’informations de débogage
* Champs du parcours
* Champs de profil
* Champs d’événement de service

## debugInfo

| Nom du champ | Type | Description |
|---|---|------------|
| requestId | Chaîne | ID de requête utilisé par Journey Orchestration pour suivre le flux d’une requête. |

## parcours

Ce groupe de champs est utilisé dans le schéma du parcours (en relation avec journeyStepEvent). Il contient les champs suivant :

| Nom du champ | Type | Description |
|---|---|------------|
| Identifiant | Chaîne | Identifiant du Parcours donné |
| VersionID | Chaîne | Identifiant de la version du parcours. Cet identifiant représente l’identité d’un parcours |
| name | Chaîne | Nom du parcours |
| description | Chaîne | Description du parcours |
| version | Chaîne | version, représentée sous la forme `major`.`minor` |

## profile

Ce groupe de champs est spécifique à journeyStepEvent : cet événement est en relation avec parcours et ne dispose pas de identityMap décrivant l’identité du profil, le cas échéant.

Pour un événement journeyStepEvent, nous devons également ajouter des champs liés à l’identité :

| Nom du champ | Type | Description |
|---|---|------------|
| Identifiant | Chaîne | L’identifiant de profil identifie le profil envoyé/utilisé dans un parcours. Par exemple : foo@adobe.com. |
| espace de noms | Chaîne | Ce champ décrit l’espace de noms référencé par le profil utilisé dans le Parcours. Par exemple : Email, ECID |

## serviceEvents

Ce mixin contient tous les champs correspondant à une tâche d’exportation de profil.

| Nom du champ | Type | Description |
|---|---|------------|
| Identifiant | Chaîne | L’identifiant de la tâche d’exportation de segments déclenchée |
| status | Chaîne | État de la tâche d’exportation de segments : en file d’attente, commencé, terminé |
| exportCountTotal | Entier | Valeur maximale possible de la tâche d’exportation de segments |
| exportCountRealized | Entier | Le nombre réel de segments exportés par la tâche |
| exportCountFailed | Entier | Le nombre de segments ayant échoué lors de l’exportation via la tâche |
| exportSegmentID | Chaîne | Identifiant du segment à exporter |
| eventType | Chaîne | Type d’événement indiquant s’il s’agit d’un événement info d’erreur : Informations, erreur |
| eventCode | Chaîne | Le code d’erreur indiquant la raison de eventType correspondant |

## stepEvents

Cette catégorie contient les champs d’événement d’étape d’origine. Reportez-vous à cette [section](../building-journeys/sharing-legacy-fields.md).
