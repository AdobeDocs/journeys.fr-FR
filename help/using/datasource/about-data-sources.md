---
title: A propos des sources de données
description: 'Découvrez comment configurer une source de données '
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# A propos des sources de données {#concept_s1s_dqt_52b}

La configuration de la source de données est toujours effectuée par un utilisateur **** technique.

La configuration de la source de données vous permet de définir une connexion à un système afin de récupérer des informations supplémentaires qui seront utilisées dans vos voyages, par exemple :

* définition de condition
* données de paramètres et de personnalisation dans les actions
* définition d’attente personnalisée
* définition de fuseau horaire personnalisé

Cette configuration n’est pas requise si vos voyages utilisent uniquement les données locales provenant d’une charge utile d’événement. Par exemple, si votre voyage est composé d’un événement suivi d’une activité de courrier électronique qui utilise uniquement les données de l’événement, il n’est pas nécessaire de configurer une source de données.

Il existe deux types de sources de données :

* Source de données de la plateforme d’expérience préconfigurée qui définit la connexion au service de profil client en temps réel. Il s’agit d’une source de données intégrée. Voir la section [](../datasource/adobe-experience-platform-data-source.md).
* Sources de données externes qui vous permettent de définir une connexion à des systèmes externes. Ce sont celles que vous pouvez créer. Voir la section [](../datasource/external-data-sources.md).

Pour chaque source de données, vous définissez les informations à récupérer à l’aide de groupes de champs. Voir la section [](../datasource/field-groups.md).

Voici les principales étapes de configuration de la source de données :

1. Dans le menu supérieur, cliquez sur l’onglet Sources **[!UICONTROL de]**données.

   La liste des sources de données s’affiche. Voir [](../about/user-interface.md) pour plus d’informations sur l’interface.

   ![](../assets/journey18.png)

1. Vous pouvez ensuite ajouter des groupes de champs à la source de données intégrée (voir [](../datasource/adobe-experience-platform-data-source.md)) ou créer une source de données externe (voir [](../datasource/external-data-sources.md)) et des groupes de champs associés (voir [](../datasource/field-groups.md)).

   ![](../assets/journey23.png)

1. Cliquez sur **[!UICONTROL Enregistrer]**.

   La source de données est maintenant configurée et prête à être utilisée dans vos voyages.
