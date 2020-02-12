---
title: Restrictions relatives aux actions personnalisées
description: En savoir plus sur les restrictions relatives aux actions personnalisées
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: ht
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# Restrictions relatives aux actions personnalisées {#concept_lh2_df1_2gb}

Voici quelques restrictions concernant l’utilisation des actions personnalisées :

* Il n’y a pas de limitation ni de lissage/mise en mémoire tampon concernant le volume d’envoi.
* En cas d’erreur, deux reprises sont systématiquement effectuées. Vous ne pouvez pas adapter le nombre de reprises en fonction du message d’erreur renvoyé.
* L’événement **[!UICONTROL Réaction]** intégré vous permet de réagir aux actions d’usine (voir [](../building-journeys/event-activities.md). Si vous souhaitez réagir à un message envoyé par le biais d’une action personnalisée, vous devez configurer un événement dédié.
* L’URL de l’action personnalisée ne prend pas en charge les paramètres dynamiques.
* Seules les méthodes d’appel POST et PUT sont prises en charge.
* Le nom du paramètre de requête ou de l’en-tête ne doit pas commencer par « . » ni par « $ ».
* Les adresses IP ne sont pas autorisées.
* Les adresses Adobe internes (.adobe.) ne sont pas autorisées.
