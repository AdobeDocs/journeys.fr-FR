---
title: Sélection du namespace
description: Découvrez comment sélectionner le namespace
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

---


# Sélection du namespace {#concept_ckb_3qt_52b}

Un namespace vous permet de définir le type de clé utilisé pour identifier la personne associée à l’événement. Sa configuration est facultative. Elle est obligatoire si vous souhaitez récupérer, dans vos parcours, des informations supplémentaires provenant de [profil client en temps réel](https://docs.adobe.com/content/help/en/experience-platform/profile/home.html). Il n’est pas nécessaire de définir le namespace si vous utilisez uniquement des données provenant d’un système tiers via une source de données personnalisée.

Vous pouvez utiliser l’un des namespaces prédéfinis ou en créer un à l’aide du service Identity Namespace. À ce propos, consultez cette [page](https://docs.adobe.com/content/help/en/experience-platform/identity/home.html).

If you select a schema that has a primary identity, then the **[!UICONTROL Key]** and **[!UICONTROL Namespace]** fields are pre-filled. Si aucune identité n’est définie, _identityMap > id_ est sélectionné comme clé principale. Vous devez ensuite sélectionner un et la clé sera préremplie (sous le champ **[!UICONTROL Namespace]** Namespace) à l’aide de _identityMap > id_.

Lors de la sélection de champs, les champs d’identité principale sont balisés.

![](../assets/primary-identity.png)


Sélectionnez un namespace dans la liste déroulante.

![](../assets/journey17.png)

Un seul namespace est autorisé par parcours. Si vous utilisez plusieurs événements dans le même parcours, tous doivent utiliser le même namespace. Voir [](../building-journeys/journey.md).
