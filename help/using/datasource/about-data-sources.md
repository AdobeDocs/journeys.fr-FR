---
title: À propos des sources de données
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
translation-type: ht
source-git-commit: d0a7bbb43ae62fbdcf7ef34b0b56b1d437047ad2

---


# À propos des sources de données {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id=&quot;jo_datasources&quot;
>title=&quot;À propos des sources de données&quot;
>abstract=&quot;La configuration d’une source de données est toujours effectuée par un utilisateur technique. Elle vous permet de définir une connexion à un système afin de récupérer des informations supplémentaires qui seront utilisées dans vos parcours. Par exemple : définition de conditions, données de paramètres et de personnalisation dans les actions, définition d’attente personnalisée, définition de fuseau horaire personnalisé.&quot;

La configuration d’une source de données est toujours effectuée par un **utilisateur technique**.

Elle vous permet de définir une connexion à un système afin de récupérer des informations supplémentaires qui seront utilisées dans vos parcours. Par exemple :

* Définition d’une condition
* Données de paramètres et de personnalisation dans les actions
* Définition d’une attente personnalisée
* Définition d’un fuseau horaire personnalisé

Cette configuration n’est pas requise si vos parcours utilisent uniquement les données locales provenant d’une payload d’événement. Par exemple, si votre parcours comprend un événement suivi d’une activité d’email qui utilise uniquement les données de l’événement, il n’est pas nécessaire de configurer une source de données.

Il existe deux types de sources de données :

* La source de données Experience Platform préconfigurée qui définit la connexion au service de profil client en temps réel. Il s’agit d’une source de données intégrée. Voir [](../datasource/adobe-experience-platform-data-source.md).
* Les sources de données externes qui vous permettent de définir une connexion à des systèmes externes. Il s’agit des sources de données que vous pouvez créer. Voir [](../datasource/external-data-sources.md).

Pour chaque source de données, vous définissez les informations à récupérer à l’aide de groupes de champs. Voir [](../datasource/field-groups.md).

Les principales étapes de configuration d’une source de données sont les suivantes :

1. Dans le menu supérieur, cliquez sur l’onglet **[!UICONTROL Sources de données]**.

   La liste des sources de données s’affiche. Pour plus d’informations sur l’interface, voir [](../about/user-interface.md).

   ![](../assets/journey18.png)

1. Ensuite, vous pouvez soit ajouter des groupes de champs à la source de données intégrée (voir [](../datasource/adobe-experience-platform-data-source.md)), soit créer une source de données externe (voir [](../datasource/external-data-sources.md)) et les groupes de champs associés (voir [](../datasource/field-groups.md)).

   ![](../assets/journey23.png)

1. Cliquez sur **[!UICONTROL Enregistrer]**.

   La source de données est maintenant configurée et prête à être utilisée dans vos parcours.
