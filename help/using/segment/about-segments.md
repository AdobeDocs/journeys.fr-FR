---
product: adobe campaign
title: À propos des segments Adobe Experience Platform
description: Découvrez comment configurer un segment Adobe Experience Platform
feature: Journeys
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
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
source-wordcount: '425'
ht-degree: 100%
---
# À propos des segments Adobe Experience Platform {#about-segments}


>[!CAUTION]
>
>**Vous recherchez Adobe Journey Optimizer** ? Cliquez [ici](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/ajo-home){target="_blank"} pour consulter la documentation de Journey Optimizer.
>
>
>_Cette documentation se rapporte aux anciens contenus de Journey Orchestration qui ont été remplacés par Journey Optimizer. Pour toute question concernant votre accès à Journey Orchestration ou Journey Optimizer, contactez votre équipe en charge des comptes._


Si vous utilisez le [service de segmentation Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=fr) pour créer vos segments, vous pouvez les exploiter dans [!DNL Journey Orchestration]. Grâce à une activité d’événement dédiée, vous pouvez faire entrer des individus ou leur permettre de progresser dans un parcours en fonction des entrées et des sorties de segments Adobe Experience Platform. Vous pouvez également créer des conditions complexes dans vos parcours grâce à l’éditeur d’expression simple ou avancé.

Supposons que vous ayez un segment « client Silver ». Avec cette activité, vous pouvez faire entrer tous les nouveaux clients Silver dans un parcours et leur envoyer une série de messages personnalisés. Vous pouvez aussi créer facilement des conditions basées sur ce segment.

Les possibilités que vous apporte [!DNL Journey Orchestration] concernant les segments sont présentées ci-dessous :

* Accéder à la liste des segments Adobe Experience Platform. Pour plus d&#39;informations, consultez la section [Création d’un segment](../segment/creating-a-segment.md).
* Créer des segments directement dans [!DNL Journey Orchestration] comme vous le faites avec le service de segmentation. Pour plus d&#39;informations, consultez la section [Création d’un segment](../segment/creating-a-segment.md).
* Tirer parti des segments dans les conditions de votre parcours à l’aide de l’éditeur d’expression simple ou avancé. Pour plus d&#39;informations, consultez la section [Utilisation de segments dans des conditions](../segment/using-a-segment.md).
* Ajouter un événement de **[!UICONTROL qualification de segment]** à votre parcours pour écouter les entrées et les sorties des profils dans les segments Adobe Experience Platform. Pour plus d&#39;informations, consultez la section [Activités d’événement](../building-journeys/segment-qualification-events.md).

## Méthode d’évaluation dans Journey Orchestration {#evaluation-method-in-journey-orchestration}

Dans Journey Orchestration, les audiences sont générées à partir des définitions de segment à l’aide de l’une des méthodes d’évaluation suivantes :

* Segmentation par flux : la liste des audiences du segment est actualisée en temps réel pendant que de nouvelles données affluent dans le système.
* Segmentation par lots : la liste des audiences du segment est mise à jour toutes les heures, en fonction des données arrivées au cours de la dernière heure.

Le système détermine la segmentation par lots et la segmentation par flux pour chaque définition de segment, en fonction de la complexité et du coût de l’évaluation de la règle de segment.

Vous pouvez afficher la méthode d’évaluation pour chaque segment dans la colonne **[!UICONTROL Méthode d’évaluation]** de la liste des segments.

Une fois que vous avez défini un segment pour la première fois, les profils sont ajoutés à l’audience lorsqu’ils remplissent les critères.

Le renvoi de l’audience à partir de données antérieures peut prendre jusqu’à 24 heures. Une fois l’audience renvoyée, elle est constamment tenue à jour et toujours prête pour le ciblage.