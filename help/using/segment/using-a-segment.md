---
product: adobe campaign
title: Utilisation de segments dans des conditions
description: Découvrez comment utiliser un segment
feature: Journeys
role: User
level: Intermediate
exl-id: 9a0490c8-c940-44d2-af1a-d1863c51465d
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
source-wordcount: '229'
ht-degree: 100%
---
# Utilisation de segments dans des conditions {#using-a-segment}


>[!CAUTION]
>
>**Vous recherchez Adobe Journey Optimizer** ? Cliquez [ici](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/ajo-home){target="_blank"} pour consulter la documentation de Journey Optimizer.
>
>
>_Cette documentation se rapporte aux anciens contenus de Journey Orchestration qui ont été remplacés par Journey Optimizer. Pour toute question concernant votre accès à Journey Orchestration ou Journey Optimizer, contactez votre équipe en charge des comptes._


Cette section explique comment utiliser un segment dans une condition de parcours. Pour savoir comment utiliser un événement de **[!UICONTROL qualification de segment]** dans votre parcours, reportez-vous à cette [section](../building-journeys/segment-qualification-events.md).

Pour utiliser un segment dans une condition de parcours, procédez comme suit :

1. Ouvrez un parcours, déposez une activité **[!UICONTROL Condition]** et choisissez la **condition de source de données**.
   ![](../assets/journey47.png)

1. Cliquez sur **[!UICONTROL Ajouter un chemin]** pour chaque chemin supplémentaire nécessaire. Pour chaque chemin, cliquez sur le champ **[!UICONTROL Expression]**.

   ![](../assets/segment3.png)

1. Sur le côté gauche, développez le nœud **[!UICONTROL Segments]**. Faites glisser et déposez le segment à utiliser pour votre condition. Par défaut, la condition sur le segment est &#39;true&#39;.

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >Seuls les individus présentant les statuts de participation **Réalisé** et **Existant** sont considérés comme membres du segment. Pour plus d&#39;informations sur l&#39;évaluation d&#39;un segment, consultez la [documentation du service de segmentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=fr#interpret-segment-results).

Pour plus d’informations sur les conditions de parcours et sur l’utilisation de l’éditeur d’expression simple, consultez la section [Activité de condition](../building-journeys/condition-activity.md#about_condition).
