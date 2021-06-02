---
product: adobe campaign
title: Sélection de l’espace de noms
description: Découvrez comment sélectionner l’espace de noms
feature: Parcours
role: Business Practitioner
level: Intermediate
exl-id: 976c6353-797e-40cc-bb90-5d82381bb903
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 100%

---

# Sélection de l’espace de noms {#concept_ckb_3qt_52b}

Un espace de noms vous permet de définir le type de clé utilisé pour identifier la personne associée à l’événement. Sa configuration est facultative. Elle est obligatoire si vous souhaitez récupérer, dans vos parcours, des informations supplémentaires provenant de [profil client en temps réel](https://docs.adobe.com/content/help/fr-FR/experience-platform/profile/home.html). Il n’est pas nécessaire de définir l’espace de noms si vous utilisez uniquement des données provenant d’un système tiers via une source de données personnalisée.

Vous pouvez utiliser l’un des espaces de noms prédéfinis ou en créer un à l’aide du service Espace de noms d’identité. Voir cette [page](https://docs.adobe.com/content/help/fr-FR/experience-platform/identity/home.html).

Si vous sélectionnez un schéma doté d’une identité principale, les champs **[!UICONTROL Clé]** et **[!UICONTROL Espace de noms]** sont déjà renseignés. Si aucune identité n’est définie, _identityMap > id_ est sélectionné comme clé principale. Vous devez ensuite sélectionner un espace de noms et la clé sera préremplie (sous le champ **[!UICONTROL Espace de noms]**) à l’aide de _identityMap > id_.

Lors de la sélection de champs, les champs d’identité principale sont balisés.

![](../assets/primary-identity.png)


Sélectionnez un espace de noms dans la liste déroulante.

![](../assets/journey17.png)

Un seul espace de noms est autorisé par parcours. Si vous utilisez plusieurs événements dans le même parcours, tous doivent utiliser le même espace de noms. Voir [cette page](../building-journeys/journey.md).
