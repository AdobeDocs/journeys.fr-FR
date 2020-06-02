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
source-git-commit: 2a53413c79f0213434f9ca6a7847bd7f20fbf41e
workflow-type: tm+mt
source-wordcount: '900'
ht-degree: 32%

---


# Gestion des accès{#concept_rfj_wpt_52b}

## Gestion des accès {#about-access-management}

L’orchestration du parcours vous permet d’attribuer un ensemble de droits et de sandbox à vos utilisateurs afin de définir la partie de l’interface à laquelle ils peuvent accéder.

Ils peuvent être gérés par des administrateurs qui ont accès à la console d’administration. Pour plus d&#39;informations sur la console d&#39;administration, consultez cette [documentation](https://helpx.adobe.com/fr/enterprise/managing/user-guide.html).

Admin console permet d’attribuer aux utilisateurs l’un des profils de produit d’usine suivants :

* **[!UICONTROL Utilisateur à accès limité]** : utilisateur disposant d’un accès en lecture seule aux parcours et aux rapports. Ce profil de produit comprend les droits suivants :
   * Lire les parcours
   * Lire les rapports

* **[!UICONTROL Administrateur]** : utilisateur ayant accès aux menus d’administration avec la possibilité de gérer les parcours, les événements et les rapports. Ce profil de produit comprend les droits suivants :
   * Gérer les voyages
   * Publier les voyages
   * Gérer les événements, les sources de données et les actions
   * Gérer les rapports
   >[!NOTE]
   >
   >Les **[!UICONTROL administrateurs]** sont le seul profil de produit qui permet la création, l’édition et la publication de messages transactionnels (ou de modèles de message) dans Adobe Campaign Standard. Ce profil de produit est nécessaire si vous utilisez Adobe Campaign Standard pour envoyer des messages dans vos parcours.

* **[!UICONTROL Utilisateur standard]** : utilisateur disposant d’un accès de base, tel que la gestion des parcours. Ce profil de produit comprend les droits suivants :
   * Gérer les voyages
   * Publier les voyages
   * Gérer les rapports

Vous pouvez également créer vos propres profils de produits si les profils prêts à l’emploi ne suffisent pas à gérer vos utilisateurs.
Les utilisateurs doivent toujours être liés à un profil de produits, ce qui vous permet de leur attribuer des droits de connexion spécifiques, tels que :

* **[!UICONTROL Lire les parcours]**
* **[!UICONTROL Lire les rapports]**
* **[!UICONTROL Gérer les événements, les sources de données et les actions]**
* **[!UICONTROL Lire les événements, les sources de données et les actions]**
* **[!UICONTROL Gérer les voyages]**
* **[!UICONTROL Publier les voyages]**
* **[!UICONTROL Gérer les rapports]**

Vous trouverez ci-dessous la compatibilité entre les droits et les différentes fonctionnalités de Journey Orchestration.

![](../assets/journey_permission.png)

## Creating a product profile {#create-product-profile}

L’orchestration du voyage vous permet de créer vos propres profils de produits et d’attribuer un ensemble de droits et de sandbox à vos utilisateurs. Avec les profils de produit, vous pouvez autoriser ou refuser l’accès à certaines fonctionnalités ou à certains objets de l’interface.

