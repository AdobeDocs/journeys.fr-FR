---
title: L’interface utilisateur
description: En savoir plus sur l’interface utilisateur
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# User interface {#concept_rcq_lqt_52b}

>[!NOTE]
>
>Pour tirer le meilleur parti de Journey Orchestration, nous vous recommandons d’utiliser Chrome comme navigateur Internet.
>
>Cette documentation est fréquemment mise à jour pour refléter les modifications récentes du produit. Cependant, certaines captures d’écran peuvent légèrement différer de l’interface du produit.

## Découverte de l&#39;interface{#section_jsq_zr1_ffb}

Pour accéder à l’interface de Journey Orchestration, cliquez sur l’icône Sélecteur **[!UICONTROL d’]**application, en haut à droite. Cliquez ensuite sur**[!UICONTROL  Journey Orchestration]**, sur le côté droit, sous &quot;Experience Platform&quot;.

![](../assets/journey1.png)

Vous pouvez également accéder à l’orchestration du voyage à partir de la page d’accueil d’Experience Cloud, dans la section Accès **[!UICONTROL rapide]**.

![](../assets/journey1bis.png)

Les menus supérieurs vous permettent de naviguer parmi les différentes fonctionnalités de Journey Orchestration : **[!UICONTROL Accueil]**(voyages),**[!UICONTROL  Sources]**de données, **[!UICONTROL événements]**,**[!UICONTROL  actions.]**

![](../assets/journey2.png)

## Recherche et filtrage{#section_lgm_hpz_pgb}

Dans les listes **[!UICONTROL Accueil]**,**[!UICONTROL  Sources]**de données, **[!UICONTROL Evénements]**et**[!UICONTROL  Actions, une barre de recherche vous permet de rechercher un élément.]**

Pour accéder aux **[!UICONTROL filtres]**, cliquez sur l’icône de filtre en haut à gauche de la liste. Le menu Filtres vous permet de filtrer les éléments affichés selon différents critères. Vous pouvez choisir d’afficher uniquement les éléments d’un certain type ou état, ceux que vous avez créés ou ceux que vous avez modifiés au cours des 30 derniers jours.

Dans les listes Sources **[!UICONTROL de]**données,**[!UICONTROL  Evénements]** et **[!UICONTROL Actions]****, utilisez les filtresCréation pour filtrer la date de création et l’utilisateur. **Vous pouvez, par exemple, choisir d’afficher uniquement les événements que vous avez créés au cours des 30 derniers jours.

Dans la liste des parcours (sous **[!UICONTROL Accueil]**), outre les filtres****Création, vous pouvez également filtrer les parcours affichés en fonction de leur statut et de leur version (filtres ****État et version). Vous pouvez également choisir d’afficher uniquement les voyages qui utilisent un événement, un groupe de champs ou une action spécifique (filtres**[!UICONTROL  d’]** activité et filtres **[!UICONTROL de]**données). Les filtres**** Publication vous permettent de sélectionner une date de publication ou un utilisateur. Vous pouvez, par exemple, choisir d’afficher uniquement les dernières versions des voyages en direct publiées hier. Voir la section [](../building-journeys/using-the-journey-designer.md).

>[!NOTE]
>
>Notez que les colonnes affichées peuvent être personnalisées à l’aide du bouton de configuration en haut à droite des listes. La personnalisation est enregistrée pour chaque utilisateur.

![](../assets/journey74.png)

Dans les volets de configuration de la source de données et de l’action, le champ **[!UICONTROL Utilisé dans]**affiche le nombre de voyages qui utilisent cet événement, ce groupe de champs ou cette action spécifique. Vous pouvez cliquer sur le bouton**[!UICONTROL  Afficher les voyages]** pour afficher la liste des voyages correspondants.

![](../assets/journey3bis.png)

Dans les différentes listes, vous pouvez exécuter des actions de base sur chaque élément. Par exemple, vous pouvez dupliquer ou supprimer un élément.

![](../assets/journey4.png)

## Utilisation des différents raccourcis{#section_ksq_zr1_ffb}

Voici les différents raccourcis disponibles dans l&#39;interface de Journey Orchestration.

_Dans la liste des voyages, actions, sources de données ou événements :_

* Appuyez sur **c** pour créer un nouveau voyage, une nouvelle action, une source de données ou un nouvel événement.

_Lors de la configuration d’une activité dans un voyage :_

Le canevas est automatiquement enregistré. Vous pouvez voir, en haut à gauche de la trame, l’état d’enregistrement.

* Appuyez sur **escape** pour fermer le volet de configuration et ignorer les modifications apportées. Il s’agit de l’équivalent du bouton **[!UICONTROL Annuler]**.
* Appuyez sur **[!UICONTROL Entrée]**ou cliquez en dehors du volet pour fermer le volet de configuration. Les modifications sont enregistrées. C&#39;est l&#39;équivalent du bouton**[!UICONTROL  Ok]** .
* Si vous appuyez sur **[!UICONTROL Supprimer]**ou** Retour arrière **, vous pouvez appuyer sur**[!UICONTROL  Entrée]** pour confirmer la suppression.

_Dans les fenêtres contextuelles :_

* Appuyez sur **escape** pour le fermer (équivalent du bouton **Annuler** ).
* Appuyez sur **[!UICONTROL Entrée]**pour enregistrer ou confirmer (équivalent au bouton**[!UICONTROL  Ok]** ou **[!UICONTROL Enregistrer]**).

_Dans le volet de configuration de l’événement, de la source de données ou de l’action :_

* Appuyez sur **escape** pour fermer le volet de configuration sans enregistrer.
* Appuyez sur **[!UICONTROL Entrée]**pour enregistrer les modifications et fermer le volet de configuration.
* Appuyez sur **l’onglet** pour passer d’un champ à l’autre pour le configurer.

_Dans l’éditeur d’expression simple_

* Cliquez deux fois sur un champ, à gauche, pour ajouter une requête (équivalent à glisser-déposer).

_Lorsque vous parcourez les champs XDM :_

* Si vous cochez &quot;noeud&quot;, tous les champs du noeud seront sélectionnés.

_Dans toutes les zones de texte :_

* Utilisez la combinaison de touches **Ctrl/Commande + A** pour sélectionner le texte. Dans l’aperçu de la charge utile, il sélectionne la charge.

_Dans un écran avec une barre de recherche :_

* Utilisez la combinaison **Ctrl/Commande + F** pour sélectionner la barre de recherche.

_Sur la toile d&#39;un voyage :_

* Utilisez la combinaison de touches **Ctrl/Commande + A** pour sélectionner toutes les activités.
* Lorsqu’une ou plusieurs activités sont sélectionnées, appuyez sur **[!UICONTROL Supprimer]**ou** Retour arrière **pour les supprimer. Ensuite, vous pouvez appuyer sur**[!UICONTROL  Entrée]** pour confirmer dans la fenêtre contextuelle de confirmation.
* Cliquez deux fois sur une activité dans la palette de gauche pour l’ajouter à la première position disponible (du haut vers le bas).
