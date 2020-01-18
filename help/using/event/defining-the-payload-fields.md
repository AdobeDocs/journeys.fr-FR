---
title: Définition des champs de charge utile
description: Découvrez comment définir les champs de charge utile
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


# Définition des champs de charge utile {#concept_yrw_3qt_52b}

La définition de charge utile vous permet de choisir les informations que le système attend de recevoir de l&#39;événement dans votre voyage et la clé pour identifier la personne associée à l&#39;événement. La charge est basée sur la définition du champ XDM d’Experience Cloud. For more information on XDM, refer to this [page](https://www.adobe.io/apis/cloudplatform/dataservices/xdm.html).

1. Sélectionnez un schéma XDM dans la liste et cliquez sur le champ **[!UICONTROL Charge]**utile ou sur l’icône**[!UICONTROL  Modifier]** .

   ![](../assets/journey8.png)

   Tous les champs définis dans le schéma sont affichés. La liste des champs varie d’un schéma à l’autre. Vous pouvez rechercher un champ spécifique ou utiliser les filtres pour afficher tous les noeuds et champs ou uniquement les champs sélectionnés. Selon la définition du schéma, certains champs peuvent être obligatoires et présélectionnés. Vous ne pouvez pas les désélectionner.

   >[!NOTE]
   >
   >Assurez-vous d’avoir ajouté le mixin &quot;orchestration&quot; au schéma XDM. Vous serez ainsi assuré que votre schéma contient toutes les informations requises pour travailler avec l’orchestration de Journey.

   ![](../assets/journey9.png)

1. Sélectionnez les champs que vous prévoyez de recevoir de l’événement. Ce sont les domaines que l&#39;utilisateur commercial exploitera dans le voyage. Ils doivent également inclure la clé qui sera utilisée pour identifier la personne associée à l&#39;événement (voir [](../event/defining-the-event-key.md)).

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >Le champ **[!UICONTROL eventID]**est automatiquement ajouté dans la liste des champs sélectionnés afin que l’orchestration du voyage puisse identifier l’événement. Le système poussant l’événement ne doit pas générer d’identifiant, il doit utiliser celui disponible dans l’aperçu de la charge utile. Voir la section[](../event/previewing-the-payload.md).

1. Lorsque vous avez terminé de sélectionner les champs nécessaires, cliquez sur **[!UICONTROL Enregistrer]**ou appuyez sur**[!UICONTROL  Entrée]**.

   ![](../assets/journey11.png)

   Le nombre de champs sélectionnés s’affiche dans le champ **[!UICONTROL Charge]**utile.

   ![](../assets/journey12.png)
