---
title: Prise en main
description: Commencer avec l'orchestration Journey
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


# Prise en main{#concept_y4b_4qt_52b}

Dans Journey Orchestration, il existe deux types d’utilisateurs, chacun exécutant des tâches spécifiques : l’utilisateur **** technique et l’utilisateur **** professionnel. L’accès utilisateur est géré par le biais des profils de produit et des droits. Reportez-vous [](../about/access-management.md) à pour savoir comment configurer l’accès utilisateur.

Voici les étapes principales pour configurer et utiliser Journey Orchestration :

1. **Configurer un événement**

   Vous devez définir les informations attendues et comment les traiter. Cette configuration est obligatoire. Cette étape est effectuée par un utilisateur **** technique.

   Voir à ce sujet la section [](../event/about-events.md).

   ![](../assets/journey7.png)

1. **Configuration de la source de données**

   Vous devez définir une connexion à un système pour récupérer des informations supplémentaires qui seront utilisées dans vos voyages, par exemple dans vos conditions. Une source de données de plateforme d’expérience intégrée est également configurée au moment de la mise en service. Cette étape n’est pas requise si vous exploitez uniquement les données des événements de votre voyage. Cette étape est effectuée par un utilisateur **** technique.

   Voir à ce sujet la section [](../datasource/about-data-sources.md).

   ![](../assets/journey22.png)

1. **Configuration d’une action**

   Si vous utilisez un système tiers pour envoyer vos messages, vous devez configurer sa connexion avec Journey Orchestration. Voir la section [](../action/about-custom-action-configuration.md).

   Si vous utilisez Adobe Campaign Standard pour envoyer des messages, vous devez configurer l’action intégrée. Voir la section [](../action/working-with-adobe-campaign.md).

   Ces étapes sont effectuées par un utilisateur **** technique.

   ![](../assets/custom2.png)

1. **Concevez votre voyage**

   Combinez les différentes activités d’événement, d’orchestration et d’action pour créer vos scénarios multicanaux. Cette étape est effectuée par un utilisateur **** professionnel.

   Pour plus d&#39;informations à ce sujet, voir [](../building-journeys/journey.md).

   ![](../assets/journeyuc2_24.png)

1. **Test et publication du voyage**

   Vous devez valider et activer le voyage. Cette étape est effectuée par un utilisateur **** professionnel.

   For more on this, see [](../building-journeys/testing-the-journey.md) and [](../building-journeys/publishing-the-journey.md).

   ![](../assets/journeyuc2_32bis.png)

1. **Surveillez votre voyage**

   Utilisez les outils de création de rapports dédiés pour mesurer l&#39;efficacité de votre voyage. Cette étape est effectuée par un utilisateur **** professionnel.

   Pour plus d&#39;informations à ce sujet, voir [](../reporting/about-journey-reports.md).

   ![](../assets/dynamic_report_journey_12.png)

