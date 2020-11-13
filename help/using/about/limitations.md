---
title: Limites du Journey Orchestration
description: En savoir plus sur les limitations des Journey Orchestration
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: f45069225b284fe47e2acaccb4aa5d34fe171f35
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 33%

---


# Limitations {#limitations}

Voici les limites liées à l&#39;utilisation du Journey Orchestration.

## Limitations des actions générales

* Il n&#39;y a pas de limitation d&#39;envoi. 
* En cas d’erreur, deux reprises sont systématiquement effectuées. Vous ne pouvez pas adapter le nombre de reprises en fonction du message d’erreur renvoyé. 
* The built-in **Reaction** event allows you to react to out-of-the-box actions (see this [page](../building-journeys/reaction-events.md)). Si vous souhaitez réagir à un message envoyé par le biais d’une action personnalisée, vous devez configurer un événement dédié. 
* Il n&#39;y a pas d&#39;intégration productive à Adobe Campaign Classic.
 
## Limitations des actions personnalisées

* L’URL de l’action personnalisée ne prend pas en charge les paramètres dynamiques. 
* Seules les méthodes d’appel POST et PUT sont prises en charge. 
* Le nom du paramètre de requête ou de l’en-tête ne doit pas commencer par « . » ni par « $ ». 
* Les adresses IP ne sont pas autorisées. 
* Les adresses Adobe internes (.adobe.) ne sont pas autorisées.
 

## Limitations des actions Adobe Campaign

* Les messages transactionnels Adobe Campaign Standard ont une échelle de 50 000 messages par heure maximum sur tous les canaux pour une instance donnée. See [Adobe Campaign Standard Product Description](https://helpx.adobe.com/fr/legal/product-descriptions/campaign-standard.html). 
* L&#39;activité de qualification **de** segment ne doit pas être utilisée conjointement avec les messages transactionnels Adobe Campaign Standard en raison de contraintes de débit.
 
## Limites des événements

* Les données de diffusion en continu utilisées pour initier un parcours client doivent d’abord être configurées dans le Journey Orchestration pour obtenir un identifiant d’orchestration unique. Cet ID d’orchestration doit être ajouté à la charge utile de diffusion en flux continu entrant dans Adobe Experience Platform.
 

## Limitations des sources de données

* Les sources de données externes peuvent être exploitées au cours d’un parcours client pour rechercher des données externes en temps réel. Ces sources doivent être utilisables via l’API REST, prendre en charge JSON et être en mesure de gérer le volume de requêtes.