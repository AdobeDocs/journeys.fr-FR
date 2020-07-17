---
title: Prise en main
description: Prise en main de Journey Orchestration
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 95%

---


# Prise en main{#concept_y4b_4qt_52b}

Dans [!DNL Journey Orchestration], il existe deux types d’utilisateurs, chacun d’eux effectuant des tâches spécifiques : l’**utilisateur technique** et l’**utilisateur chargé de la conception de parcours**. Les profils de produit et les droits servent à gérer les accès des utilisateurs. Reportez-vous à la section [](../about/access-management.md) pour configurer les accès des utilisateurs.

Les principales étapes pour configurer et utiliser [!DNL Journey Orchestration] sont les suivantes :

1. **Configurer un événement**

   Vous devez définir les informations attendues et comment les traiter. Cette configuration est obligatoire. Cette étape est effectuée par un **utilisateur technique**.

   Voir à ce sujet la section [](../event/about-events.md).

   ![](../assets/journey7.png)

1. **Configurer la source de données**

   Vous devez définir une connexion à un système pour récupérer des informations supplémentaires qui seront utilisées pour vos parcours, par exemple dans vos conditions. Une source de données d’Adobe Experience Platform intégrée est également configurée au moment de la mise en service. Cette étape n’est pas obligatoire si vous n’exploitez que les données des événements de votre parcours. Elle est effectuée par un **utilisateur technique**.

   Voir à ce sujet la section [](../datasource/about-data-sources.md).

   ![](../assets/journey22.png)

1. **Configurer une action**

   Si vous utilisez un système tiers pour envoyer vos messages, vous devez configurer sa connexion à [!DNL Journey Orchestration]. Voir [](../action/about-custom-action-configuration.md).

   Si vous utilisez Adobe Campaign Standard pour envoyer des messages, vous devez configurer l’action intégrée. Voir [](../action/working-with-adobe-campaign.md).

   Ces étapes sont effectuées par un **utilisateur technique**.

   ![](../assets/custom2.png)

1. **Concevoir le parcours**

   Combinez les différentes activités d’événement, d’orchestration et d’action afin de créer des scénarios cross-canal à plusieurs étapes. Cette étape est effectuée par un **utilisateur chargé de la conception de parcours**.

   Pour plus d’informations à ce sujet, voir [](../building-journeys/journey.md).

   ![](../assets/journeyuc2_24.png)

1. **Tester et publier le parcours**

   Vous devez valider et activer le parcours. Cette étape est effectuée par un **utilisateur chargé de la conception de parcours**.

   Pour plus d’informations à ce sujet, voir [](../building-journeys/testing-the-journey.md) et [](../building-journeys/publishing-the-journey.md).

   ![](../assets/journeyuc2_32bis.png)

1. **Suivre le parcours**

   Utilisez les outils de reporting dédiés pour mesurer l’efficacité du parcours. Cette étape est effectuée par un **utilisateur chargé de la conception de parcours**.

   Pour plus d’informations à ce sujet, voir [](../reporting/about-journey-reports.md).

   ![](../assets/dynamic_report_journey_12.png)

