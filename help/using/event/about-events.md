---
title: À propos des événements
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
source-git-commit: e579936cfe5eb43caf72627004f98a5746c7abb1
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 98%

---


# À propos des événements {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="À propos des événements"
>abstract="Un événement est associé à une personne. Il décrit son comportement (par exemple, cette personne a acheté un produit, a visité un magasin, a quitté un site web, etc.) ou un événement qui s’est produit en rapport avec cette personne (par exemple, elle a accumulé 10 000 points de fidélité). C’est ce type d’élément que Journey Orchestration écoute dans les parcours pour orchestrer les meilleures actions qu’il convient de prendre ensuite."

Un événement est associé à une personne. Il décrit son comportement (par exemple, cette personne a acheté un produit, a visité un magasin, a quitté un site web, etc.) ou un événement qui s’est produit en rapport avec cette personne (par exemple, elle a accumulé 10 000 points de fidélité). C’est ce type d’élément que Journey Orchestration écoute dans les parcours pour orchestrer les meilleures actions qu’il convient de prendre ensuite.

Cette configuration est **obligatoire**, dans la mesure où Journey Orchestration est conçu pour « écouter » les événements. Elle est toujours effectuée par un **utilisateur technique**.

La configuration d’événement vous permet de définir les informations que Journey Orchestration recevra en tant qu’événements. Vous pouvez utiliser plusieurs événements (à différentes étapes d’un parcours) et plusieurs parcours peuvent utiliser un même événement.

Si vous modifiez un événement utilisé dans un parcours actif ou dans un état de brouillon, vous pouvez uniquement en modifier le nom ou la description, ou ajouter des champs de payload. La modification des parcours actifs ou dans un état de brouillon est strictement limitée pour éviter de les interrompre.

## Principe général {#section_r1f_xqt_pgb}

Les événements sont des appels d’API POST. Ils sont envoyés à Adobe Experience Cloud Data Platform par le biais des API d’ingestion en flux continu. L’URL de destination des événements envoyés via les API de messagerie transactionnelle est appelée « inlet ». La payload des événements respecte la mise en forme XDM.

La payload contient les informations nécessaires au fonctionnement des API d’ingestion en flux continu (dans l’en-tête) et de Journey Orchestration (l’identifiant d’événement, un élément du corps de la payload), ainsi que des informations à utiliser dans les parcours (dans le corps, par exemple, le montant d’un panier abandonné). Il existe deux modes d’ingestion en flux continu : authentifié et non authentifié. Pour plus d’informations sur les API d’ingestion en flux continu, cliquez sur [ce lien](https://docs.adobe.com/content/help/en/experience-platform/xdm/api/getting-started.html).

Après avoir transité par les API d’ingestion en flux continu, les événements se propagent dans un service interne appelé Pipeline, puis dans Data Platform. Si l’indicateur du service de profil client en temps réel est activé pour le schéma d’événement et que ce dernier comprend également un identifiant de jeu de données avec l’indicateur de profil client en temps réel, le schéma est propagé dans ce service.

Le service Pipeline filtre les événements avec une payload contenant les eventID de Journey Orchestration (reportez-vous au processus de création d’événements ci-dessous) fournis par Journey Orchestration et contenus dans une payload d’événement. Ces événements sont écoutés par Journey Orchestration et le parcours correspondant est déclenché.

## Création d’un événement {#section_tbk_5qt_pgb}

Les principales étapes nécessaires pour configurer un nouvel événement sont les suivantes :

1. Dans le menu supérieur, cliquez sur l’onglet **[!UICONTROL Événements]**. La liste des événements s’affiche. Pour plus d’informations sur l’interface, voir [](../about/user-interface.md).

   ![](../assets/journey5.png)

1. Cliquez sur le bouton **[!UICONTROL Ajouter]** pour créer un événement. Le volet de configuration d’événement s’ouvre dans la partie droite de l’écran.

   ![](../assets/journey6.png)

1. Saisissez le nom de votre événement.

   >[!NOTE]
   >
   >N’utilisez ni espaces ni caractères spéciaux. Utilisez 30 caractères au maximum.

1. Ajoutez une description à l’événement. Cette étape est facultative.
1. Définissez les champs de payload et de schéma : c’est dans ces champs que vous sélectionnez les informations d’événement (désignées généralement sous le nom de payload) que Journey Orchestration s’attend à recevoir. Vous pourrez alors utiliser ces informations dans votre parcours. Voir [](../event/defining-the-payload-fields.md).
1. Le nombre de parcours qui font appel à cet événement apparaît dans le champ **[!UICONTROL Utilisé(e) dans]**. Vous pouvez cliquer sur l’icône **[!UICONTROL Afficher les parcours]** pour faire apparaître la liste des parcours utilisant cet événement.
1. Ajoutez un namespace. Cette étape est facultative, mais recommandée. En effet, l’ajout d’un namespace permet d’exploiter les informations stockées dans le service de profil client en temps réel. Il définit le type de clé dont dispose l’événement. Voir [](../event/selecting-the-namespace.md).
1. Définissez la clé : effectuez votre choix parmi vos champs de payload ou définissez une formule pour identifier la personne associée à l’événement. Cette clé est configurée automatiquement (mais peut toujours être modifiée) si vous sélectionnez un namespace. En effet, Journey Orchestration sélectionne la clé qui doit correspondre au namespace ; par exemple, si vous sélectionnez un namespace d’email, la clé d’email est sélectionnée. Voir [](../event/defining-the-event-key.md).
1. Ajoutez une condition. Cette étape est facultative. Elle permet au système de traiter uniquement les événements qui répondent à la condition. Cette condition ne peut être basée que sur les informations contenues dans l’événement. Voir [](../event/adding-a-condition.md).
1. Cliquez sur **[!UICONTROL Enregistrer]**.

   ![](../assets/journey7.png)

   L’événement est maintenant configuré et prêt à être déposé dans un parcours. Des étapes de configuration supplémentaires sont requises pour la réception d’événements. Voir [](../event/additional-steps-to-send-events-to-journey-orchestration.md).
