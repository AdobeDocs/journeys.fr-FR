---
product: adobe campaign
solution: Journey Orchestration
title: Prise en main
description: Découvrez les étapes principales pour configurer Journey Orchestration et créer votre premier parcours.
translation-type: ht
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: ht
source-wordcount: '322'
ht-degree: 100%

---


# Prise en main{#concept_y4b_4qt_52b}

Dans [!DNL Journey Orchestration], il existe deux types d’utilisateurs, chacun d’eux effectuant des tâches spécifiques : l’**utilisateur technique** et l’**utilisateur chargé de la conception de parcours**. Les profils de produit et les droits servent à gérer les accès des utilisateurs. Consultez [cette page](../about/access-management.md) pour découvrir comment configurer les accès des utilisateurs.

Les principales étapes pour configurer et utiliser [!DNL Journey Orchestration] sont les suivantes :

1. **Configurer un événement**

   Vous devez définir les informations attendues et comment les traiter. Cette configuration est obligatoire. Cette étape est effectuée par un **utilisateur technique**.

   Consultez [cette page](../event/about-events.md) pour plus d’informations.

   ![](../assets/journey7.png)

1. **Configurer la source de données**

   Vous devez définir une connexion à un système pour récupérer des informations supplémentaires qui seront utilisées pour vos parcours, par exemple dans vos conditions. Une source de données Adobe Experience Platform intégrée est également définie au moment de l’approvisionnement. Cette étape n’est pas obligatoire si vous n’exploitez que les données des événements de votre parcours. Elle est effectuée par un **utilisateur technique**.

   Consultez [cette page](../datasource/about-data-sources.md) pour plus d’informations à ce sujet.

   ![](../assets/journey22.png)

1. **Configurer une action**

   Si vous utilisez un système tiers pour envoyer vos messages, vous devez configurer sa connexion à [!DNL Journey Orchestration]. Voir [cette page](../action/about-custom-action-configuration.md).

   Si vous utilisez Adobe Campaign Standard pour envoyer des messages, vous devez configurer l’action intégrée. Voir [cette page](../action/working-with-adobe-campaign.md).

   Ces étapes sont effectuées par un **utilisateur technique**.

   ![](../assets/custom2.png)

1. **Concevoir le parcours**

   Combinez les différentes activités d’événement, d’orchestration et d’action afin de créer des scénarios cross-canal à plusieurs étapes. Cette étape est effectuée par un **utilisateur chargé de la conception de parcours**.

   Voir à ce propos [cette page](../building-journeys/journey.md).

   ![](../assets/journeyuc2_24.png)

1. **Tester et publier le parcours**

   Vous devez valider et activer le parcours. Cette étape est effectuée par un **utilisateur chargé de la conception de parcours**.

   Pour en savoir plus, consultez les pages [Test du parcours](../building-journeys/testing-the-journey.md) et [Publication du parcours](../building-journeys/publishing-the-journey.md).

   ![](../assets/journeyuc2_32bis.png)

1. **Suivre le parcours**

   Utilisez les outils de reporting dédiés pour mesurer l’efficacité du parcours. Cette étape est effectuée par un **utilisateur chargé de la conception de parcours**.

   Voir à ce propos [cette page](../reporting/about-journey-reports.md).

   ![](../assets/dynamic_report_journey_12.png)

