---
product: adobe campaign
solution: Journey Orchestration
title: Cycle de données événement
description: En savoir plus sur le cycle de données de événement
translation-type: tm+mt
source-git-commit: b3ed5d305ddd1c86814373fc923390dc50a80c7e
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 78%

---


# Cycle de données {#section_r1f_xqt_pgb}

Les événements sont des appels d’API POST. Ils sont envoyés à Adobe Experience Platform par le biais des API d’ingestion en flux continu. L’URL de destination des événements envoyés via les API de messagerie transactionnelle est appelée « inlet ». La payload des événements respecte la mise en forme XDM.

La payload contient les informations nécessaires au fonctionnement des API d’ingestion en flux continu (dans l’en-tête) et de [!DNL Journey Orchestration] (l’identifiant d’événement, un élément du corps de la payload), ainsi que des informations à utiliser dans les parcours (dans le corps, par exemple, le montant d’un panier abandonné). Il existe deux modes d’ingestion en flux continu : authentifié et non authentifié. Pour plus d’informations sur les API d’ingestion en flux continu, cliquez sur [ce lien](https://docs.adobe.com/content/help/fr-FR/experience-platform/xdm/api/getting-started.html).

Après avoir transité par les API d’ingestion en flux continu, les événements se propagent dans un service interne appelé Pipeline, puis dans Adobe Experience Platform. Si l’indicateur du service de profil client en temps réel est activé pour le schéma d’événement et que ce dernier comprend également un identifiant de jeu de données avec l’indicateur de profil client en temps réel, le schéma est propagé dans ce service.

For system-generated events, the Pipeline filters events which have a payload containing [!DNL Journey Orchestration] eventIDs (see the event creation process below) provided by [!DNL Journey Orchestration] and contained in event payload. Pour les événements basés sur des règles, le système identifie le événement à l’aide de la condition eventID. Ces événements sont écoutés par [!DNL Journey Orchestration] et le parcours correspondant est déclenché.
