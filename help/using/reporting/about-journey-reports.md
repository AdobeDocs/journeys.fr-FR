---
title: A propos des rapports de voyage
description: Découvrez comment créer vos rapports de voyage
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
source-git-commit: b5b3c8b6adafaedbdd80db3091300e7a26249a3e

---


# A propos des rapports de voyage {#concept_rfj_wpt_52b}

>[!NOTE]
>
>Les données de remise et le composant Segments ne seront renseignés que si vous disposez d’Adobe Campaign Standard.

Cette section vous explique comment accéder aux rapports et les utiliser pour mesurer l&#39;efficacité de vos voyages.

## Interface du reporting {#reporting-interface}

La barre d&#39;outils supérieure vous permet de modifier, d&#39;enregistrer ou d&#39;imprimer votre rapport, par exemple.

![](../assets/dynamic_report_toolbar.png)

Utilisez l&#39;onglet **[!UICONTROL Projet]**pour :

* **[!UICONTROL Ouvrir]**: ouvre un rapport ou un modèle créé précédemment.
* **[!UICONTROL Enregistrer sous]**: duplique les modèles pour pouvoir les modifier.
* **[!UICONTROL Actualiser le projet]**: met à jour votre rapport en fonction des nouvelles données et des modifications apportées aux filtres.
* **[!UICONTROL Télécharger CSV]**: exporte vos rapports dans un fichier CSV.
* **[!UICONTROL Imprimer]**: imprime votre rapport.

L&#39;onglet **[!UICONTROL Modifier]**vous permet de :

* **[!UICONTROL Annuler]**: annule votre dernière action sur votre tableau de bord.
* **[!UICONTROL Rétablir]**: annule votre dernière action**[!UICONTROL  Annuler]** sur votre tableau de bord.
* **[!UICONTROL Effacer tout]**: supprime chaque panneau de votre tableau de bord.

Le tableau **[!UICONTROL Insérer]**vous permet de personnaliser vos rapports en ajoutant des graphiques et des tableaux à votre tableau de bord :

* **[!UICONTROL Nouveau panneau]**vierge : ajoute un nouveau panneau vide à votre tableau de bord.
* **[!UICONTROL Nouvelle forme libre]**: ajoute un nouveau tableau à structure libre à votre tableau de bord.
* **[!UICONTROL Nouvelle ligne]**: ajoute un nouveau graphique en courbes à votre tableau de bord.
* **[!UICONTROL Nouvelle barre]**: ajoute un nouveau graphique à barres à votre tableau de bord.

Les onglets de gauche vous permettent de créer votre rapport et de filtrer les données selon les besoins.

![](../assets/dynamic_report_interface.png)

Ces onglets vous donnent accès aux éléments suivants :

