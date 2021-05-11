---
product: adobe campaign
solution: Journey Orchestration
title: Configuration de la source de données
description: Découvrez comment configurer la source de données pour le cas d’utilisation simple de parcours
feature: Parcours
role: Business Practitioner
level: Intermediate
exl-id: 87f63d7d-b7d9-4243-a5ce-8948939f3d93
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 100%

---

# Configuration de la source de données{#concept_ax3_bcy_w2b}

Dans notre cas d’utilisation, nous voulons utiliser des données de personnalisation pour nos messages. Nous devons aussi vérifier si la personne est une femme. Ces informations sont stockées dans la base de données des profils clients en temps réel. Un **utilisateur technique** doit vérifier que ces champs sont définis dans la source de données Adobe Experience Platform intégrée.

Pour plus d’informations sur la configuration des sources de données, consultez [cette page](../datasource/about-data-sources.md).


1. Dans le menu supérieur, cliquez sur l’onglet **[!UICONTROL Sources de données]** et sélectionnez la source de données Adobe Experience Platform intégrée.

   ![](../assets/journey23.png)

1. Dans les groupes de champs, vérifiez que les champs suivants sont sélectionnés :

   * _person > name > firstName_
   * _person > name > lastName_
   * _person > gender_
   * _personalEmail > address_

1. Cliquez sur **[!UICONTROL Enregistrer]**.

La source de données est maintenant configurée et prête à être utilisée dans votre parcours.
