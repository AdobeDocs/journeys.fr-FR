---
product: adobe campaign
title: Passage d’un parcours à un autre
description: Passage d’un parcours à un autre
feature: Parcours
role: Business Practitioner
level: Intermediate
exl-id: eaf2c795-0920-4b9c-9f06-801e43c1844b
source-git-commit: 29aa6b6e16f8e6d051065f8157f4e25e8b1c05e1
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 91%

---

# Mettre à jour le profil {#update-profile}

L’activité d’action **[!UICONTROL Mettre à jour le profil]** vous permet de mettre à jour un profil Adobe Experience Platform existant avec des informations provenant de l’événement, d’une source de données ou à l’aide d’une valeur spécifique.

## Remarques importantes

* L’action **Mettre à jour le profil** ne peut être utilisée que dans les parcours commençant par un événement qui possède un espace de noms.
* L’action ne met à jour que les champs existants, elle ne crée pas de nouveaux champs de profil.
* Vous ne pouvez pas utiliser l’action **Mettre à jour le profil** pour générer des événements d’expérience, par exemple un achat.
* Comme toute autre action, vous pouvez définir un itinéraire alternatif en cas d’erreur ou de temporisation, et vous ne pouvez pas placer deux actions en parallèle.
* La requête de mise à jour envoyée à Platform sera rapide mais pas immédiate/ne démarrera pas dans la seconde. Cela prendra normalement quelques secondes, parfois plus, sans aucune garantie. En conséquence, par exemple, si une action utilise « champ 1 » mis à jour par une action Mettre à jour le profil positionnée juste avant, vous ne devriez pas vous attendre à une mise à jour de « champ 1 » dans l’action.
* Les sources de données ont une notion de la durée de mise en cache au niveau du groupe de champs. Si vous prévoyez d’utiliser un champ de profil récemment mis à jour dans un parcours, veillez à définir une durée de mise en cache très courte.
* En mode test, la mise à jour du profil ne sera pas simulée. La mise à jour sera effectuée sur le profil de test.

## Utilisation de la mise à jour du profil

1. Concevez votre parcours en commençant par un événement. Consultez cette [section](../building-journeys/journey.md).

1. Dans la section **Action** de la palette, déposez l’activité **Mettre à jour le profil** sur la zone de travail.

   ![](../assets/profileupdate0.png)

1. Sélectionnez un schéma dans la liste.

1. Cliquez sur **Champs** pour sélectionner le champ à mettre à jour. Vous ne pouvez sélectionner qu’un seul champ.

   ![](../assets/profileupdate2.png)

1. Sélectionnez un jeu de données dans la liste.

   >[!NOTE]
   >
   >L’action **Mettre à jour le profil** met à jour les données de profil en temps réel, mais elle ne met pas à jour les jeux de données. La sélection du jeu de données est nécessaire, car le profil est un enregistrement associé à un jeu de données.

1. Cliquez sur le champ **Valeur** pour définir la valeur à utiliser :

   * L’éditeur d’expression simple vous permet de sélectionner un champ à partir d’une source de données ou de l’événement entrant.

      ![](../assets/profileupdate4.png)

   * Si vous souhaitez définir une valeur spécifique ou utiliser des fonctions avancées, cliquez sur **Mode avancé**.

      ![](../assets/profileupdate3.png)

L’action **Mettre à jour le profil** est désormais configurée.

![](../assets/profileupdate1.png)
