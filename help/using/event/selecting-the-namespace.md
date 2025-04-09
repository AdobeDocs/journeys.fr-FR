---
product: adobe campaign
title: Sélection de l’espace de noms
description: Découvrez comment sélectionner l’espace de noms
feature: Journeys
role: User
level: Intermediate
exl-id: 976c6353-797e-40cc-bb90-5d82381bb903
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 81%

---

# Sélection de l’espace de noms {#concept_ckb_3qt_52b}


>[!CAUTION]
>
>**Vous recherchez Adobe Journey Optimizer** ? Cliquez [ici](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/ajo-home){target="_blank"} pour accéder à la documentation de Journey Optimizer.
>
>
>_Cette documentation se rapporte aux anciens contenus de Journey Orchestration qui ont été remplacés par Journey Optimizer. Pour toute question concernant votre accès à Journey Orchestration ou Journey Optimizer, veuillez contacter votre équipe de compte._


Un espace de noms vous permet de définir le type de clé utilisé pour identifier la personne associée à l&#39;événement. Sa configuration est facultative. Elle est obligatoire si vous souhaitez récupérer, dans vos parcours, des informations supplémentaires provenant de [profil client en temps réel](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=fr). Il n&#39;est pas nécessaire de définir l&#39;espace de noms si vous utilisez uniquement des données provenant d&#39;un système tiers via une source de données personnalisée.

Vous pouvez utiliser l&#39;un des espaces de noms prédéfinis ou en créer un à l&#39;aide du service Espace de noms d&#39;identité. Voir cette [page](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=fr).

Si vous sélectionnez un schéma doté d&#39;une identité principale, les champs **[!UICONTROL Clé]** et **[!UICONTROL Espace de noms]** sont déjà renseignés. Si aucune identité n&#39;est définie, _identityMap > id_ est sélectionné comme clé principale. Vous devez ensuite sélectionner un espace de noms et la clé sera préremplie (sous le champ **[!UICONTROL Espace de noms]**) à l&#39;aide de _identityMap > id_.

Lors de la sélection de champs, les champs d&#39;identité principale sont balisés.

![](../assets/primary-identity.png)


Sélectionnez un espace de noms dans la liste déroulante.

![](../assets/journey17.png)

Un seul espace de noms est autorisé par parcours. Si vous utilisez plusieurs événements dans le même parcours, ils doivent utiliser le même espace de noms. Voir [cette page](../building-journeys/journey.md).
