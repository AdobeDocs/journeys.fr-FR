---
title: Utilisation du concepteur du voyage
description: En savoir plus sur l'utilisation du concepteur de voyages
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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# Using the journey designer {#concept_m1g_5qt_52b}

Le menu Accueil du voyage vous permet de consulter la **liste des voyages**. Créez un nouveau voyage ou cliquez sur un voyage existant pour ouvrir l&#39;interface **du concepteur du** voyage. Le concepteur se compose des zones suivantes : la palette, le canevas et le volet de configuration de l’activité.

## La liste des voyages {#journey_list}

La liste des **voyages** vous permet de visualiser tous vos voyages en même temps, de voir leur statut et d&#39;effectuer des actions de base. Vous pouvez dupliquer, arrêter ou supprimer vos voyages. En fonction du voyage, certaines actions peuvent ne pas être disponibles. Par exemple, vous ne pouvez pas arrêter un voyage arrêté. Vous pouvez également utiliser la barre de recherche pour rechercher un voyage.

Pour accéder aux **[!UICONTROL filtres]**, cliquez sur l’icône de filtre en haut à gauche de la liste. Le menu Filtres vous permet de filtrer les voyages affichés selon différents critères (statut, ceux que vous avez créés, ceux que vous avez modifiés au cours des 30 derniers jours, versions les plus récentes uniquement, etc.). Vous pouvez également choisir d’afficher uniquement les voyages qui utilisent un événement, un groupe de champs ou une action spécifique. Les colonnes affichées dans la liste peuvent être configurées. Tous les filtres et colonnes sont enregistrés par utilisateur.

![](../assets/journey74.png)

Toutes les versions de vos voyages apparaissent dans la liste avec le numéro de version. Voir la section [](../building-journeys/journey-versions.md).

![](../assets/journey37.png)

>[!NOTE]
>
>Pour ouvrir le canevas d&#39;un voyage dans un autre onglet du navigateur, maintenez la touche **Contrôle** ou **Commande enfoncée** et cliquez sur le voyage.

## La palette {#palette}

The **palette** is on the left-hand side of the screen. Toutes les activités disponibles sont classées en plusieurs catégories : **[!UICONTROL Evénements]**,**[!UICONTROL  orchestration]** et **[!UICONTROL actions]**. Vous pouvez développer/réduire les différentes catégories en cliquant sur leur nom. Pour utiliser une activité dans votre parcours, faites-la glisser de la palette vers votre canevas. Vous pouvez également cliquer deux fois sur une activité de la palette pour l’ajouter à la trame, à l’étape suivante. Vous devez configurer chaque activité ajoutée à partir de la palette avant de publier le voyage. Si vous déposez une activité dans le canevas et que vous ne terminez pas sa configuration, elle restera dans le canevas, mais un avertissement rouge indique que la configuration n’est pas terminée pour cette activité.

>[!NOTE]
>
>Notez qu’il existe des règles lors de la configuration d’un voyage. La configuration non autorisée sera ignorée. Par exemple, vous ne pouvez pas placer des actions en parallèle, lier une activité à une étape précédente pour créer une boucle, lancer un voyage avec autre chose qu’un événement, etc.

![](../assets/journey38.png)

## La toile {#canvas}

La **toile** est la zone centrale du concepteur du voyage. C’est dans cette zone que vous pouvez abandonner vos activités et les configurer. Cliquez sur une activité dans la trame pour la configurer. Le volet de configuration de l’activité s’ouvre alors sur le côté droit. Vous pouvez effectuer un zoom avant ou arrière à l’aide des boutons &quot;+&quot; et &quot;-&quot; en haut à droite. Dans le canevas, toutes les activités vous permettent d’ajouter une étape suivante, à l’exception des activités de **[!UICONTROL fin]**(voir[](../building-journeys/end-activity.md)).

![](../assets/journey39.png)

## Le volet de configuration de l’activité {#configuration_pane}

Le volet **de configuration de l’** activité s’affiche lorsque vous cliquez sur une activité dans la palette. Renseignez les champs obligatoires. Cliquez sur l’icône **[!UICONTROL Supprimer]**pour supprimer l’activité. Cliquez sur**[!UICONTROL  Annuler]** pour annuler les modifications ou **[!UICONTROL OK]**pour confirmer. Pour supprimer des activités, vous pouvez également sélectionner une ou plusieurs activités et appuyer sur la touche Retour arrière. Appuyez sur la touche d’échappement pour fermer le volet de configuration de l’activité.

Dans le canevas, vos activités d’action et d’événement sont représentées par une icône dont le nom s’affiche sous la fenêtre. Dans le volet de configuration de l’activité, vous pouvez utiliser le champ **[!UICONTROL Etiquette]**pour ajouter un suffixe au nom de l’activité. Ces étiquettes vous aideront à contextualiser l’utilisation des événements et des actions, en particulier lorsque vous utilisez le même événement ou la même action plusieurs fois dans votre parcours. Vous pourrez également voir les étiquettes que vous avez ajoutées dans le rapport Orchestration du voyage.

![](../assets/journey59bis.png)

## Actions de la barre supérieure {#top_actions}

Selon l’état du parcours, vous pouvez effectuer différentes actions sur le parcours à l’aide des boutons disponibles dans le coin supérieur droit : **[!UICONTROL Publier]**,**[!UICONTROL  Dupliquer]**, **[!UICONTROL Supprimer]****[!UICONTROL , Propriétés du voyage, Test. ]******Ces boutons s’affichent lorsqu’aucune activité n’est sélectionnée. Certains boutons s’affichent dans le contexte. Le bouton du journal du mode test apparaît lorsque le mode test est activé (voir[](../building-journeys/testing-the-journey.md)). Le bouton de création de rapports s’affiche lorsque le voyage est en direct, arrêté ou terminé.

![](../assets/journey41.png)

## Utilisation des chemins dans la zone de travail {#paths}

Plusieurs activités (**[!UICONTROL Condition]**,**[!UICONTROL  Action]** ) vous permettent de définir une action de secours en cas d’erreur ou d’expiration. Dans le volet de configuration de l’activité, cochez la case : **[!UICONTROL Ajoutez un autre chemin en cas d’expiration ou d’erreur]**. Un autre chemin est ajouté après l’activité. La durée du délai d’expiration est définie dans les propriétés du parcours (voir[](../building-journeys/changing-properties.md)par un utilisateur administrateur). Par exemple, si l’envoi d’un courriel prend trop de temps ou est erroné, vous pouvez décider d’envoyer un SMS.

![](../assets/journey42.png)

Diverses activités (événement, action, attente) vous permettent d’ajouter plusieurs chemins après elles. Pour ce faire, placez votre curseur sur l’activité et cliquez sur le symbole &quot;+&quot;. Seules les activités d’événement et d’attente peuvent être définies en parallèle. Si plusieurs événements sont définis en parallèle, le chemin choisi est celui du premier événement qui se produit.

Lorsque vous écoutez un événement, nous vous recommandons de ne pas attendre l’événement indéfiniment. Ce n&#39;est pas obligatoire, juste une bonne pratique. Si vous souhaitez écouter un ou plusieurs événements uniquement pendant une certaine période, vous placerez un ou plusieurs événements et une activité d’attente en parallèle. Voir la section [](../building-journeys/event-activities.md#section_vxv_h25_pgb).

Pour supprimer le chemin, placez le curseur dessus et cliquez sur l’icône **[!UICONTROL Supprimer flèche]**.

![](../assets/journey42ter.png)
