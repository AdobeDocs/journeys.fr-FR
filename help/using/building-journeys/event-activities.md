---
title: À propos des activités d’événement
description: En savoir plus sur les activités d’événement
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 100%

---


# À propos des activités d’événement {#concept_rws_1rt_52b}

Les événements configurés par l’utilisateur technique (voir la section [](../event/about-events.md)) sont tous affichés dans la première catégorie de la palette, dans la partie gauche de l’écran.

![](../assets/journey43.png)

Commencez toujours votre parcours en faisant glisser une activité d’événement. Vous pouvez également double-cliquer sur celle-ci.

![](../assets/journey44.png)

Lorsque vous cliquez sur l’activité d’événement dans la zone de travail, le volet de configuration correspondant s’affiche. Par défaut, lorsque vous utilisez plusieurs fois un même événement, un nombre incrémenté est ajouté à son nom dans la zone de travail. Vous pouvez, en outre, utiliser le champ **[!UICONTROL Libellé]** pour ajouter au nom de l’événement un suffixe qui apparaîtra sous votre activité dans la zone de travail. Cela s’avère utile pour identifier vos événements dans la zone de travail, notamment si vous utilisez le même événement à plusieurs reprises. Cela facilite également le débogage lorsque des erreurs se produisent et permet une lecture plus facile des rapports.

![](../assets/journey33.png)

## Utilisation avancée : événements avec une activité d’attente en parallèle{#section_vxv_h25_pgb}

**Comment faire pour écouter un événement pendant une certaine période ?**

Une activité d’événement située dans le parcours « écoute » les événements pendant une durée indéterminée. Pour limiter la durée d’écoute à une période bien définie, vous devez ajouter une activité d’attente parallèlement au chemin de l’événement. Ce faisant, le parcours écoutera l’événement au cours de la période définie dans l’activité d’attente. Si un événement est reçu au cours de cette période, le client sera intégré dans le chemin de l’événement. Dans le cas contraire, il sera placé dans le chemin d’attente.

Supposons, par exemple, que vous ayez envoyé une première notification push de bienvenue à un client et que vous souhaitiez lui envoyer une notification push de remise sur un repas, uniquement s’il se rend dans le restaurant dans les 6 prochaines heures. Pour ce faire, vous allez créer un deuxième chemin (parallèlement à l’événement « restaurant » numéro 1) avec une activité d’attente de 6 heures. Si l’événement « restaurant » est reçu moins de 6 heures après la notification push de bienvenue, l’activité push de remise sur un repas est envoyée. Si aucun événement « restaurant » n’est reçu sous 6 heures, le client passe par le chemin d’attente.

![](../assets/journeyuc2_31.png)
