---
product: adobe campaign
solution: Journey Orchestration
title: Propriétés du parcours
description: En savoir plus sur les propriétés du parcours
translation-type: tm+mt
source-git-commit: 1fd02fcc2a535046cfbcdb5d1c52850ee93370af
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 0%

---


# Journey properties {#journey-properties}

Dans l’éditeur d’expressions avancé, vous trouverez la catégorie Propriétés **du** voyage, sous les catégories de événement et de source de données. Cette catégorie contient des domaines techniques liés au parcours d&#39;un profil donné. Il s&#39;agit des informations récupérées par le système à partir de voyages en direct, telles que l&#39;ID de voyage ou les erreurs spécifiques rencontrées.

![](../assets/journey-properties.png)

Vous trouverez, par exemple, des informations sur :

* version du voyage : guide de voyage, guide de voyage, guide de voyage, guide d&#39;instance, etc.
* erreurs : extraction de données, exécution d&#39;actions, etc.
* étape en cours, dernière étape en cours, etc.
* profils ignorés

Vous pouvez utiliser ces champs pour créer des expressions. Pendant l&#39;exécution du voyage, les valeurs seront récupérées directement du voyage.

Voici quelques exemples d’utilisation :

* **Enregistrer les profils** ignorés : vous pouvez envoyer tous les profils exclus d’un message par une règle de plafonnement à un système tiers à des fins de journalisation. Pour ce faire, vous configurez un chemin en cas de dépassement de délai et d’erreur et ajoutez une condition pour filtrer selon un type d’erreur spécifique, par exemple : &quot;Ignorer les gens en plafonnant la règle&quot;. Vous pouvez ensuite pousser les profils ignorés vers un système tiers par le biais d’une action personnalisée.

* **Envoi d’alertes Push en cas d’erreur**: vous pouvez envoyer une notification à un système tiers chaque fois qu’une erreur survient sur un message. Pour ce faire, vous configurez un chemin en cas d’erreur, ajoutez une condition et une action personnalisée. Vous pouvez envoyer une notification sur un canal Slack, par exemple, avec la description de l’erreur rencontrée.

* **Affiner les erreurs dans le rapports** : au lieu d&#39;avoir un seul chemin pour les messages en erreur, vous pouvez définir une condition par type d&#39;erreur. Cela vous permettra d&#39;affiner le rapports et la vue de toutes les données de types d&#39;erreur.

## Liste de champs {#journey-properties-fields}

|Catégorie|Nom du champ|Libellé|Description|
|-|-|-|—|
|Version du voyage|voyageUID|Identifiant du voyage| |
| |voyageVersionUID|Identificateur de version du voyage| |
| |cheminVersionName|Nom de la version du voyage| |
| |travelVersionDescription|Description de la version du voyage| |
| |travelVersion|Journey Version| |
|Instance de parcours|instanceUID|Identifiant d&#39;instance de parcours|ID de l&#39;instance|
| |externeKey|Clé externe|Identifiant individuel déclenchant le voyage|
|Identité|IdProfil|Identifiant d&#39;identité du Profil|Identifiant du profil du voyage|
| |espace de nommage|Profil Identité Espace de nommage|Espace de nommage du profil dans le parcours (exemple : ECID)|
|Noeud actuel|currentNodeId|Identifiant de noeud actuel|Identifiant de l&#39;activité actuelle (noeud)|
| |currentNodeName|Nom du noeud actuel|Nom de l&#39;activité actuelle (noeud)|
|Noeud précédent|previousNodeId|Identificateur de noeud précédent|Identifiant de l&#39;activité précédente (noeud)|
| |previousNodeName|Previous Node Name|Name of the previous activité (node)|
|Erreurs|lastNodeUIDInError|Last Node Identifier in Error|Identifier de la dernière activité (noeud) en erreur|
| |lastNodeNameInError|Nom du noeud dans Erreur|Nom de la dernière activité (noeud) en erreur|
| |lastNodeTypeInError|Dernier type de noeud dans Error|Type d&#39;erreur de la dernière activité (noeud) en erreur. Types possibles :<ul><li>Événements : Événements, Réactions, SQ (exemple : Qualification de segment)</li><li>Contrôle de flux : Fin, condition, attendre</li><li>Actions : Actions ACS, vidage, action personnalisée</li></ul>|
| |lastErrorCode|Last Error Code|Code d&#39;erreur de la dernière activité (noeud) en erreur. Erreurs possibles : <ul><li>Codes d’erreur HTTP</li><li>mis en cache</li><li>timedOut</li><li>error (exemple : par défaut en cas d’erreur inattendue. Ne devrait pas/extrêmement rarement se produire)</li></ul>|
| |lastExecutedActionErrorCode|Dernière action exécutée Code d&#39;erreur|Code d&#39;erreur de la dernière action en erreur |
| |lastDataFetchErrorCode|Dernière récupération des données Code d&#39;erreur|Code d&#39;erreur de la dernière récupération des données à partir des sources de données|
|Time|lastActionExecutionElapsedTime|La dernière exécution de l&#39;action s&#39;est terminée|Le temps passé à exécuter la dernière action|
| |lastDataFetchElapsedTime|Dernière récupération de données temps écoulé|Temps passé à exécuter la dernière récupération de données à partir de sources de données|
