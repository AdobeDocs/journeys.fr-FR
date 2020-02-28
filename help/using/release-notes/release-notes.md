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
source-git-commit: 73f1a503ea2c8b3494460c666a05078ed914e58b

---


# Notes de mise à jour {#release-notes}

Cette page répertorie toutes les nouvelles fonctionnalités et améliorations de Journey Orchestration.
Vous pouvez également consulter les [mises à jour de la documentation](../release-notes/documentation-updates.md).

## Version du 1er trimestre - Mars 2020 {#q1-release---march-2020}

**Nouveautés**

<table>
<thead>
<tr>
<th><strong>Améliorations du mode de test</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Les améliorations suivantes ont été apportées au mode test :</p>
<ul>
<li>Lorsqu’un voyage utilise plusieurs événements, vous pouvez désormais les déclencher individuellement dans une liste déroulante, dans l’écran de configuration <strong>de l’</strong> événement du mode test. <a href="../building-journeys/testing-the-journey.md#firing_events">En savoir plus</a></p></li>
<li><p>Lorsqu’une ou plusieurs activités <strong>d’attente</strong> sont utilisées dans un voyage, vous pouvez maintenant définir le temps de fin de chacune de ces activités en mode test. La durée par défaut est de 10 secondes. Vous pouvez le modifier à l’aide du paramètre <strong>Durée d’attente dans le paramètre test</strong> , dans le coin inférieur gauche. <a href="../building-journeys/testing-the-journey.md">En savoir plus</a></p><img src="../assets/rn-test.png"/>
</li>
<li>Dans les journaux <strong>de</strong>test, en cas d’erreur lors de l’appel d’un système tiers (source de données ou action), le code d’erreur et la réponse à l’erreur s’affichent désormais. <a href="../building-journeys/testing-the-journey.md#viewing_logs">En savoir plus</a>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Gestion centralisée des fuseaux horaires</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>La gestion du fuseau horaire est désormais centralisée dans le panneau des propriétés du voyage. Deux paramètres ont été ajoutés aux propriétés de voyage :</p>
<img src="../assets/rn-timezone.png"/>
<ul>
<li>La liste <strong>déroulante Fuseau</strong> horaire vous permet de sélectionner un fuseau horaire spécifique. Par défaut, le fuseau horaire du navigateur est utilisé.</li>
<li>La case à cocher Fuseau horaire <strong>du</strong> profil vous permet d’utiliser le fuseau horaire Profil de la plateforme d’expérience de la personne qui entre dans le voyage, le cas échéant. Dans le cas contraire, le fuseau horaire défini dans la liste déroulante est utilisé. Cette fonctionnalité n’est pas compatible avec les voyages utilisant des événements qui n’ont pas d’espace de noms.</li>
</ul>
<p>Pour plus d’informations, reportez-vous aux sections <a href="../building-journeys/changing-properties.md#timezone">Modification des propriétés</a> et gestion <a href="../building-journeys/timezone-management.md">du</a> fuseau horaire.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Améliorations du concepteur de voyage</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>La <strong>palette</strong>Voyage, sur le côté gauche du concepteur du voyage, a été améliorée :</p>
<ul>
<li>Une nouvelle icône, en regard de la barre **Recherche**, vous permet de masquer ou d’afficher les éléments indisponibles dans la palette, par exemple les événements qui utilisent un espace de noms différent de ceux utilisés dans votre parcours. Par défaut, les éléments non disponibles sont masqués.</li>
<li>Lors de l’utilisation du champ <strong>Rechercher</strong> , le nombre de résultats pour chaque catégorie d’activité de canevas est maintenant affiché.</li>
<li>La navigation entre les différentes catégories d’activités a été améliorée.</li>
</ul>
<p>Dans le concepteur du voyage, vous pouvez désormais vérifier que vous accédez à la dernière version du voyage. Ces informations s’affichent en regard du numéro de version.</p>
<p>Dans le <strong>canevas</strong>de voyage, lorsque deux activités sont déconnectées, un message d’avertissement s’affiche.</p>
<img src="../assets/rn-canvas.png"/>
<p>Pour plus d'informations, consultez la <a href="../building-journeys/using-the-journey-designer.md">documentation détaillée</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Aide contextuelle</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Une aide contextuelle est désormais disponible dans les différents écrans de la liste Orchestration du voyage (voyages, événements, actions et sources de données). Vous pouvez ainsi afficher une description rapide de la fonctionnalité actuelle et accéder aux articles et vidéos connexes.</p>
<p>Pour afficher l’aide contextuelle, cliquez sur l’ <img src="../assets/icon-context.png"/> icône dans le coin supérieur droit de l’écran. </p>
<img src="../assets/rn-context.png"/>
</td>
</tr>
</tbody>
</table>

**Autres améliorations**

* Outre les Etats-Unis, Journeys Orchestration est désormais disponible dans **EMEA**. La demande et la documentation sont disponibles en français et en allemand.

* Experience League est désormais intégrée dans le produit. Cela simplifie l’accès au contenu associé et vous permet de tirer le meilleur parti d’Experience Cloud. Vous pouvez accéder directement à la documentation de l’orchestration de Journey en bas de l’onglet Aide. De plus, cliquez sur Aide > Commentaires pour signaler des problèmes ou partager vos idées avec Adobe.

* Le raccourci clavier **C** , qui vous permet de créer un élément, est désormais disponible dans tous les écrans de liste : voyages, sources de données, actions et événements. [En savoir plus](../about/user-interface.md#section_ksq_zr1_ffb)

* Vous pouvez désormais **supprimer** les voyages interrompus. Les rapports associés à ces voyages supprimés ne seront pas disponibles.

* Lorsque vous parcourez les champs **de plateforme de** données (format XDM), le nom d’affichage s’affiche en plus du nom du champ. Ces informations sont récupérées à partir de la définition de schéma dans le modèle de données d’expérience. Lorsqu’il est disponible, le nom d’affichage alternatif s’affiche. Cette description conviviale, particulièrement utile dans le cas des champs d’eVar, vous permet d’identifier vos champs plus facilement. [En savoir plus](../about/user-interface.md#friendly-names-display)

## Version GA - Décembre 2019 {#ga-release---december-2019}

Journey Orchestration est maintenant disponible en version GA (disponibilité générale).

Créez des cas d’utilisation d’orchestration en temps réel à l’aide de données contextuelles stockées dans des événements ou des sources de données.

Journey Orchestration permet une orchestration en temps réel et s’appuie sur les données contextuelles issues d’événements, les informations provenant d’Adobe Experience Platform ou les données issues de services d’API tiers. L’application détermine, dans les flux à plusieurs étapes appelés parcours, les meilleures actions spécifiques au consommateur, en fonction de son profil et de ses comportements. Elles consistent à conjuguer une synchronisation optimale et un type d’action, comme l’envoi d’une notification push au consommateur à l’aide des fonctionnalités de messages transactionnels d’Adobe Campaign Standard (nécessite Adobe Campaign Standard), ou d’une notification d’un système tiers. Ces décisions sont prises en fonction de scores Sensei et de règles.

[En savoir plus](../action/working-with-adobe-campaign.md) sur Journey Orchestration.

Ressources supplémentaires :

* [Tutoriels](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [Communauté](https://www.adobe.com/go/journeyorchestrationcommunity)