---
product: adobe campaign
solution: Journey Orchestration
title: Passage d’un parcours à un autre
description: Passage d’un parcours à un autre
feature: Parcours
role: Professionnel
level: Intermédiaire
translation-type: tm+mt
source-git-commit: 8685dfdcbfb414af89b304a6a9a0f9418959909b
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 100%

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

## Utilisation du mode test {#using-the-test-mode}

En mode test, la mise à jour du profil ne sera pas simulée. La mise à jour sera effectuée sur le profil de test.

Seuls les profils de test peuvent rejoindre un parcours en mode test. Vous pouvez soit créer un profil de test, soit transformer un profil existant en profil de test. Dans Adobe Experience Platorm, vous pouvez mettre à jour les attributs des profils par le biais d’appels d’API, mais il n’est pas possible de le faire par le biais de l’interface. Pour ce faire, la méthode la plus simple consiste à utiliser une activité d’action **Mettre à jour le profil** et à modifier le champ booléen du profil de test en le passant de false à true.

Pour plus d’informations sur le mode test, consultez cette [section](../building-journeys/testing-the-journey.md).

## Utilisation de la mise à jour du profil

1. Concevez votre parcours en commençant par un événement. Consultez cette [section](../building-journeys/journey.md).

1. Dans la section **Action** de la palette, déposez l’activité **Mettre à jour le profil** sur la zone de travail.

   ![](../assets/profileupdate0.png)

1. Sélectionnez un schéma dans la liste.

1. Cliquez sur **Champs** pour sélectionner le champ à mettre à jour. Vous ne pouvez sélectionner qu’un seul champ.

   ![](../assets/profileupdate2.png)

1. Sélectionnez un jeu de données dans la liste. La sélection du jeu de données détermine l’endroit où sera stockée la nouvelle valeur du champ de profil.

1. Cliquez sur le champ **Valeur** pour définir la valeur à utiliser :

   * L’éditeur d’expression simple vous permet de sélectionner un champ à partir d’une source de données ou de l’événement entrant.

      ![](../assets/profileupdate4.png)

   * Si vous souhaitez définir une valeur spécifique ou utiliser des fonctions avancées, cliquez sur **Mode avancé**.

      ![](../assets/profileupdate3.png)

L’action **Mettre à jour le profil** est désormais configurée.

![](../assets/profileupdate1.png)
