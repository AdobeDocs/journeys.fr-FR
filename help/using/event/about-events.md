---
title: A propos des événements
description: Découvrez comment configurer un événement
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


# A propos des événements {#concept_gfj_fqt_52b}

Un événement est lié à une personne. Il s&#39;agit du comportement d&#39;une personne (par exemple, une personne a acheté un produit, a visité un magasin, est sortie d&#39;un site Web, etc.) ou un élément lié à une personne (par exemple, une personne a atteint 10 000 points de fidélité). C&#39;est ce que Journey Orchestration écoutera dans les voyages pour orchestrer les meilleures actions suivantes.

Cette configuration est **obligatoire**, car Journey Orchestration est conçu pour écouter les événements et toujours effectué par un utilisateur **** technique.

La configuration des événements vous permet de définir les informations que l&#39;orchestration du voyage recevra en tant qu&#39;événements. Vous pouvez utiliser plusieurs événements (à différentes étapes d’un voyage) et plusieurs voyages peuvent utiliser le même événement.

Si vous modifiez un événement utilisé dans un brouillon ou un voyage en direct, vous pouvez uniquement modifier le nom, la description ou ajouter des champs de charge utile. Nous limitons strictement l&#39;édition des brouillons ou des voyages en direct pour éviter de rompre les voyages.

## Principe général {#section_r1f_xqt_pgb}

Les événements sont des appels d’API POST. Les événements sont envoyés à la plateforme de données Adobe Experience Cloud par le biais des API d’importation en flux continu. La destination URL des événements envoyés via les API de messagerie transactionnelle est appelée &quot;entrée&quot;. La charge utile des événements suit le formatage XDM.

La charge utile contient les informations requises par les API de gestion en flux continu pour fonctionner (dans l’en-tête) et les informations requises par l’orchestration du voyage pour fonctionner (l’ID d’événement, une partie du corps de la charge) ainsi que les informations à utiliser dans les voyages (dans le corps, par exemple, la quantité d’un panier abandonné). Il existe deux modes pour l’assimilation en flux continu : authentifié et non authentifié. Pour plus d&#39;informations sur les API d&#39;importation en flux continu, consultez [ce lien](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/getting_started_with_platform_streaming_ingestion.md).

Une fois les API de gestion en flux continu envoyées, les événements se propagent dans un service interne appelé Pipeline, puis dans la plateforme de données. Si l’indicateur Service de profil du client en temps réel est activé pour le schéma d’événement et qu’un ID de jeu de données est également associé à l’indicateur Profil du client en temps réel, il est transféré dans le service de profil du client en temps réel.

Le pipeline filtre les événements qui ont une charge utile contenant les identifiants d’événement Journey Orchestration (voir le processus de création d’événement ci-dessous) fournis par Journey Orchestration et contenus dans la charge utile d’événement. Ces événements sont écoutés par Journey Orchestration et le voyage correspondant est déclenché.

## Creating a new event {#section_tbk_5qt_pgb}

Voici les étapes principales de configuration d’un nouvel événement :

1. Dans le menu supérieur, cliquez sur l&#39;onglet **[!UICONTROL Evénements]**. La liste des événements s’affiche. Voir[](../about/user-interface.md)pour plus d’informations sur l’interface.

   ![](../assets/journey5.png)

1. Click **[!UICONTROL Add]**to create a new event. Le volet de configuration des événements s’ouvre sur le côté droit de l’écran.

   ![](../assets/journey6.png)

1. Entrez le nom de votre événement.

   >[!NOTE]
   >
   >N’utilisez pas d’espaces ni de caractères spéciaux. N’utilisez pas plus de 30 caractères.

1. Ajoutez une description à votre événement. Cette étape est facultative.
1. Définissez le schéma et les champs de charge utile : c’est là que vous sélectionnez les informations sur l’événement (généralement appelées données utiles) que l’orchestration de voyage attend de recevoir. Vous pourrez alors utiliser ces informations dans votre voyage. Voir la section [](../event/defining-the-payload-fields.md).
1. Le nombre de voyages qui utilisent cet événement s’affiche dans le champ **[!UICONTROL Utilisé dans]**. Vous pouvez cliquer sur l&#39;icône**[!UICONTROL  Afficher les voyages]** pour afficher la liste des voyages utilisant cet événement.
1. Ajouter un espace de noms. Cette étape est facultative, mais recommandée car l’ajout d’un espace de noms permet d’exploiter les informations stockées dans le service de profil client en temps réel. Il définit le type de clé dont dispose l’événement. Voir la section [](../event/selecting-the-namespace.md).
1. Définissez la clé : choisissez un champ dans vos champs de charge utile ou définissez une formule pour identifier la personne associée à l’événement. Cette clé est automatiquement configurée (mais peut toujours être modifiée) si vous sélectionnez un espace de noms. En effet, Journey Orchestration sélectionne la clé qui doit correspondre à l’espace de noms (par exemple, si vous sélectionnez un espace de noms de courrier électronique, la clé de courrier électronique est sélectionnée). Voir la section [](../event/defining-the-event-key.md).
1. Ajouter une condition. Cette étape est facultative. Cela permet au système de traiter uniquement les événements qui répondent à la condition. La condition ne peut être basée que sur les informations contenues dans l’événement. Voir la section [](../event/adding-a-condition.md).
1. Cliquez sur **[!UICONTROL Enregistrer]**.

   ![](../assets/journey7.png)

   L’événement est maintenant configuré et prêt à être déposé dans un voyage. Des étapes de configuration supplémentaires sont requises pour recevoir les événements. Voir la section [](../event/additional-steps-to-send-events-to-journey-orchestration.md).