Pour plus d’informations sur la création et la gestion des sandbox, voir la documentation [de la plateforme](https://docs.adobe.com/content/help/en/experience-platform/sandbox/ui/user-guide.html)Adobe Experience Platform.

Pour créer un profil de produits et attribuer un ensemble de droits et de sandbox :

1. Sélectionnez **[!UICONTROL Journey Orchestration]** dans Admin console. Dans l’onglet profil **** de produits, cliquez sur **[!UICONTROL Nouveau Profil]**.

1. Ajoutez un nom **[!UICONTROL de]** Profil et une **[!UICONTROL description]** pour votre nouveau profil de produits. Si vous souhaitez que le nom **[!UICONTROL d’]** affichage du profil soit différent, désélectionnez **[!UICONTROL Identique au nom]** du Profil et saisissez votre nom **** d’affichage.

1. Dans la catégorie Notifications **** utilisateur, indiquez si les utilisateurs seront avertis par courrier électronique lorsqu’ils seront ajoutés ou supprimés de ce profil de produits.

1. Lorsque vous avez terminé, cliquez sur **[!UICONTROL Terminé]**. Votre nouveau profil de produits est maintenant créé.

1. Sélectionnez votre nouveau profil de produits pour début des autorisations de gestion. Dans l’onglet **[!UICONTROL Utilisateurs]** , ajoutez des utilisateurs à votre profil de produits. Pour plus d’informations à ce propos, consultez cette [page](../about/access-management.md#assigning-product-profile).

1. Effectuez les mêmes étapes que celles décrites ci-dessus pour ajouter l’ **[!UICONTROL administrateur]** à votre profil de produits.

1. Dans l’onglet **[!UICONTROL Autorisations]** , sélectionnez l’une des deux catégories **[!UICONTROL Sandbox]** ou **[!UICONTROL Création]** pour ouvrir la page **[!UICONTROL Modifier les autorisations et ajouter ou supprimer des autorisations pour votre profil de produits.]**

1. Dans la catégorie d’autorisation **[!UICONTROL Sandbox]** , sélectionnez le ou les sandbox à affecter à votre profil de produits. Sous Éléments **[!UICONTROL d’autorisations]** disponibles, cliquez sur l’icône Plus (+) pour affecter des sandbox à votre profil.

   >[!NOTE]
   >
   >L&#39;orchestration du voyage peut maintenant être connectée à la plateforme de production et non-production Sandbox. Disponibilité efficace : 15 juin 2020.
   <br>Pour plus d&#39;informations sur les sandbox, consultez cette [section](../about/access-management.md#sandboxes).

1. Si nécessaire, sous Éléments **[!UICONTROL d’autorisation]** inclus, cliquez sur l’icône X en regard de pour supprimer les autorisations sur votre profil de produits.

1. A partir de la catégorie d’autorisation de **[!UICONTROL création]** , effectuez les mêmes étapes que ci-dessus pour ajouter des droits à votre profil de produits.
   <br>Pour plus d&#39;informations sur les droits et la compatibilité entre les droits et les différentes fonctionnalités de Journey Orchestration, consultez cette [section](../about/access-management.md#about-access-management).

1. Lorsque vous avez terminé, cliquez sur **[!UICONTROL Enregistrer]**.

Votre profil de produits est maintenant créé et configuré. Les utilisateurs liés à ce profil peuvent désormais se connecter à l’orchestration du parcours.

## Attribution d’un profil de produit {#assigning-product-profile}

Les profils de produit sont attribués à un ensemble d’utilisateurs qui partagent les mêmes droits au sein de votre entreprise.
La liste de tous les profils de produits prêts à l&#39;emploi avec des droits attribués se trouve dans cette section.

Pour attribuer un profil de produit à un utilisateur et lui permettre d’accéder à Journey Orchestration :

1. Sélectionnez **[!UICONTROL Journey Orchestration]** dans Admin console.

   ![](../assets/user_management.png)

1. Sélectionnez le profil de produit auquel votre nouvel utilisateur sera associé.

   ![](../assets/user_management_2.png)

1. Cliquez sur **[!UICONTROL Ajouter un utilisateur]**.

   Vous pouvez également ajouter votre nouvel utilisateur à un groupe d’utilisateurs pour parfaire l’ensemble d’autorisations partagé. Pour plus d’informations à ce propos, consultez [cette page](https://helpx.adobe.com/fr/enterprise/using/user-groups.html).

   ![](../assets/user_management_3.png)

1. Saisissez l’adresse email du nouvel utilisateur, puis cliquez sur **[!UICONTROL Enregistrer]**.

   ![](../assets/user_management_4.png)

L’utilisateur doit alors recevoir un email pour le rediriger vers votre instance de Journey Orchestration.

## Utilisation des sandbox {#sandboxes}

>[!NOTE]
>
>L&#39;orchestration du voyage peut maintenant être connectée à la plateforme de production et non-production Sandbox. Disponibilité efficace : 15 juin 2020.

L&#39;orchestration du voyage vous permet de partitionner votre instance en environnements virtuels séparés appelés sandbox.
Les sandbox sont assignées par le biais des profils de produit dans la console d’administration. For more information on how to assign sandboxes, refer to this [section](../about/access-management.md#create-product-profile).

L’orchestration du voyage reflète les sandbox de plateforme qui ont été créés pour une organisation donnée.
Vous pouvez créer ou réinitialiser des sandbox de plateforme à partir de votre instance de plateforme d’expérience Adobe. Consultez le guide [d&#39;utilisation de](https://docs.adobe.com/content/help/en/experience-platform/sandbox/ui/user-guide.html) Sandbox pour connaître les étapes détaillées.

Vous pouvez trouver la commande sandbox dans la partie supérieure gauche de votre écran. Pour passer d’un sandbox à un autre, cliquez sur le sandbox actif dans le sélecteur et sélectionnez un autre sandbox dans la liste déroulante.