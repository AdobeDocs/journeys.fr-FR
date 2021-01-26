---
product: adobe campaign
solution: Journey Orchestration
title: Définition des champs de payload
description: Découvrez comment définir les champs de payload
translation-type: tm+mt
source-git-commit: a515e052a5bc1359632a1829df70a206614a5bb2
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 93%

---


# Définition des champs de payload {#concept_yrw_3qt_52b}

La définition de la payload vous permet de choisir les informations que le système s’attend à recevoir de l’événement dans votre parcours, ainsi que la clé permettant d’identifier la personne associée à l’événement. La payload est basée sur la définition de champ XDM d’Experience Cloud. Pour plus d’informations sur XDM, consultez [cette page](https://docs.adobe.com/content/help/fr-FR/experience-platform/xdm/home.html).

1. Sélectionnez un schéma XDM dans la liste et cliquez ensuite sur le champ **[!UICONTROL Payload]** ou sur l’icône **[!UICONTROL Modifier]**.

   ![](../assets/journey8.png)

   Tous les champs définis dans le schéma sont affichés. La liste des champs varie d’un schéma à l’autre. Vous pouvez rechercher un champ spécifique, ou utiliser les filtres pour afficher l’ensemble des nœuds et des champs ou uniquement les champs sélectionnés. En fonction de la définition du schéma, certains champs peuvent être obligatoires et présélectionnés. Vous ne pouvez pas les désélectionner. Tous les champs obligatoires pour que le Journey Orchestration reçoive correctement le événement sont sélectionnés par défaut.

   >[!NOTE]
   >
   >Vérifiez que vous avez bien ajouté le mixin « orchestration » au schéma XDM. Vous aurez ainsi la garantie que votre schéma contient toutes les informations requises pour fonctionner avec [!DNL Journey Orchestration].

   ![](../assets/journey9.png)

1. Sélectionnez les champs que vous prévoyez de recevoir de l’événement. Il s’agit des champs que l’utilisateur chargé de la conception de parcours exploitera dans le parcours. Ils doivent également inclure la clé qui sera utilisée pour identifier la personne associée à l’événement (voir [cette page](../event/defining-the-event-key.md)).

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >Pour les événements générés par le système, le champ **[!UICONTROL eventID]** est automatiquement ajouté à la liste des champs sélectionnés afin que [!DNL Journey Orchestration] puisse identifier l’événement. Le système à l’origine de l’envoi de l’événement ne doit pas générer d’identifiant, mais plutôt utiliser celui indiqué dans l’aperçu de la payload. Voir [cette page](../event/previewing-the-payload.md).

1. Une fois la sélection des champs nécessaires terminée, cliquez sur **[!UICONTROL Enregistrer]** ou appuyez sur la touche **[!UICONTROL Entrée]**.

   ![](../assets/journey11.png)

   Le nombre de champs sélectionnés s’affiche dans le champ **[!UICONTROL Payload]**.

   ![](../assets/journey12.png)
