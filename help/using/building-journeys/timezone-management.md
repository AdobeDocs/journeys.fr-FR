---
title: Gestion des fuseaux horaires
description: En savoir plus sur la gestion des fuseaux horaires
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
source-git-commit: f4f41428b19f611da15b20a1788b240fadfd49fa

---



# Gestion des fuseaux horaires {#timezone_management}

Vous pouvez définir un fuseau horaire dans les [propriétés](../building-journeys/changing-properties.md) de votre voyage.

Pour accéder à Propriétés, cliquez sur l&#39;icône en forme de crayon dans le coin supérieur droit de l&#39;écran.

Ce fuseau horaire sera utilisé pour chaque activité du voyage contenant un élément temporel tel que :

* [](../building-journeys/condition-activity.md#time_condition)
* [](../building-journeys/condition-activity.md#date_condition)
* [](../building-journeys/wait-activity.md#custom)
* [](../building-journeys/wait-activity.md#fixed_date)

Vous pouvez sélectionner un fuseau horaire ou choisir d’utiliser le fuseau horaire défini dans le profil utilisateur.

## Définition d’un fuseau horaire fixe {#fixed-timezone}

Le fuseau horaire peut également être fixe. Effacez le fuseau horaire prédéfini et sélectionnez-en un dans la liste déroulante. Si vous utilisez un fuseau horaire fixe, il sera identique pour toutes les personnes qui participent au parcours.

Pour ce faire, sélectionnez **[!UICONTROL Properties]** un fuseau horaire.

![](../assets/journey73.png)

## Utilisation de profils pour définir le fuseau horaire du voyage {#timezone-from-profiles}

Si un namespace est associé à l’événement d’entrée du parcours, ce qui signifie que ce dernier peut accéder au service de profil client en temps réel de Data Platform, le fuseau horaire est prédéfini avec celui spécifié dans le profil de la personne qui participe au parcours.

Si un fuseau horaire est défini dans le profil de la plateforme d’expérience, il peut être récupéré dans le voyage.

Si le profil de la personne ne contient pas de fuseau horaire, celui récupéré sera celui défini dans le champ de fuseau horaire.

Pour ce faire, vérifiez **[!UICONTROL Properties]****[!UICONTROL Use Profile timezone in timers and conditions]**.

![](../assets/journey72.png)

## Utilisation des fuseaux horaires dans les expressions {#timezone-in-expressions}

Les fuseaux horaires sont utilisés pour créer une expression avec l’éditeur d’expression avancé. Dans ce cas, vous utiliserez l’éditeur d’expression pour sélectionner l’emplacement où vous souhaitez que le système obtienne ces informations. Voir [](../expression/expressionadvanced.md).

Les dates de début et de fin d’un parcours ne peuvent pas être liées à un fuseau horaire spécifique. Elles sont automatiquement associées à celui de l’instance.
