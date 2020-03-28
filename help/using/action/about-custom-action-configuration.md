---
title: À propos de la configuration des actions personnalisées
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
source-git-commit: e53ecd96bbb308fe109843de6f64cde4cba5e246

---


# À propos de la configuration des actions personnalisées {#concept_sxy_bzs_dgb}

Si vous utilisez un système tiers pour envoyer des messages ou si vous souhaitez que Journey Orchestration envoie des appels d’API à un système tiers, vous devez configurer la connexion de ce système à la solution. L’action personnalisée définie par les utilisateurs techniques sera alors disponible dans la palette de gauche du parcours, dans la catégorie **[!UICONTROL Action]** (voir [](../building-journeys/about-action-activities.md)). À titre d’exemple, Epsilon, Facebook, Adobe.io, Firebase, etc. sont des systèmes auxquels vous pouvez vous connecter à l’aide d’actions personnalisées : 
Les restrictions sont répertoriées ici : [](../action/custom-action-limitations.md).

Les principales étapes nécessaires pour configurer une action personnalisée sont les suivantes :

1. From the **[!UICONTROL Actions]** list, click **[!UICONTROL Add]** to create a new action. Le volet de configuration des actions s’ouvre dans la droite de l’écran.

   ![](../assets/custom2.png)

1. Saisissez le nom de l’action.

   >[!NOTE]
   >
   >N’utilisez ni espaces ni caractères spéciaux. Utilisez 30 caractères au maximum.

1. Ajoutez une description à l’action. Cette étape est facultative.
1. The number of journeys that use this action is displayed in the **[!UICONTROL Used in]** field. You can click the **[!UICONTROL View journeys]** button to display the list of  journeys using this action.
1. Définissez les différents **[!UICONTROL URL Configuration]** paramètres. Voir [](../action/url-configuration.md).
1. Configurez la **[!UICONTROL Authentication]** section. Cette configuration est la même que pour les sources de données.  Voir [](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Définissez le **[!UICONTROL Message parameters]**. Voir [](../action/defining-the-message-parameters.md).
1. Clics **[!UICONTROL Save]**.

   L’action personnalisée est maintenant configurée et prête à être utilisée dans vos parcours. Voir [](../building-journeys/about-action-activities.md).

   >[!NOTE]
   >
   >Lorsqu’une action personnalisée est utilisée dans un voyage, la plupart des paramètres sont en lecture seule. Vous pouvez uniquement modifier les champs **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** et la **[!UICONTROL Authentication]** section.
