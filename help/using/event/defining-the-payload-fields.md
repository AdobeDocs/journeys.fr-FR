---
product: adobe campaign
title: Définition des champs de payload
description: Découvrez comment définir les champs de payload
feature: Journeys
role: User
level: Intermediate
exl-id: 9d385b64-46cd-489b-9c18-352fa2a2dbba
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: ht
source-wordcount: '300'
ht-degree: 100%

---

# Définition des champs de payload {#concept_yrw_3qt_52b}

La définition de la payload vous permet de choisir les informations que le système s&#39;attend à recevoir de l&#39;événement dans votre parcours, ainsi que la clé permettant d&#39;identifier la personne associée à l&#39;événement. La payload est basée sur la définition de champ XDM d&#39;Experience Cloud. Pour plus d&#39;informations sur XDM, consultez [cette page](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr).

1. Sélectionnez un schéma XDM dans la liste et cliquez ensuite sur le champ **[!UICONTROL Payload]** ou sur l&#39;icône **[!UICONTROL Modifier]**.

   ![](../assets/journey8.png)

   Tous les champs définis dans le schéma sont affichés. La liste des champs varie d&#39;un schéma à l&#39;autre. Vous pouvez rechercher un champ spécifique, ou utiliser les filtres pour afficher l&#39;ensemble des nœuds et des champs ou uniquement les champs sélectionnés. En fonction de la définition du schéma, certains champs peuvent être obligatoires et présélectionnés. Vous ne pouvez pas les désélectionner. Tous les champs obligatoires pour que Journey Orchestration reçoive correctement l’événement sont sélectionnés par défaut.

   >[!NOTE]
   >
   >Vérifiez que vous avez bien ajouté le mixin « orchestration » au schéma XDM. Vous aurez ainsi la garantie que votre schéma contient toutes les informations requises pour fonctionner avec [!DNL Journey Orchestration].

   ![](../assets/journey9.png)

1. Sélectionnez les champs que vous prévoyez de recevoir de l&#39;événement. Il s&#39;agit des champs que l&#39;utilisateur chargé de la conception de parcours exploitera dans le parcours. Ils doivent également inclure la clé qui sera utilisée pour identifier la personne associée à l’événement (voir [cette page](../event/defining-the-event-key.md)).

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >Pour les événements générés par le système, le champ **[!UICONTROL eventID]** est automatiquement ajouté à la liste des champs sélectionnés afin que [!DNL Journey Orchestration] puisse identifier l&#39;événement. Le système à l&#39;origine de l&#39;envoi de l&#39;événement ne doit pas générer d&#39;identifiant, mais plutôt utiliser celui indiqué dans l&#39;aperçu de la payload. Voir [cette page](../event/previewing-the-payload.md).

1. Une fois la sélection des champs nécessaires terminée, cliquez sur **[!UICONTROL Enregistrer]** ou appuyez sur la touche **[!UICONTROL Entrée]**.

   ![](../assets/journey11.png)

   Le nombre de champs sélectionnés s&#39;affiche dans le champ **[!UICONTROL Payload]**.

   ![](../assets/journey12.png)
