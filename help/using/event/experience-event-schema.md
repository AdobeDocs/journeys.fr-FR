---
title: 'À propos des schémas ExperienceEvent pour les événements Journey Orchestration '
description: 'En savoir plus sur les schémas ExperienceEvent pour les événements Journey Orchestration '
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 65%

---



# À propos des schémas ExperienceEvent pour les événements [!DNL Journey Orchestration]

Les événements [!DNL Journey Orchestration] sont des événements d’expérience XDM envoyés à Adobe Experience Platform par l’intermédiaire de l’ingestion en flux continu.

As such, an important prerequisite for setting up events for [!DNL Journey Orchestration] is that you are familiar with the Adobe Experience Platform’s Experience Data Model (or XDM) and how to compose XDM Experience Event schemas, as well as how to stream XDM-formatted data to the Adobe Experience Platform.

## Schéma requis pour les événements [!DNL Journey Orchestration]

The first step in setting up an event for [!DNL Journey Orchestration] is to ensure that you have an XDM schema defined to represent the event, and a dataset created to record instances of the event on the Adobe Experience Platform. Il n’est pas absolument nécessaire de disposer d’un jeu de données pour vos événements, mais envoyer les événements à un jeu de données spécifique permettra de conserver l’historique des événements des utilisateurs pour une consultation et une analyse ultérieures, ce qui est judicieux. Si vous ne disposez pas déjà d&#39;un schéma et d&#39;un jeu de données appropriés pour votre événement, ces deux tâches peuvent être effectuées dans l&#39;interface Web de Adobe Experience Platform.

![](../assets/schema1.png)

Un schéma XDM destiné aux événements [!DNL Journey Orchestration] doit répondre aux exigences suivantes :

* Le schéma doit appartenir à la classe XDM ExperienceEvent.

![](../assets/schema2.png)

* Le schéma doit contenir le mixin Orchestration eventID. [!DNL Journey Orchestration] emploie ce champ pour identifier les événements utilisés dans les parcours.

![](../assets/schema3.png)

* Vous devez déclarer un champ d’identité pour identifier le sujet de l’événement. Si aucune identité n’est spécifiée, un mapping d’identité peut être utilisée. Cette solution n’est pas recommandée.

![](../assets/schema4.png)

* Si vous souhaitez que ces données soient disponibles pour une recherche ultérieure dans un parcours, marquez le schéma et le jeu de données pour le profil.

![](../assets/schema5.png)

![](../assets/schema6.png)

* N’hésitez pas à inclure des champs de données pour recueillir toutes les autres données contextuelles que vous souhaitez incorporer à l’événement, telles que des informations relatives à l’utilisateur, l’appareil à partir duquel l’événement a été généré, l’emplacement ou toute autre circonstance significative liée à l’événement.

![](../assets/schema7.png)

![](../assets/schema8.png)