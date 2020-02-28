---
title: Groupes de champs
description: En savoir plus sur les groupes de champs
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
source-git-commit: 690f8c1732c7d54c234e9ba633a2cf014492f423

---



# Groupes de champs {#concept_ntl_ypt_52b}

Les groupes de champs sont des ensembles de champs que vous pouvez récupérer d’une source de données et utiliser dans un voyage.

## Définition de groupes de champs {#section_dsz_kjd_fjb}

Pour chaque source de données, vous pouvez définir plusieurs groupes de champs ayant chacun une durée de mise en cache spécifique.

Vous pouvez, par exemple, créer un groupe de champs avec le numéro de téléphone, l’adresse email, le prénom et l’adresse du profil. Vous pourrez alors utiliser ces données dans votre parcours afin de créer des conditions. Par exemple, vous pouvez choisir de n’envoyer un SMS que si le numéro de téléphone du profil est renseigné. Si le champ est vide, vous pouvez envoyer un email.

Bien qu’un nom par défaut soit automatiquement ajouté à votre groupe de champs, nous vous recommandons d’attribuer un nom personnalisé. En effet, ce nom sera visible par d’autres utilisateurs de Journey Orchestration. Il est conseillé d’attribuer au groupe un nom pertinent.

Lorsqu’un champ de source de données est utilisé dans un parcours, le système récupère tous ceux qui sont définis pour ce groupe. Par conséquent, il est recommandé de ne sélectionner que les champs dont vous avez besoin pour vos parcours. Cela permettra de réduire la latence des requêtes dans vos parcours et d’améliorer les performances. Notez que vous pourrez facilement ajouter d’autres champs dans les groupes ultérieurement.

**[!UICONTROL Cache duration]** est également important car il vous aidera à optimiser les performances. Concrètement, cela signifie que dans le cadre d’un parcours, si des données d’un groupe de champs sont récupérées une fois, le système les met temporairement en cache. Si les mêmes données sont requises plus tard dans le même parcours, le système n’effectue aucune autre requête vers la source de données. La configuration de la durée de mise en cache doit être adaptée à chaque cas d’utilisation. Si vous devez récupérer des données en temps réel, telles que le statut d’une réservation d’hôtel, des informations météorologiques ou le nombre de points de fidélité, vous associerez le groupe contenant ces champs à une durée de mise en cache brève (1 seconde, par exemple). Pour les champs mis à jour moins souvent (nom, genre, etc.), vous créerez un deuxième groupe de champs avec une durée de mise en cache plus longue (5 jours, par exemple).

The number of journeys that use a field group is displayed in the **[!UICONTROL Used in]** field. You can click the **[!UICONTROL View journeys]** button to display the list of journeys using this field group.

>[!NOTE]
>
>Notez que si un groupe ne contient aucun champ, il ne s’affiche pas dans l’éditeur d’expression.

![](../assets/journey3bis.png)

## Cycle de vie du groupe de champs {#section_abk_njd_fjb}

Vous pouvez ajouter des champs à un groupe qui n’est utilisé dans aucun parcours actif ou dans un état de brouillon, ou en supprimer.

Vous pouvez ajouter un champ à un groupe utilisé dans un ou plusieurs parcours actifs ou dans un état de brouillon, mais pas en supprimer. Cela permet d’éviter l’interruption des parcours.

Pour supprimer un champ d’un groupe utilisé dans un ou plusieurs parcours, procédez comme suit. Prenons l’exemple d’un groupe de champs appelé « Groupe de champs A ».

1. In the list of field groups, place the cursor on “Field Group A” and click on the **[!UICONTROL Duplicate]** icon located on the right. Appelez le groupe de champs dupliqué « Groupe de champs B », par exemple.
1. Dans « Groupe de champs B », supprimez les champs dont vous n’avez plus besoin.
1. Dans « Groupe de champs A », vérifiez à quel emplacement ce groupe de champs est utilisé. This information is displayed in the **[!UICONTROL Used in]** field.
1. Ouvrez tous les parcours qui utilisent « Groupe de champs A ».
1. Créez de nouvelles versions de chacun de ces parcours. Modifiez toutes les activités qui utilisent « Groupe de champs A » et sélectionnez « Groupe de champs B ».
1. Arrêtez les anciennes versions des parcours qui utilisent « Groupe de champs A ». Normalement, il ne devrait plus y avoir de parcours qui utilisent « Groupe de champs A ».
1. Supprimez « Groupe de champs A », car il n’est plus utilisé.
