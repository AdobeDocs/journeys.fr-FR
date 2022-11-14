---
product: adobe campaign
title: Présentation du partage des étapes du parcours
description: Présentation du partage des étapes du parcours
feature: Journeys
role: User
level: Intermediate
exl-id: 95ca5fdb-38b7-47a0-b1a9-b1b26bf8e5f5
source-git-commit: bb07c0edaae469962ee3bf678664b4a0a83572fe
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 100%

---

# Présentation du partage des étapes du parcours{#sharing-overview}

[!DNL Journey Orchestration] envoie automatiquement les données de performances à Adobe Experience Platform pour les combiner avec d’autres données à des fins d’analyse.

>[!NOTE]
>
>Cette fonction est activée par défaut sur toutes les instances pour les événements d&#39;étapes de parcours. Vous ne pouvez pas modifier ni mettre à jour les schémas et les jeux de données créés lors de l’approvisionnement des événements d’étape. Par défaut, ces schémas et jeux de données sont en lecture seule.

Par exemple, vous avez configuré un parcours qui envoie plusieurs e-mails. Cette fonctionnalité permet de combiner les données de [!DNL Journey Orchestration] avec des données d’événements situés en aval, comme le nombre de conversions réalisées, le nombre d’engagements survenus sur le site web ou le nombre de transactions effectuées dans le magasin. Les informations de parcours sont combinées avec les données d’Adobe Experience Platform, à partir d’autres propriétés numériques ou de propriétés hors ligne, pour offrir une vue plus complète des performances.

[!DNL Journey Orchestration] crée automatiquement les schémas et les flux nécessaires dans les jeux de données de Adobe Experience Platform pour chaque étape d’un parcours individuel. Un événement d’étape correspond à un individu qui se déplace d’un nœud à un autre d’un parcours. Par exemple, dans le cadre d’un parcours comportant un événement, une condition et une action, trois événements d’étape sont envoyés à Adobe Experience Platform.

La liste des champs XDM transmis est complète. Certains contiennent des codes générés par le système et d’autres portent des noms conçus pour être lisibles. Il peut s’agir, par exemple, du libellé de l’activité de parcours ou du statut de l’étape : nombre de fois où une action a expiré ou s’est terminée par une erreur.

>[!CAUTION]
>
>Les jeux de données ne peuvent pas être activés pour le service de profil en temps réel. Assurez-vous que le bouton bascule **[!UICONTROL Profil]** est désactivé..

Les parcours envoient les données au fur et à mesure, en flux continu. Vous pouvez appliquer des requêtes à ces données à l’aide du service Requêtes. Vous pouvez vous connecter à Customer Journey Analytics ou à d’autres outils de BI pour visualiser les données concernant ces étapes.

Les schémas suivants sont créés :

* Schéma d’événement d’étape du parcours pour [!DNL Journey Orchestration] - Événement d’étape du parcours lié à des métadonnées de parcours.
* Schéma du parcours avec champs de parcours pour [!DNL Journey Orchestration] - Métadonnées servant à décrire les parcours.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

Les jeux de données suivants sont transmis :

* Événements d’étape du parcours
* Parcours

![](../assets/sharing3.png)

Les listes des champs XDM transmis à Adobe Experience Platform sont détaillées ici :

* [Liste des champs d’événement d’étape](../building-journeys/sharing-field-list.md)
* [Champs d’événement d’étape hérités](../building-journeys/sharing-legacy-fields.md)

Pour plus d’informations sur le reporting des événements d’étape à Adobe Experience Platform, regardez ce [tutoriel vidéo](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html?lang=fr).

## Intégration à Customer Journey Analytics{#integration-cja}

Les événements d’étape Journey Orchestration peuvent être liés à d’autres jeux de données dans [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=fr). Le workflow général est le suivant :

* Customer Journey Analytics ingère le jeu de données « Événement d’étape du parcours ».
* Le champ **profileID** dans le « schéma d’événement d’étape du parcours pour Journey Orchestration » associé est défini comme un champ d’identité. Dans Customer Journey Analytics, vous pouvez ensuite lier ce jeu de données à tout autre jeu de données ayant la même valeur que l’identifiant basé sur la personne.
* Si vous souhaitez utiliser ce jeu de données dans Customer Journey Analytics pour l’analyse de parcours cross-canal, reportez-vous à cette [documentation](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/cross-channel.html?lang=fr).
