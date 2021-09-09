---
product: adobe campaign
title: À propos des segments Adobe Experience Platform
description: Découvrez comment configurer un segment Adobe Experience Platform
feature: Journeys
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
source-git-commit: e5c0db2e1f85ea72fd54f91e4a26cc287377fb0e
workflow-type: ht
source-wordcount: '366'
ht-degree: 100%

---

# À propos des segments Adobe Experience Platform {#about-segments}

Si vous utilisez le [service de segmentation Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=fr) pour créer vos segments, vous pouvez les exploiter dans [!DNL Journey Orchestration]. Grâce à une activité d’événement dédiée, vous pouvez faire entrer des individus ou leur permettre de progresser dans un parcours en fonction des entrées et des sorties de segments Adobe Experience Platform. Vous pouvez également créer des conditions complexes dans vos parcours grâce à l’éditeur d’expression simple ou avancé.

Supposons que vous ayez un segment « client Silver ». Avec cette activité, vous pouvez faire entrer tous les nouveaux clients Silver dans un parcours et leur envoyer une série de messages personnalisés. Vous pouvez aussi créer facilement des conditions basées sur ce segment.

Les possibilités que vous apporte [!DNL Journey Orchestration] concernant les segments sont présentées ci-dessous :

* Accéder à la liste des segments Adobe Experience Platform. Pour plus d&#39;informations, consultez la section [Création d’un segment](../segment/creating-a-segment.md).
* Créer des segments directement dans [!DNL Journey Orchestration] comme vous le faites avec le service de segmentation. Pour plus d&#39;informations, consultez la section [Création d’un segment](../segment/creating-a-segment.md).
* Tirer parti des segments dans les conditions de votre parcours à l’aide de l’éditeur d’expression simple ou avancé. Pour plus d&#39;informations, consultez la section [Utilisation de segments dans des conditions](../segment/using-a-segment.md).
* Ajouter un événement de **[!UICONTROL qualification de segment]** à votre parcours pour écouter les entrées et les sorties des profils dans les segments Adobe Experience Platform. Pour plus d&#39;informations, consultez la section [Activités d’événement](../building-journeys/segment-qualification-events.md).

## Méthode d’évaluation dans Journey Orchestration {#evaluation-method-in-journey-orchestration}

Dans Journey Orchestration, les audiences sont générées à partir des définitions de segment à l’aide de l’une des méthodes d’évaluation suivantes :

* Segmentation par flux : la liste des audiences du segment est actualisée en temps réel pendant que de nouvelles données affluent dans le système.
* Segmentation par lots : la liste des audiences du segment est mise à jour toutes les heures, en fonction des données arrivées au cours de la dernière heure.

Le système détermine la segmentation par lots et la segmentation par flux pour chaque définition de segment, en fonction de la complexité et du coût de l’évaluation de la règle de segment.

Vous pouvez afficher la méthode d’évaluation pour chaque segment dans la colonne **[!UICONTROL Méthode d’évaluation]** de la liste des segments.

Une fois que vous avez défini un segment pour la première fois, les profils sont ajoutés à l’audience lorsqu’ils remplissent les critères.

Le renvoi de l’audience à partir de données antérieures peut prendre jusqu’à 24 heures. Une fois l’audience renvoyée, elle est constamment tenue à jour et toujours prête pour le ciblage.