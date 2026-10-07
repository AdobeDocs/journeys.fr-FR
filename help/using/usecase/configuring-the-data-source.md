---
product: adobe campaign
title: Configuration de la source de données
description: Découvrez comment configurer la source de données pour le cas d’utilisation simple de parcours
feature: Journeys
role: User
level: Intermediate
exl-id: 87f63d7d-b7d9-4243-a5ce-8948939f3d93
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 100%
---
# Configuration de la source de données{#concept_ax3_bcy_w2b}


>[!CAUTION]
>
>**Vous recherchez Adobe Journey Optimizer** ? Cliquez [ici](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/ajo-home){target="_blank"} pour consulter la documentation de Journey Optimizer.
>
>
>_Cette documentation se rapporte aux anciens contenus de Journey Orchestration qui ont été remplacés par Journey Optimizer. Pour toute question concernant votre accès à Journey Orchestration ou Journey Optimizer, contactez votre équipe en charge des comptes._


Dans notre cas d’utilisation, nous voulons utiliser des données de personnalisation pour nos messages. Nous devons aussi vérifier si la personne est une femme. Ces informations sont stockées dans la base de données des profils clients en temps réel. Un **utilisateur technique** doit vérifier que ces champs sont définis dans la source de données Adobe Experience Platform intégrée.

Pour plus d’informations sur la configuration des sources de données, consultez [cette page](../datasource/about-data-sources.md).

1. Dans le volet de menus, sélectionnez **[!UICONTROL Admin]**. Dans la section **[!UICONTROL Sources de données]**, cliquez sur **[!UICONTROL Gérer]**.
1. Sélectionnez la source de données Adobe Experience Platform intégrée.

   ![](../assets/journey23.png)

1. Dans les groupes de champs, vérifiez que les champs suivants sont sélectionnés :

   * _person > name > firstName_
   * _person > name > lastName_
   * _person > gender_
   * _personalEmail > address_

1. Cliquez sur **[!UICONTROL Enregistrer]**.

La source de données est maintenant configurée et prête à être utilisée dans votre parcours.
