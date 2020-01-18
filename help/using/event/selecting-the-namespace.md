---
title: Sélection de l’espace de noms
description: Découvrez comment sélectionner l’espace de noms
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


# Sélection de l’espace de noms {#concept_ckb_3qt_52b}

L’espace de noms vous permet de définir le type de clé utilisé pour identifier la personne associée à l’événement. Sa configuration est facultative. Elle est requise si vous souhaitez récupérer, dans vos voyages, des informations supplémentaires provenant du profil [client en temps](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md)réel. La définition de l’espace de noms n’est pas nécessaire si vous utilisez uniquement des données provenant d’un système tiers via une source de données personnalisée.

Vous pouvez utiliser l’un des paramètres prédéfinis ou en créer un nouveau à l’aide du service Identity Namespace. Refer to this [page](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/identity_namespace_overview/identity_namespace_overview.md).

Si vous sélectionnez un schéma doté d’une identité principale, les champs **[!UICONTROL Clé]**et**[!UICONTROL  Espace de noms]** sont préremplis. Si aucune identité n’est définie, nous sélectionnons _identityMap > id_ comme clé principale. Ensuite, vous devez sélectionner un espace de noms et la clé sera préremplie (sous le champ **[!UICONTROL Espace]**de noms) à l’aide de _IdentityMap > id_.

Sélectionnez un espace de noms dans la liste déroulante.

![](../assets/journey17.png)

Un seul espace de noms est autorisé par voyage. Si vous utilisez plusieurs événements dans le même parcours, ils doivent utiliser le même espace de noms. Voir la section [](../building-journeys/journey.md).
