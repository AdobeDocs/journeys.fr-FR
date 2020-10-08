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
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 100%

---


# À propos de la configuration des actions personnalisées {#concept_sxy_bzs_dgb}

Si vous utilisez un système tiers pour envoyer des messages ou si vous souhaitez que [!DNL Journey Orchestration] envoie des appels d’API à un système tiers, vous devez configurer la connexion de ce système à [!DNL Journey Orchestration]. L’action personnalisée définie par les utilisateurs techniques sera alors disponible dans la palette de gauche du parcours, dans la catégorie **[!UICONTROL Action]** (voir [](../building-journeys/about-action-activities.md)). À titre d’exemple, Epsilon, Facebook, Adobe.io, Firebase, etc. sont des systèmes auxquels vous pouvez vous connecter à l’aide d’actions personnalisées : 
Les restrictions sont répertoriées ici : [](../action/custom-action-limitations.md).

Les principales étapes nécessaires pour configurer une action personnalisée sont les suivantes :

1. Dans la liste **[!UICONTROL Actions]**, cliquez sur **[!UICONTROL Ajouter]** pour créer une action. Le volet de configuration des actions s’ouvre dans la droite de l’écran.

   ![](../assets/custom2.png)

1. Saisissez le nom de l’action.

   >[!NOTE]
   >
   >N’utilisez ni espaces ni caractères spéciaux. Utilisez 30 caractères au maximum.

1. Ajoutez une description à l’action. Cette étape est facultative.
1. Le nombre de parcours qui font appel à cette action apparaît dans le champ **[!UICONTROL Utilisé(e) dans]**. Vous pouvez cliquer sur le bouton **[!UICONTROL Afficher les parcours]** pour faire apparaître la liste des parcours utilisant cette action.
1. Définissez les différents paramètres de **[!UICONTROL Configuration d’URL]**. Voir [](../action/url-configuration.md).
1. Configurez la section **[!UICONTROL Authentification]**. Cette configuration est la même que pour les sources de données.  Voir [](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Définissez les **[!UICONTROL Paramètres de message]**. Voir [](../action/defining-the-message-parameters.md).
1. Cliquez sur **[!UICONTROL Enregistrer]**.

   L’action personnalisée est maintenant configurée et prête à être utilisée dans vos parcours. Voir [](../building-journeys/about-action-activities.md).

   >[!NOTE]
   >
   >Lorsqu’une action personnalisée est utilisée dans un parcours, la plupart des paramètres sont en lecture seule. Vous ne pouvez modifier que les champs **[!UICONTROL Nom]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** et la section **[!UICONTROL Authentification.]**
