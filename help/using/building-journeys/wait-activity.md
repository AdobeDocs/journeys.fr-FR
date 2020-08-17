---
title: Activité d’attente
description: En savoir plus sur l’activité d’attente
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
source-git-commit: 92bd110c4c91c459c8074184bdb486733ab5f3d7
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 95%

---


# Activité d’attente{#section_rlm_nft_dgb}

Si vous souhaitez observer un temps d’attente avant d’exécuter l’activité suivante dans le chemin, vous pouvez utiliser une activité **[!UICONTROL Attente]**. Cela vous permet de définir le moment d’exécution de l’activité suivante. Quatre options sont disponibles :

* [Durée](#duration)
* [Date fixe](#fixed_date)
* [Personnalisé](#custom)
* [Optimisation de l’heure d’envoi des emails](#email_send_time_optimization)

## À propos de l’activité d’attente{#about_wait}

Voici comment les attentes sont classées par priorité lorsque vous en utilisez plusieurs en parallèle. Si les attentes présentent la même configuration temporelle et une condition différente, mais superposée, celle qui est placée au-dessus est prioritaire. Supposons, par exemple, que la condition de la première attente soit « être une femme » et que la condition de la deuxième attente en parallèle est « être une VIP ». La première activité d’attente sera donc prioritaire.

Notez également que si deux attentes différentes s’exécutent en parallèle, celle qui se produit en premier est prioritaire, quelle que soit sa position verticale. Par exemple, si une attente d’une heure est placée au-dessus et une attente de 30 minutes en dessous, cette dernière est traitée après 30 minutes.

Vous pouvez définir une condition afin de limiter l’attente à une certaine population.

>[!NOTE]
>
>La durée d’attente maximale est de 30 jours.
>
>En mode test, le paramètre **[!UICONTROL Temps d’attente en test]** vous permet de définir la durée de chaque activité d’attente. La durée par défaut est de 10 secondes. Vous obtiendrez ainsi rapidement les résultats du test. Voir la section [](../building-journeys/testing-the-journey.md)

## Durée de l’attente{#duration}

Sélectionnez la durée d’attente avant l’exécution de l’activité suivante.

![](../assets/journey55.png)

## Attente à date fixe{#fixed_date}

Sélectionnez la date d’exécution de l’activité suivante.

![](../assets/journey56.png)

## Attente personnalisée{#custom}

Cette option vous permet de définir une date personnalisée (le 12 juillet 2020 à 17 heures, par exemple) à l’aide d’une expression avancée basée sur un champ provenant d’un événement ou d’une source de données. Elle ne vous permet pas de définir une durée personnalisée ; 7 jours, par exemple. L’expression figurant dans l’éditeur d’expression doit fournir un format dateTimeOnly. Voir [](../expression/expressionadvanced.md). Pour plus d’informations sur le format dateTimeOnly, voir [](../expression/data-types.md).

>[!NOTE]
>
>Vous pouvez tirer parti d’une expression dateTimeOnly ou utiliser une fonction pour effectuer une conversion dans ce format. Par exemple : toDateTimeOnly(@{Event.offerOpened.activity.endTime}), le champ de l’événement se présentant sous la forme 2016-08-12T09:46:06.
>
>La définition du **fuseau horaire** est attendue dans les propriétés de votre parcours. Par conséquent, il n’est pas possible actuellement de pointer directement, à partir de l’interface, vers un horodatage ISO-8601 complet associant l’heure et le décalage dû au fuseau horaire, tel que 2016-08-12T09:46:06.982-05. Voir [](../building-journeys/timezone-management.md).

![](../assets/journey57.png)

## Optimisation de l’heure d’envoi des emails{#email_send_time_optimization}

>[!CAUTION]
>
>The email send time optimization capability is only available to customers who use the [Adobe Experience Platform Data Connector](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html).

Ce type d’attente utilise un score calculé dans Adobe Experience Platform. Le score calcule la propension d’un client à cliquer sur un email ou à l’ouvrir dans le futur en se basant sur son comportement passé. Notez qu’une certaine quantité de données est nécessaire pour que l’algorithme qui calcule le score puisse fonctionner. Par conséquent, lorsque les données sont insuffisantes, le temps d’attente par défaut est appliqué. Au moment de la publication, vous serez informé que le laps de temps par défaut s’applique.

>[!NOTE]
>
>Le premier événement de votre parcours doit avoir un espace de noms.
>
>Cette fonctionnalité n’est disponible qu’après une activité **[!UICONTROL Email]**. Vous devez disposer d’Adobe Campaign Standard.

1. Dans le champ **[!UICONTROL Laps de temps]**, définissez le nombre d’heures à prendre en compte pour optimiser l’envoi des emails.
1. Dans le champ **[!UICONTROL Type d’optimisation]**, indiquez si l’optimisation doit augmenter le nombre de clics ou d’ouvertures.
1. Dans le champ **[!UICONTROL Laps de temps par défaut]**, définissez le délai d’attente par défaut si le score de l’heure d’envoi prédictif n’est pas disponible.

   >[!NOTE]
   >
   >Notez que le score de l’heure d’envoi peut être indisponible en raison d’une quantité de données insuffisante pour effectuer le calcul. Dans ce cas, vous êtes informé, au moment de la publication, que le laps de temps par défaut est appliqué.

![](../assets/journey57bis.png)
