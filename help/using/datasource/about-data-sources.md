---
product: adobe campaign
title: À propos des sources de données
description: Découvrez comment configurer une source de données.
feature: Journeys
role: User
level: Intermediate
exl-id: 2371d2c9-3035-46ac-9c76-755fb453c24e
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '355'
ht-degree: 100%

---

# À propos des sources de données {#concept_s1s_dqt_52b}


>[!CAUTION]
>
>**Vous recherchez Adobe Journey Optimizer** ? Cliquez [ici](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/ajo-home){target="_blank"} pour consulter la documentation de Journey Optimizer.
>
>
>_Cette documentation se rapporte aux anciens contenus de Journey Orchestration qui ont été remplacés par Journey Optimizer. Pour toute question concernant votre accès à Journey Orchestration ou Journey Optimizer, contactez votre équipe en charge des comptes._



>[!CONTEXTUALHELP]
>id="jo_datasources"
>title="À propos des sources de données"
>abstract="La configuration des sources de données vous permet de définir une connexion à un système afin de récupérer des informations supplémentaires qui seront utilisées dans vos parcours."

Elle vous permet de définir une connexion à un système afin de récupérer des informations supplémentaires qui seront utilisées dans vos parcours. Par exemple :

* [Définition d’une condition](../building-journeys/condition-activity.md)
* Données de paramètre et de personnalisation dans les [actions](../action/action.md)
* [Définition d’une attente personnalisée](../building-journeys/wait-activity.md#custom)
* [Définition d’un fuseau horaire](../building-journeys/timezone-management.md)

Cette configuration n’est pas requise si vos parcours utilisent uniquement les données locales provenant d’une payload d’événement. Par exemple, si votre parcours comprend un événement suivi d’une activité d’email qui utilise uniquement les données de l’événement, il n’est pas nécessaire de configurer une source de données.

Il existe deux types de sources de données :

* La source de données Adobe Experience Platform préconfigurée qui définit la connexion au service de profil client en temps réel. Il s’agit d’une source de données intégrée. Voir [cette page](../datasource/adobe-experience-platform-data-source.md).
* Les sources de données externes qui vous permettent de définir une connexion à des systèmes externes. Il s’agit des sources de données que vous pouvez créer. Voir [cette page](../datasource/external-data-sources.md).

Pour chaque source de données, vous définissez les informations à récupérer à l’aide de groupes de champs. Les groupes de champs sont des ensembles de champs qui peuvent être récupérés à partir d’une source de données. Voir [cette page](../datasource/field-groups.md).

Les principales étapes de configuration d’une source de données sont les suivantes :

>[!NOTE]
>
>La configuration d’une source de données est toujours effectuée par un **utilisateur ou une utilisatrice technique**.

1. Dans le volet de menus, sélectionnez **[!UICONTROL Admin]**. Dans la section **[!UICONTROL Sources de données]**, cliquez sur **[!UICONTROL Gérer]**.

   La liste des sources de données s’affiche. Pour plus d&#39;informations sur l&#39;interface, voir [cette page](../about/user-interface.md)

   ![](../assets/journey18.png)

1. Ensuite, vous pouvez soit ajouter des groupes de champs à la source de données intégrée (voir [cette page](../datasource/adobe-experience-platform-data-source.md)), soit créer une source de données externe (voir [cette page](../datasource/external-data-sources.md)) et les groupes de champs associés (voir [cette page](../datasource/field-groups.md)).

   ![](../assets/journey23.png)

1. Cliquez sur **[!UICONTROL Enregistrer]**.

   La source de données est maintenant configurée et prête à être utilisée dans vos parcours.
