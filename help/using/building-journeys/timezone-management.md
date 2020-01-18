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
source-git-commit: f57cc43d8f2a223c04cc4ccccb3b3c3e0bcadfc1

---



# Gestion des fuseaux horaires {#timezone_management}

La définition de fuseau horaire est disponible dans les activités suivantes :

* [](../building-journeys/condition-activity.md#time_condition)
* [](../building-journeys/condition-activity.md#date_condition)
* [](../building-journeys/wait-activity.md#custom)
* [](../building-journeys/wait-activity.md#fixed_date)

Si l’événement d’entrée du voyage comporte un espace de noms, ce qui signifie que le voyage peut atteindre le service Profil du client en temps réel de la plateforme de données, le fuseau horaire est prédéfini avec celui spécifié dans le profil de l’individu qui effectue le voyage. Si le profil de la personne ne contient pas de fuseau horaire, celui de l’instance est utilisé. Vous pouvez contacter votre administrateur pour connaître le fuseau horaire de l’instance.

![](../assets/journey73.png)

Le fuseau horaire peut également être corrigé. Effacez le fuseau horaire prédéfini et sélectionnez-en un dans la liste déroulante. Si vous utilisez un fuseau horaire fixe, il sera le même pour toutes les personnes qui entrent dans le voyage.

![](../assets/journey72.png)

Enfin, le fuseau horaire peut être dynamique pour chaque personne qui entre dans l’étape. Dans ce cas, vous allez utiliser l’éditeur d’expression pour sélectionner l’emplacement où vous souhaitez que le système obtienne ces informations (elles peuvent provenir d’un événement ou d’une source de données). Voir la section [](../expression/expressionadvanced.md).


Les dates de début et de fin d&#39;un voyage ne peuvent pas être liées à un fuseau horaire spécifique. Ils sont automatiquement associés au fuseau horaire de l’instance.
