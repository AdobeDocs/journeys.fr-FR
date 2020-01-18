---
title: Limitations des actions personnalisées
description: En savoir plus sur les limitations d’actions personnalisées
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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# Limitations des actions personnalisées {#concept_lh2_df1_2gb}

Voici quelques restrictions concernant l’utilisation d’actions personnalisées :

* Il n&#39;y a pas de plafonnement ni d&#39;envoi de la mise en mémoire tampon/du lissage du volume.
* Deux tentatives sont systématiquement effectuées en cas d’erreur. Vous ne pouvez pas ajuster le nombre de tentatives en fonction du message d’erreur reçu.
* L’événement **[!UICONTROL Réaction]**intégré vous permet de réagir à des actions prêtes à l’emploi (voir[](../building-journeys/event-activities.md). Si vous souhaitez réagir à un message envoyé via une action personnalisée, vous devez configurer un événement dédié.
* L’URL de l’action personnalisée ne prend pas en charge les paramètres dynamiques.
* Seules les méthodes d’appel POST et PUT sont prises en charge.
* Le nom du paramètre de requête ou de l’en-tête ne doit pas commencer par &quot;&quot;. ou &quot;$&quot;.
* Les adresses IP ne sont pas autorisées.
* Adresses Adobe internes (.adobe). ne sont pas autorisées.
