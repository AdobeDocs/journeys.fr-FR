---
title: Configuration de la source de données
description: Découvrez comment configurer la source de données pour le cas d’utilisation simple de parcours
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
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 100%

---


# Configuration de la source de données{#concept_ax3_bcy_w2b}

Dans notre cas d’utilisation, nous voulons utiliser des données de personnalisation pour nos messages. Nous devons aussi vérifier si la personne est une femme. Ces informations sont stockées dans la base de données des profils clients en temps réel. Un **utilisateur technique** doit vérifier que ces champs sont définis dans la source de données Experience Platform intégrée.

Pour plus d’informations sur la configuration des sources de données, reportez-vous à la section [](../datasource/about-data-sources.md).

1. Dans le menu supérieur, cliquez sur l’onglet **[!UICONTROL Sources de données]** et sélectionnez la source de données Experience Platform intégrée.

   ![](../assets/journey23.png)

1. Dans les groupes de champs, vérifiez que les champs suivants sont sélectionnés :

   * _person > name > firstName_
   * _person > name > lastName_
   * _person > gender_
   * _personalEmail > address_

1. Cliquez sur **[!UICONTROL Enregistrer]**.

La source de données est maintenant configurée et prête à être utilisée dans votre parcours.