* **[!UICONTROL Panneaux]** : ajoutez un panneau vide ou une forme libre à votre rapport pour commencer à filtrer les données. For more on this, refer to the[Adding panels](../reporting/creating-your-journey-reports.md#adding-panels)section
* **[!UICONTROL Visualisations]** : déposez une sélection d&#39;éléments de visualisation pour donner à votre rapport une dimension graphique. For more on this, refer to the[Adding visualizations](../reporting/creating-your-journey-reports.md#adding-visualizations)section.
* **[!UICONTROL Composants]** : permettent de personnaliser les rapports grâce à différentes dimensions, valeurs métriques et périodes et à différents segments. For more on this, refer to the[Adding components](../reporting/creating-your-journey-reports.md#adding-components)section.

## Modèle de résumé de voyage {#ootb-template}

Les rapports sont répartis en deux catégories : un modèle prêt à l’emploi et des rapports personnalisés.
Le modèle prêt à l’emploi, Résumé ****du voyage, vous donne une vue claire des données de suivi les plus importantes.

![](../assets/dynamic_report_journey_8.png)

Chaque tableau est représenté par des nombres et des graphiques de synthèse. Les paramètres de visualisation des détails vous permettent de modifier leur affichage.

Les IPC suivants sont disponibles en haut du rapport :

* **[!UICONTROL Parcours - Entré]**: nombre total de personnes ayant atteint l’événement d’entrée du voyage.
* **[!UICONTROL Parcours - Taux]**d&#39;achèvement : nombre total de personnes qui ont atteint la fin du voyage (ou dans le cas d&#39;une personne ne correspondant à aucune condition) par rapport au nombre total de personnes qui sont entrées dans le voyage.
* **[!UICONTROL Voyage - Actuel]**: nombre total de personnes actuellement en voyage.
* **[!UICONTROL Voyage - Taux]**d&#39;échec : nombre total de voyages qui n&#39;ont pas été exécutés avec succès par rapport au nombre de voyages d&#39;exécution.
* **[!UICONTROL Livraison - Messages envoyés]**: nombre total de messages envoyés.
* **[!UICONTROL Taux]**de remise : nombre total de messages transmis avec succès par rapport aux messages envoyés.
* **[!UICONTROL Livraison - Taux]**de rebonds : nombre total de messages qui ont rebondi par rapport aux messages envoyés.
* **[!UICONTROL Livraison - Taux]**de désabonnement : nombre total de désabonnements par destinataire par rapport aux messages diffusés.
* **[!UICONTROL Livraison - Taux]**ouvert : nombre total de messages ouverts par rapport au nombre de messages remis.
* **[!UICONTROL Livraison - Taux]**de clics : nombre total de clics dans une remise par rapport au nombre de messages remis.

La visualisation du flux de voyage vous permet de voir le chemin de vos profils ciblés pas à pas dans votre parcours. Ceci n’est disponible que lorsque vous ciblez un voyage. Il est généré automatiquement et ne peut pas être modifié.

![](../assets/dynamic_report_journey_10.png)

Le tableau récapitulatif **[!UICONTROL du]**voyage contient les données disponibles pour votre voyage, telles que :

* **[!UICONTROL Saisi]**: nombre total de personnes ayant atteint l’événement d’entrée du voyage.
* **[!UICONTROL Taux]**d&#39;achèvement : nombre total de personnes qui ont atteint le contrôle du flux final du voyage par rapport au nombre total de personnes qui sont entrées dans le voyage.
* **[!UICONTROL Actuel]**: nombre total de personnes actuellement en voyage.
* **[!UICONTROL Échec]**: nombre total de voyages qui n&#39;ont pas été exécutés avec succès.
* **[!UICONTROL Taux]**d&#39;échec : nombre total de voyages qui n&#39;ont pas été exécutés avec succès par rapport au nombre de voyages d&#39;exécution.

Le tableau **[!UICONTROL Principaux événements]**affiche les événements les plus réussis et l&#39;action****Principaux, les actions les plus réussies de vos voyages.

![](../assets/dynamic_report_journey_11.png)

Le tableau récapitulatif **[!UICONTROL Livraison - Envoi]**contient les données disponibles pour les livraisons de votre voyage, telles que :

* **[!UICONTROL Traitée/envoyée]**: nombre total de messages envoyés.
* **[!UICONTROL Taux]**de remise : nombre total de messages transmis avec succès par rapport aux messages envoyés.
* **[!UICONTROL Livré]**: nombre de messages envoyés, par rapport au nombre total de messages envoyés.
* **[!UICONTROL Rebonds + taux]**d’erreur : nombre total de messages qui ont rebondi par rapport aux messages envoyés.
* **[!UICONTROL Retours + erreurs]**: total des erreurs cumulées pendant la remise et le traitement automatique des retours par rapport au nombre total de messages envoyés.

Le tableau récapitulatif ****Livraison - Suivi contient les données disponibles pour suivre le succès des livraisons de vos voyages, telles que :

* **[!UICONTROL Taux]**d&#39;ouverture : pourcentage de messages ouverts.
* **[!UICONTROL Ouvrir]**: nombre de fois où un message a été ouvert dans une remise.
* **[!UICONTROL Taux]**de clics publicitaires : nombre total de clics dans une remise par rapport au nombre de messages remis.
* **[!UICONTROL Cliquez sur]**: nombre de clics sur un contenu dans une diffusion.
* **[!UICONTROL Taux]**de désabonnement : pourcentage de désabonnements par destinataire par rapport aux messages diffusés.
* **[!UICONTROL Désabonnement]**: nombre total de désabonnements par destinataire par rapport aux messages diffusés.
