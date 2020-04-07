---
title: 'Source de données Adobe Experience Platform '
description: 'Découvrez comment configurer la source de données Adobe Experience Platform '
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
source-git-commit: e579936cfe5eb43caf72627004f98a5746c7abb1

---


# Source de données Adobe Experience Platform {#concept_zrb_nqt_52b}

La source de données Experience Platform définit la connexion au service de profil client en temps réel. Il s’agit d’une source de données intégrée et préconfigurée. Elle ne peut pas être supprimée. Cette source de données est conçue pour récupérer et utiliser des données du service de profil client en temps réel (par exemple, vérifier si la personne qui est entrée dans un parcours est de sexe féminin). Elle vous permet d’utiliser les données de profil et les données des événements d’expérience. Pour plus d’informations sur le service de profil client en temps réel, consultez cette [page](https://docs.adobe.com/content/help/en/experience-platform/profile/home.html).

>[!NOTE]
>
>Vous pouvez récupérer les 1 000 derniers événements d’expérience créés il y a moins d’un an.

Pour autoriser la connexion au service de profil client en temps réel, nous devons utiliser une clé afin d’identifier une personne, ainsi qu’un namespace qui contextualise la clé. Par conséquent, vous ne pouvez utiliser cette source de données que si vos parcours commencent par un événement contenant une clé et un namespace. Voir [](../building-journeys/journey.md).

Vous pouvez modifier le groupe de champs préconfiguré nommé « ProfileFieldGroup », en ajouter de nouveaux et supprimer ceux qui ne sont pas utilisés dans les parcours actifs ou dans un état de brouillon. Voir [](../datasource/field-groups.md).

Les principales étapes nécessaires pour ajouter des groupes de champs à la source de données intégrée sont les suivantes :

1. Dans la liste des sources de données, sélectionnez la source de données Experience Platform intégrée.

   Le volet de configuration de la source de données s’ouvre alors dans la partie droite de l’écran.

   ![](../assets/journey23.png)

1. Cliquez sur **[!UICONTROL Add a New Field Group]** pour définir une nouvelle série de champs à récupérer. Voir [](../datasource/field-groups.md).

   ![](../assets/journey24.png)

1. Select a schema from the **[!UICONTROL Schema]** drop-down. Ce champ répertorie les schémas de profil et d’événements d’expérience disponibles dans la plate-forme. La création du schéma n’est pas effectuée dans Journey Orchestration, mais dans Data Platform.
1. Sélectionnez les champs que vous souhaitez utiliser.
1. Définissez la durée de mise en cache.
1. Cliquez sur **[!UICONTROL Save]**.

Lorsque vous placez le curseur sur le nom d’un groupe de champs, deux icônes s’affichent à droite. Elles vous permettent de supprimer et de dupliquer le groupe de champs. Note that the **[!UICONTROL Delete]** icon is only available if the field group is not used in any live or draft journey (information displayed in the **[!UICONTROL Used in]** field).
