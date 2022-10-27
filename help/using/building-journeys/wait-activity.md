---
product: adobe campaign
title: Activité d'attente
description: En savoir plus sur l'activité d'attente
feature: Journeys
role: User
level: Intermediate
exl-id: 819ff3c3-0e3e-4d86-b5d2-10c5b10d19e6
source-git-commit: 77fcc4ba02a855d4d584627625a08abb4af0da2f
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---

# Activité d&#39;attente{#section_rlm_nft_dgb}

Si vous souhaitez observer un temps d&#39;attente avant d&#39;exécuter l&#39;activité suivante dans le chemin, vous pouvez utiliser une activité **[!UICONTROL Attente]**. Cela vous permet de définir le moment d&#39;exécution de l&#39;activité suivante. Trois options sont disponibles :

* [Durée](#duration)
* [Valeur](#custom) personnalisée
<!--* [Email send time optimization](#email_send_time_optimization)-->

## À propos de l&#39;activité d&#39;attente{#about_wait}

Voici comment les attentes sont classées par priorité lorsque vous en utilisez plusieurs en parallèle. Si les attentes présentent la même configuration temporelle et une condition différente, mais superposée, celle qui est placée au-dessus est prioritaire. Supposons, par exemple, que la condition de la première attente soit « être une femme » et que la condition de la deuxième attente en parallèle est « être une VIP ». La première activité d&#39;attente sera donc prioritaire..

Notez également que si deux attentes différentes s&#39;exécutent en parallèle, celle qui se produit en premier est prioritaire, quelle que soit sa position verticale. Par exemple, si une attente d&#39;une heure est placée au-dessus et une attente de 30 minutes en dessous, cette dernière est traitée après 30 minutes.

>[!NOTE]
>
>La durée d&#39;attente maximale est de 30 jours.
>
>En mode test, le paramètre **[!UICONTROL Temps d&#39;attente en test]** vous permet de définir la durée de chaque activité d&#39;attente. La valeur par défaut est de 10 secondes. Vous obtiendrez ainsi rapidement les résultats du test. Voir [cette page](../building-journeys/testing-the-journey.md)

## Durée de l&#39;attente{#duration}

Sélectionnez la durée d&#39;attente avant l&#39;exécution de l&#39;activité suivante.

![](../assets/journey55.png)

## Attente personnalisée{#custom}

Cette option vous permet de définir une date personnalisée (le 12 juillet 2020 à 17 heures, par exemple) à l&#39;aide d&#39;une expression avancée basée sur un champ provenant d&#39;un événement ou d&#39;une source de données. Elle ne vous permet pas de définir une durée personnalisée ; 7 jours, par exemple. L&#39;expression figurant dans l&#39;éditeur d&#39;expression doit fournir un format dateTimeOnly. Voir [cette page](../expression/expressionadvanced.md). Pour plus d&#39;informations sur le format dateTimeOnly, voir [cette page](../expression/data-types.md).

>[!NOTE]
>
>Vous pouvez tirer parti d&#39;une expression dateTimeOnly ou utiliser une fonction pour effectuer une conversion dans ce format. Par exemple : toDateTimeOnly(@{Event.offerOpened.activity.endTime}), le champ de l&#39;événement se présentant sous la forme 2016-08-12T09:46:06Z.
>
>La définition du **fuseau horaire** est attendue dans les propriétés de votre parcours. Par conséquent, il n&#39;est pas possible actuellement de pointer directement, à partir de l&#39;interface, vers un horodatage ISO-8601 complet associant l&#39;heure et le décalage dû au fuseau horaire, tel que 2016-08-12T09:46:06.982-05. Voir [cette page](../building-journeys/timezone-management.md).

![](../assets/journey57.png)

<!--## Email send time optimization{#email_send_time_optimization}

>[!CAUTION]
>
>The email send time optimization capability is only available to customers who use the [Adobe Experience Platform Data Connector](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html).

This type of wait uses a score calculated in the Adobe Experience Platform. The score calculates the propensity to click or open an email in the future based on past behavior. Note that the algorithm calculating the score needs a certain amount of data to work. As a result, when it does not have enough data, the default wait time will apply. At publication time, you’ll be notified that the default time applies.

>[!NOTE]
>
>The first event of your journey must have a namespace.
>
>This capability is only available after an **[!UICONTROL Email]** activity. You need to have Adobe Campaign Standard.

1. In the **[!UICONTROL Amount of time]** field, define the number of hours to consider to optimize email sending.
1. In the **[!UICONTROL Optimization type]** field, choose if the optimization should increase clicks or opens.
1. In the **[!UICONTROL Default time]** field, define the default time to wait if the predictive send time score is not available.

    >[!NOTE]
    >
    >Note that the send time score can be unavailable because there is not enough data to perform the calculation. In this case, you will be informed, at publication time, that the default time applies.

![](../assets/journey57bis.png)-->
