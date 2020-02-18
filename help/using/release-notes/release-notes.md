---
title: Notes de mise à jour
description: En savoir plus sur les notes de mise à jour
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
source-git-commit: 8023d7780d43f1de4447c63568f641ce204722c7

---


# Notes de mise à jour {#release-notes}

Cette page répertorie toutes les nouvelles fonctionnalités et améliorations de Journey Orchestration.
Vous pouvez également consulter les [mises à jour de la documentation](../release-notes/documentation-updates.md).

## Version du 1er trimestre - février 2019 {#q1-release---february-2019}

**Gestion du fuseau horaire**

Les fuseaux horaires sont maintenant gérés au niveau du voyage. Deux paramètres ont été ajoutés aux propriétés de voyage :

* La liste **déroulante Fuseau** de temps vous permet de sélectionner un fuseau horaire spécifique. Par défaut, le fuseau horaire du navigateur est utilisé.

* La case à cocher Fuseau horaire **du** profil vous permet d’utiliser le fuseau horaire Profil de la plateforme d’expérience de la personne qui entre dans le voyage, le cas échéant. Dans le cas contraire, le fuseau horaire défini dans la liste déroulante sera utilisé. Cette fonctionnalité n’est pas compatible avec les voyages sans espace de noms.

**Aide contextuelle**

Une fonction d’aide contextuelle est désormais disponible dans les différents écrans d’orchestration du voyage. Vous pouvez ainsi accéder directement et en un seul clic à la documentation relative à la fonctionnalité en cours d&#39;utilisation.

Pour afficher l’aide contextuelle, cliquez sur l’icône &quot;i&quot; dans le coin supérieur droit de l’écran.

Pour l’instant, cette fonctionnalité est disponible dans les écrans de liste Accueil, Sources de données, Evénements et Actions.

**Autres changements**

* En mode test, un nouveau paramètre vous permet de définir l’intervalle de temps.  les activités d’attente peuvent durer. Vous pouvez ainsi accéder rapidement aux résultats du test.

* En mode test, vous pouvez désormais déclencher tous les événements du voyage.


* un nouveau paramètre vous permet de définir l’attribut d’heure.  les activités d’attente peuvent durer. Vous pouvez ainsi accéder rapidement aux résultats du test.

* L&#39;orchestration des voyages est désormais disponible dans la zone EMEA.

* Nouvelle icône de la palette pour afficher ou non les éléments indisponibles. sans espace de noms. par défaut.

* trame, déconnexion, petite icone, qui dit noeud déconnecté.

* raccourci C ttes les listes

* interface utilisateur de la palette, résultats de recherche icone de

* Pouvoir capper les appelle a des APIS externes (sources de données ou actions). n&#39;accepté que 500 appels par seconde, marque elle européenne un plafonnement de 500 appels qui évite de surchargeur système de fidélité des niveaux

* journaux du journal de test. Avant status = erreur. quand sur des systèmes de pomme. Possibilityé de voir code erreur qu&#39;à renvoyé le système. -> ds un test en cas d&#39;erreur, niveaux système, code d&#39;erreur, réponse d&#39;erreur.

* fin du voyage de suppression

* voyage : version 1 il te met à jour si

1er mars.


## Version GA - Décembre 2019 {#ga-release---december-2019}

Journey Orchestration est maintenant disponible en version GA (disponibilité générale).

Créez des cas pratiques d’orchestration en temps réel à l’aide de données contextuelles stockées dans des événements ou des sources de données.

Journey Orchestration permet une orchestration en temps réel et s’appuie sur les données contextuelles issues d’événements, les informations provenant d’Adobe Experience Platform ou les données issues de services d’API tiers. L’application détermine, dans les flux à plusieurs étapes appelés parcours, les meilleures actions spécifiques au consommateur, en fonction de son profil et de ses comportements. Elles consistent à conjuguer une synchronisation optimale et un type d’action, comme l’envoi d’une notification push au consommateur à l’aide des fonctionnalités de messages transactionnels d’Adobe Campaign Standard (nécessite Adobe Campaign Standard), ou d’une notification d’un système tiers. Ces décisions sont prises en fonction de scores Sensei et de règles.

[En savoir plus](../action/working-with-adobe-campaign.md) sur Journey Orchestration.

Ressources supplémentaires :

* [Tutoriels](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [Communauté](https://www.adobe.com/go/journeyorchestrationcommunity)