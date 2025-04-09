---
product: adobe campaign
title: Source de données Adobe Experience Platform
description: Découvrez comment configurer la source de données Adobe Experience Platform
feature: Journeys
role: User
level: Intermediate
exl-id: 847fa819-2b92-49e5-8a5e-4f3f0acd5e35
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 76%

---

# Source de données Adobe Experience Platform {#concept_zrb_nqt_52b}


>[!CAUTION]
>
>**Vous recherchez Adobe Journey Optimizer** ? Cliquez [ici](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/ajo-home) pour accéder à la documentation de Journey Optimizer.
>
>
>_Cette documentation se rapporte aux anciens contenus de Journey Orchestration qui ont été remplacés par Journey Optimizer. Pour toute question concernant votre accès à Journey Orchestration ou Journey Optimizer, veuillez contacter votre équipe de compte._


La source de données Adobe Experience Platform définit la connexion au service de profil client en temps réel. Il s’agit d’une source de données intégrée et préconfigurée. Elle ne peut pas être supprimée. Cette source de données est conçue pour récupérer et utiliser des données du service de profil client en temps réel (par exemple, vérifier si la personne qui est entrée dans un parcours est de sexe féminin). Elle vous permet d&#39;utiliser les données de profil et les données des événements d&#39;expérience. Pour plus d’informations sur le service de profil client en temps réel, consultez cette [page](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=fr).

>[!NOTE]
>
>Vous pouvez récupérer les 1 000 derniers événements d’expérience créés il y a moins d’un an.

Pour autoriser la connexion au service de profil client en temps réel, nous devons utiliser une clé afin d’identifier une personne, ainsi qu’un espace de noms qui contextualise la clé. Par conséquent, vous ne pouvez utiliser cette source de données que si vos parcours commencent par un événement contenant une clé et un espace de noms. Voir [cette page](../building-journeys/journey.md).

You can edit the pre-configured field group named &quot;ProfileFieldGroup&quot;, add new ones and remove the ones that are not used in any draft or live journeys. Voir [cette page](../datasource/field-groups.md).

Les principales étapes nécessaires pour ajouter des groupes de champs à la source de données intégrée sont les suivantes :

1. Dans la liste des sources de données, sélectionnez la source de données Adobe Experience Platform intégrée.

   Le volet de configuration de la source de données s’ouvre alors dans la partie droite de l’écran.

   ![](../assets/journey23.png)

1. Cliquez sur **[!UICONTROL Ajouter un nouveau groupe de champs]** pour définir une nouvelle série de champs à récupérer. Voir [cette page](../datasource/field-groups.md).

   ![](../assets/journey24.png)

1. Sélectionnez un schéma dans la liste déroulante **[!UICONTROL Schéma]**. Ce champ répertorie les schémas de profil et d’événements d’expérience disponibles dans Adobe Experience Platform. La création du schéma n’est pas effectuée dans [!DNL Journey Orchestration], mais It&#39;s performed in the Adobe Experience Platform.
1. Sélectionnez les champs que vous souhaitez utiliser.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

Lorsque vous placez le curseur sur le nom d’un groupe de champs, deux icônes s’affichent à droite. Elles vous permettent de supprimer et de dupliquer le groupe de champs. Notez que l’icône **[!UICONTROL Supprimer]** n’est disponible que si le groupe de champs n’est utilisé dans aucun parcours actif ou dans un état de brouillon (cette information est affichée dans le champ **[!UICONTROL Utilisé(e) dans]**).
