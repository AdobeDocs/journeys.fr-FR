---
title: Définition de la clé d’événement
description: Découvrez comment définir la clé d'événement
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


# Définition de la clé d’événement {#concept_ond_hqt_52b}

La clé est le champ ou la combinaison de champs fait partie des données de charge utile de l’événement et permet au système d’identifier la personne associée à l’événement. La clé peut être, par exemple, l’ID Experience Cloud, un ID CRM ou une adresse électronique.

Si vous prévoyez d’exploiter les données stockées dans la base de données Profil du client en temps réel, vous devez sélectionner, en tant que clé d’événement, les informations que vous avez définies comme identité d’un profil dans le service [Profil du client en temps](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md)réel.

Il permettra au système d&#39;effectuer le rapprochement entre l&#39;événement et le profil de la personne. Si vous sélectionnez un schéma doté d’une identité principale, les champs **[!UICONTROL Clé]**et**[!UICONTROL  Espace de noms]** sont préremplis. Si aucune identité n’est définie, nous sélectionnons _identityMap > id_ comme clé principale. Ensuite, vous devez sélectionner un espace de noms et la clé sera préremplie (sous le champ **[!UICONTROL Espace]**de noms) à l’aide de _IdentityMap > id_.

Si vous devez utiliser une autre clé, telle qu’un ID CRM ou une adresse électronique, vous devez l’ajouter manuellement :

1. Cliquez dans le champ **[!UICONTROL Clé]**ou sur l’icône représentant un crayon.

   ![](../assets/journey16.png)

1. Sélectionnez le champ choisi comme clé dans la liste des champs de charge utile. Vous pouvez également passer à l’éditeur d’expression avancé pour créer des clés plus complexes (par exemple, une concaténation de deux champs des événements). Voir ci-dessous, dans cette section.

   ![](../assets/journey20.png)

Lorsque l&#39;événement est reçu, la valeur de la clé permet au système d&#39;identifier la personne associée à l&#39;événement. Associée à un espace de noms (voir [](../event/selecting-the-namespace.md)), la clé peut être utilisée pour effectuer des requêtes sur Adobe Experience Platform. Voir la section [](../building-journeys/about-orchestration-activities.md).
La clé est également utilisée pour vérifier qu&#39;une personne est en voyage. En effet, une personne ne peut se trouver à deux endroits différents dans le même voyage. Par conséquent, le système ne permet pas à la même clé, par exemple la clé CRMID=3224, d’être à différents endroits du même voyage.

Vous avez également accès aux fonctions d’expression avancées (mode ****avancé) si vous souhaitez effectuer des manipulations supplémentaires. Ces fonctions vous permettent de manipuler les valeurs utilisées pour exécuter des requêtes spécifiques, telles que des formats de modification, des concaténations de champs, en ne prenant en compte qu’une partie d’un champ (par exemple, les 10 premiers caractères). Voir la section[](../expression/expressionadvanced.md).
