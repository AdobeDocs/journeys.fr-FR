---
title: A propos de la configuration des actions personnalisées
description: Découvrez comment configurer une action personnalisée
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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# A propos de la configuration des actions personnalisées {#concept_sxy_bzs_dgb}

Si vous utilisez un système tiers pour envoyer des messages ou si vous souhaitez que l’orchestration Journey envoie des appels d’API à un système tiers, vous configurez sa connexion à l’orchestration Journey. L’action personnalisée définie par les utilisateurs techniques sera alors disponible dans la palette de gauche de votre voyage, dans la catégorie **[!UICONTROL Action]**(voir[](../building-journeys/about-action-activities.md). Voici quelques exemples de systèmes auxquels vous pouvez vous connecter avec des actions personnalisées : Epsilon, Facebook, Adobe.io, Firebase, etc.
Les restrictions sont répertoriées ici :[](../action/custom-action-limitations.md).

Voici les étapes principales requises pour configurer une action personnalisée :

1. Dans la liste **[!UICONTROL Actions]**, cliquez sur**[!UICONTROL  Ajouter]** pour créer une action. Le volet de configuration des actions s’ouvre sur le côté droit de l’écran.

   ![](../assets/custom2.png)

1. Entrez le nom de votre action.

   >[!NOTE]
   >
   >N’utilisez pas d’espaces ni de caractères spéciaux. N’utilisez pas plus de 30 caractères.

1. Ajoutez une description à votre action. Cette étape est facultative.
1. Le nombre de voyages qui utilisent cette action est affiché dans le champ **[!UICONTROL Utilisé dans]**. Vous pouvez cliquer sur le bouton**[!UICONTROL  Afficher les voyages]** pour afficher la liste des voyages utilisant cette action.
1. Définissez les différents paramètres de configuration **[!UICONTROL des]**URL. Voir la section[](../action/url-configuration.md).
1. Configurez la section **[!UICONTROL Authentification]**. Cette configuration est la même que pour les sources de données.  Voir la section[](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Définissez les paramètres ****Message. Voir la section[](../action/defining-the-message-parameters.md).
1. Cliquez sur **[!UICONTROL Enregistrer]**.

   L’action personnalisée est maintenant configurée et prête à être utilisée dans vos voyages. Voir la section [](../building-journeys/about-action-activities.md).

   >[!NOTE]
   >
   >Lorsqu’une action personnalisée est utilisée dans une version de voyage, la plupart des paramètres sont en lecture seule. Vous pouvez uniquement modifier les champs Nom et Description.
