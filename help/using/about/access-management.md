---
product: adobe campaign
title: Gestion des accès
description: En savoir plus sur la gestion des accès.
feature: Journeys
role: User
level: Intermediate
exl-id: a551efa5-c0d8-4138-96ca-fb407fad8c59
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '949'
ht-degree: 100%

---

# Gestion des accès{#concept_rfj_wpt_52b}


>[!CAUTION]
>
>**Vous recherchez Adobe Journey Optimizer** ? Cliquez [ici](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/ajo-home){target="_blank"} pour consulter la documentation de Journey Optimizer.
>
>
>_Cette documentation se rapporte aux anciens contenus de Journey Orchestration qui ont été remplacés par Journey Optimizer. Pour toute question concernant votre accès à Journey Orchestration ou Journey Optimizer, contactez votre équipe en charge des comptes._



## Gestion des accès {#about-access-management}

[!DNL Journey Orchestration] permet d’affecter un ensemble d’autorisations aux utilisateurs et utilisatrices afin de définir la partie de l’interface à laquelle ils ont accès.

Les autorisations peuvent être gérées par des administrateurs et administratrices qui ont accès à Admin Console. Pour plus d’informations sur Admin Console, consultez le [guide d’administration pour les entreprises et les équipes](https://helpx.adobe.com/fr/enterprise/managing/user-guide.html).

Pour pouvoir accéder à [!DNL Journey Orchestration], un utilisateur doit :

* faire partie d’un **[!UICONTROL profil de produit]** [!DNL Journey Orchestration] associé aux autorisations de [!DNL Journey Orchestration] ;
* faire partie d’un [!DNL Adobe Experience Platform] **[!UICONTROL profil de produit]**. Aucune autorisation n’est demandée. L’utilisateur doit disposer de l’autorisation de **[!UICONTROL gestion des profils]** pour pouvoir créer et modifier des segments de plateforme à partir de l’interface de [!DNL Journey Orchestration]. Pour en savoir plus à ce sujet, consultez cette [page](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=fr#adobe-admin-console).

Admin Console permet d’attribuer aux utilisateurs et utilisatrices l’un des profils de produit par défaut suivants :

* **[!UICONTROL Utilisateur ou utilisatrice à accès limité]** : utilisateur ou utilisatrice disposant d’un accès en lecture seule aux parcours et aux rapports. Ce profil de produit comprend les autorisations suivantes :
   * Lire les parcours
   * Lire les rapports

* **[!UICONTROL Administrateur]** : utilisateur ayant accès aux menus d’administration avec la possibilité de gérer les parcours, les événements et les rapports. Ce profil de produit comprend les autorisations suivantes :
   * Gérer les parcours
   * Publier les parcours
   * Gérer les événements, les sources de données et les actions
   * Gérer les rapports

  >[!NOTE]
  >
  >Le profil de produit **[!UICONTROL Administrateurs]** est le seul qui permet la création, la modification et la publication de messages transactionnels (ou de modèles de message) dans Adobe Campaign Standard. Ce profil de produit est nécessaire si vous utilisez Adobe Campaign Standard pour envoyer des messages dans vos parcours. Il ne doit pas être renommé dans Admin Console.

* **[!UICONTROL Utilisateur standard]** : utilisateur disposant d’un accès de base, tel que la gestion des parcours. Ce profil de produit comprend les autorisations suivantes :
   * Gérer les parcours
   * Publier les parcours
   * Gérer les rapports
   * Lire les événements, les sources de données et les actions

Vous pouvez également créer vos propres profils de produit si les profils par défaut ne suffisent pas pour gérer vos utilisateurs.
Les utilisateurs doivent toujours être liés à un profil de produit, ce qui vous permet de leur attribuer des autorisations intégrées spécifiques, telles que :

* **[!UICONTROL Lire les parcours]**
* **[!UICONTROL Lire les rapports]**
* **[!UICONTROL Gérer les événements, les sources de données et les actions]**
* **[!UICONTROL Lire les événements, les sources de données et les actions]**
* **[!UICONTROL Gérer les parcours]**
* **[!UICONTROL Publier les parcours]**
* **[!UICONTROL Gérer les rapports]**

Vous trouverez ci-dessous des informations relatives à la compatibilité entre les droits et les différentes fonctionnalités de [!DNL Journey Orchestration].

![](../assets/do-not-localize/journey_permission.png)

## Création d&#39;un profil de produit {#create-product-profile}

[!DNL Journey Orchestration] vous permet de créer vos propres profils de produit et d’attribuer un ensemble de droits et d’environnements Sandbox à vos utilisateurs. Avec les profils de produit, vous pouvez autoriser ou refuser l’accès à certaines fonctionnalités ou à certains objets de l’interface.

Pour plus d’informations sur la création et la gestion des sandbox, consultez la [documentation d’Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/user-guide.html?lang=fr).

Pour créer un profil de produit et attribuer un ensemble d’autorisations et d’environnements Sandbox :

1. Sélectionnez **[!UICONTROL Journey Orchestration]** dans Admin console. Dans l’onglet **[!UICONTROL Profil produit]**, cliquez sur **[!UICONTROL Nouveau profil]**.

   ![](../assets/do-not-localize/user_management_5.png)

1. Ajoutez un **[!UICONTROL Nom de profil]** et une **[!UICONTROL Description]** à votre nouveau profil de produit. Si vous souhaitez que le **[!UICONTROL Nom d’affichage]** du profil soit différent, désélectionnez **[!UICONTROL Identique au nom de profil]** et saisissez le **[!UICONTROL Nom d’affichage]**.

1. Dans la catégorie **[!UICONTROL Notifications utilisateur]**, indiquez si les utilisateurs seront avertis par e-mail lorsqu’ils seront ajoutés ou supprimés de ce profil de produit.

1. Lorsque vous avez terminé, cliquez sur **[!UICONTROL Terminé]**. Votre nouveau profil de produit est maintenant créé.

   ![](../assets/do-not-localize/user_management_1.png)

1. Sélectionnez votre nouveau profil de produit pour commencer à gérer les autorisations. Dans l’onglet **[!UICONTROL Utilisateurs]**, ajoutez des utilisateurs à votre profil de produit. Pour en savoir plus à ce sujet, consultez cette [page](../about/access-management.md#assigning-product-profile).

1. Procédez comme décrit ci-dessus pour ajouter l’**[!UICONTROL Administrateur]** à votre profil de produit.

1. Dans l’onglet **[!UICONTROL Autorisations]**, sélectionnez l’une des deux catégories **[!UICONTROL Sandbox]** ou **[!UICONTROL Création]** pour ouvrir la page **[!UICONTROL Modifier les autorisations]** et ajouter ou supprimer des autorisations pour votre profil de produit.

   ![](../assets/do-not-localize/user_management_7.png)

1. Dans la catégorie d’autorisation **[!UICONTROL Sandbox]**, sélectionnez un ou plusieurs environnements Sandbox à affecter à votre profil de produit. Dans **[!UICONTROL Éléments d’autorisations disponibles]**, cliquez sur l’icône plus (+) pour affecter des sandbox à votre profil. Pour plus d’informations sur les environnements Sandbox, consultez cette [section](../about/access-management.md#sandboxes).

   ![](../assets/do-not-localize/user_management_8.png)

1. Si nécessaire, dans **[!UICONTROL Éléments d&#39;autorisations disponibles]**, cliquez sur l&#39;icône X la plus proche pour supprimer les autorisations de votre profil de produit.

   ![](../assets/do-not-localize/user_management_9.png)

1. Dans la catégorie d’autorisation **[!UICONTROL Création]**, procédez comme indiqué ci-dessus pour ajouter des droits à votre profil de produit.
   <br>Pour plus d’informations sur les droits et la compatibilité entre les droits et les différentes fonctionnalités de [!DNL Journey Orchestration], consultez cette [section](../about/access-management.md#about-access-management).

   ![](../assets/do-not-localize/user_management_10.png)

1. Lorsque vous avez terminé, cliquez sur **[!UICONTROL Enregistrer]**.

Votre profil de produit est maintenant créé et configuré. Les utilisateurs liés à ce profil peuvent désormais se connecter à [!DNL Journey Orchestration].

## Attribution d&#39;un profil de produit {#assigning-product-profile}

Les profils de produit sont attribués à un ensemble d’utilisateurs qui partagent les mêmes autorisations au sein de votre entreprise.
Vous trouverez dans cette section la liste de tous les profils de produit par défaut auxquels des autorisations sont associées.

Pour attribuer un profil de produit à un utilisateur et lui permettre d’accéder à [!DNL Journey Orchestration]:

1. Sélectionnez **[!UICONTROL Journey Orchestration]** dans Admin console.

   ![](../assets/do-not-localize/user_management.png)

1. Sélectionnez le profil de produit auquel votre nouvel utilisateur sera associé.

   ![](../assets/do-not-localize/user_management_2.png)

1. Cliquez sur **[!UICONTROL Ajouter un utilisateur]**.

   Vous pouvez également ajouter votre nouvel utilisateur à un groupe d’utilisateurs pour parfaire l’ensemble d’autorisations partagé. Pour en savoir plus à ce sujet, consultez cette [page](https://helpx.adobe.com/fr/enterprise/using/user-groups.html).

   ![](../assets/do-not-localize/user_management_3.png)

1. Saisissez l’adresse email du nouvel utilisateur, puis cliquez sur **[!UICONTROL Enregistrer]**.

   ![](../assets/do-not-localize/user_management_4.png)

L’utilisateur doit alors recevoir un e-mail le redirigeant vers votre instance de [!DNL Journey Orchestration]

## Utilisation des sandbox {#sandboxes}

[!DNL Journey Orchestration] vous permet de partitionner votre instance en environnements virtuels séparés appelés sandbox.
Les sandbox sont affectés par le biais des profils de produit dans Admin console. Pour plus d’informations sur l’affectation de sandbox, consultez cette [section](../about/access-management.md#create-product-profile).

[!DNL Journey Orchestration] reflète les environnements Sandbox Adobe Experience Platform qui ont été créés pour une organisation donnée.
Vous pouvez créer ou réinitialiser des sandbox Adobe Experience Platform à partir de votre instance Adobe Experience Platform. Consultez le [Guide de l’utilisateur de Sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/user-guide.html?lang=fr) pour connaître la procédure à suivre.


La commande de sélecteur des environnements Sandbox se trouve dans la partie supérieure gauche de votre écran. Pour passer d’un sandbox à un autre, cliquez sur le sandbox actif dans le sélecteur et sélectionnez-en un autre dans la liste déroulante.
