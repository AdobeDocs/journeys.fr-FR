---
title: Gestion des accès
description: En savoir plus sur la gestion des accès
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: fed6fd8d8ee497ec47727f7297dc72f319fabe27

---


# Gestion des accès{#concept_rfj_wpt_52b}

## Gestion des accès {#about-access-management}

Les profils de produit sont attribués à un ensemble d’utilisateurs qui partagent les mêmes droits au sein de votre entreprise.

Dans la console d’administration, vous pouvez attribuer l’un des profils de produit prêts à l’emploi suivants à vos utilisateurs :

* **[!UICONTROL Utilisateur]**à accès limité : utilisateur disposant d’un accès en lecture seule aux voyages et aux rapports. Ce profil de produit comprend les droits suivants :
   * Lire les voyages
   * Rapports en lecture

* **[!UICONTROL Administrateurs]**: utilisateur ayant accès aux menus d&#39;administration avec la possibilité de gérer les voyages, les événements et les rapports. Ce profil de produit comprend les droits suivants :
   * Gestion et exécution des voyages
   * Gestion des événements, des sources de données et des actions
   * Gestion des rapports
   >[!NOTE]
   >
   >**[!UICONTROL Les administrateurs]**sont le seul profil de produit qui permet la création, l’édition et la publication de messages transactionnels (ou modèles de messagerie) dans Adobe Campaign Standard. Ce profil de produit est nécessaire si vous utilisez Adobe Campaign Standard pour envoyer des messages dans vos voyages.

* **[!UICONTROL Utilisateur]**standard : utilisateur disposant d’un accès de base, tel que la gestion du voyage. Ce profil de produit comprend les droits suivants :
   * Gestion et exécution des voyages
   * Gestion des rapports

Vous trouverez [ici](../assets/do-not-localize/acs_rights_journeys.pdf) la compatibilité entre les droits et les différentes fonctionnalités de Journey Orchestration.

## Affectation d’un profil de produit {#assigning-product-profile}

Les profils de produit sont gérés dans la console d’administration. For more on this, refer to the [Admin Console documentation](https://helpx.adobe.com/enterprise/managing/user-guide.html).

Pour affecter un profil de produit à un utilisateur pour accéder à l’orchestration du voyage :

1. Dans la console d’administration, sélectionnez **[!UICONTROL Orchestration]**du voyage.

   ![](../assets/user_management.png)

1. Sélectionnez le profil de produit auquel votre nouvel utilisateur sera lié.

   ![](../assets/user_management_2.png)

1. Click **[!UICONTROL Add user]**.

   Vous pouvez également ajouter votre nouvel utilisateur à un groupe d’utilisateurs afin d’affiner le jeu d’autorisations partagé. Pour plus d&#39;informations à ce propos, Voir à ce propos consultez [cette page](https://helpx.adobe.com/enterprise/using/user-groups.html).

   ![](../assets/user_management_3.png)

1. Entrez l’adresse électronique du nouvel utilisateur, puis cliquez sur **[!UICONTROL Enregistrer]**.

   ![](../assets/user_management_4.png)

Votre utilisateur doit alors recevoir un courrier électronique redirigeant vers votre instance d’orchestration du voyage.