---
title: Événements de qualification de segment
description: En savoir plus sur les événements de qualification des segments
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
source-git-commit: 78c486c3e43b0bbda666afba9cf36ba34b362a03
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 32%

---


# Événements de qualification de segment {#segment-qualification}

## About segment qualification events{#about-segment-qualification}

Cette activité permet à votre voyage d&#39;écouter les entrées et les sorties des profils dans les segments Adobe Experience Platform afin de faire entrer ou avancer les personnes dans un voyage. Pour plus d’informations sur la création de segments, consultez cette [section](../segment/about-segments.md).

Supposons que vous ayez un segment « client Silver ». Avec cette activité, vous pouvez faire entrer tous les nouveaux clients Silver dans un parcours et leur envoyer une série de messages personnalisés.

Il est possible de positionner ce type d’événement dès la première étape, ou plus tard dans le parcours.

Si le segment est diffusé en continu avec l’option Audiences haute fréquence de Adobe Experience Platform, l’entrée et les sorties sont écoutées en temps réel. Si le segment n’est pas en flux continu, les entrées et les sorties sont prises en compte au moment du calcul du segment.

1. Développez la catégorie **[!UICONTROL Événements]** et déposez une activité de **[!UICONTROL qualification de segment]** dans la zone de travail.

   ![](../assets/segment5.png)

1. Ajoutez un **[!UICONTROL libellé]** à l’activité. Cette étape est facultative.

1. Cliquez dans le champ **[!UICONTROL Segment]** et sélectionnez les segments à exploiter.

   ![](../assets/segment6.png)

1. Dans le champ **[!UICONTROL Comportement]**, choisissez d’écouter les entrées de segments, les sorties ou les deux.

1. Sélectionnez un espace de noms. Cela n’est nécessaire que si l’événement est considéré comme la première étape du parcours.

   ![](../assets/segment7.png)

La payload contient les informations contextuelles suivantes, utilisables dans des conditions et des actions :

* le comportement (entrée, sortie)
* l’horodatage de la qualification
* l’identifiant de segment

Lorsque vous utilisez l’éditeur d’expression dans une condition ou une action qui suit une activité de **[!UICONTROL qualification du segment]**, vous avez accès au nœud **[!UICONTROL Qualification de segment]**. Vous pouvez choisir entre **[!UICONTROL l’heure de la dernière qualification]** et le **[!UICONTROL statut]** (entrée ou sortie).

Voir [Activité de condition](../building-journeys/condition-activity.md#about_condition).

![](../assets/segment8.png)

## Recommandations relatives aux segments {#best-practices-segments}

L&#39;activité **[!UICONTROL de qualification]** de segment permet l&#39;entrée immédiate dans les voyages des personnes qualifiées ou disqualifiées d&#39;un segment Adobe Experience Platform.

La vitesse de réception de ces informations est élevée. Les mesures effectuées montrent une vitesse de 10 000 événements reçues par seconde. Par conséquent, vous devez vous assurer de comprendre comment les pics d&#39;entrée peuvent se produire, comment les éviter et comment préparer votre voyage pour eux.

### Segments par lots{#batch-speed-segment-qualification}

Lorsque vous utilisez la qualification de segment pour un segment par lot, notez qu’un pic d’entrée survient au moment du calcul quotidien. La taille du pic dépend du nombre de personnes qui entrent (ou sortent) dans le segment quotidiennement.

De plus, si le segment de lot est créé et immédiatement utilisé dans un voyage, le premier lot de calculs peut faire qu&#39;un très grand nombre de personnes entrent dans le voyage.

### Segments en continu{#streamed-speed-segment-qualification}

Lors de l’utilisation de la qualification de segment pour les segments en flux continu, il y a moins de risque d’obtenir de grands pics d’entrées/sorties en raison de l’évaluation continue du segment. Néanmoins, si la définition de segment conduit à rendre un grand volume de clients admissibles en même temps, il peut y avoir un pic également.

### Comment éviter les surchargements{#overloads-speed-segment-qualification}

Voici quelques bonnes pratiques qui aideront à éviter la surcharge des systèmes utilisés dans les voyages (sources de données, actions personnalisées, actions Adobe Campaign Standard).

N’utilisez pas, dans une activité de qualification **[!UICONTROL de]** segment, un segment de lot immédiatement après sa création. Il évitera le premier pic de calcul. Notez qu’il y aura un avertissement jaune dans la trame de parcours si vous êtes sur le point d’utiliser un segment qui n’a jamais été calculé.

![](../assets/segment-error.png)

Mettez en place une règle de plafonnement pour les sources de données et les actions utilisées dans les voyages pour éviter de les surcharger (reportez-vous à cette [section](../api/capping.md)). Notez que la règle de plafonnement n’a pas de nouvelle tentative. Si vous devez réessayer, vous devez utiliser un autre chemin dans le parcours en cochant la case **[!UICONTROL Ajouter un autre chemin en cas de dépassement de délai ou d&#39;erreur]** dans les conditions ou les actions.

Avant d’utiliser le segment dans un parcours de production, évaluez toujours d’abord le volume de personnes admissibles à ce segment tous les jours. Pour ce faire, vous pouvez vérifier la section **[!UICONTROL Segments]** dans le Adobe Experience Platform et regarder le graphique sur le côté droit.

![](../assets/segment-overload.png)
