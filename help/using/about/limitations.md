---
product: adobe campaign
solution: Journey Orchestration
title: Limites de Journey Orchestration
description: En savoir plus sur les limites de Journey Orchestration
translation-type: tm+mt
source-git-commit: a0b6f54e37abded690dc200bc3a901a8e0f04f79
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 93%

---


# Limitations {#limitations}

Voici les limites liées à l’utilisation de Journey Orchestration.

## Limites des actions générales

* Il n’y a pas de limite d’envoi. 
* En cas d’erreur, deux reprises sont systématiquement effectuées. Vous ne pouvez pas adapter le nombre de reprises en fonction du message d’erreur renvoyé. 
* L’événement **Réaction** intégré vous permet de réagir aux actions d’usine (voir cette [page](../building-journeys/reaction-events.md)). Si vous souhaitez réagir à un message envoyé par le biais d’une action personnalisée, vous devez configurer un événement dédié. 
* Il n’y a pas d’intégration de produit avec Adobe Campaign Classic.

## Limites des versions de parcours {#journey-versions-limitations}

* un parcours commençant par une activité d’événement dans v1 ne peut pas débuter avec un autre élément qu’un événement dans d’autres versions. Vous ne pouvez pas débuter un parcours avec un événement de **qualification de segment**.
* un parcours commençant par une activité **Qualification de segment** dans v1 doit toujours débuter avec une **Qualification de segment** dans d’autres versions.
* Le segment et l’espace de noms sélectionné dans **Qualification de segment** (premier nœud) ne peut pas être modifié dans les nouvelles versions.
* La règle de nouvelle entrée doit être la même dans toutes les versions de parcours.

## Qualification du segment {#segment-qualification}

* L’activité **Qualification de segment** ne peut pas être utilisée conjointement avec les messages transactionnels Adobe Campaign Standard en raison de contraintes de débit. Voir [Description du produit Adobe Campaign Standard](https://helpx.adobe.com/fr/legal/product-descriptions/campaign-standard.html). 
  

## Limites des actions personnalisées

* L’URL de l’action personnalisée ne prend pas en charge les paramètres dynamiques. 
* Seules les méthodes d’appel POST et PUT sont prises en charge. 
* Le nom du paramètre de requête ou de l’en-tête ne doit pas commencer par « . » ni par « $ ». 
* Les adresses IP ne sont pas autorisées. 
* Les adresses Adobe internes (.adobe.) ne sont pas autorisées.
 

## Limites des actions Adobe Campaign

* Les messages transactionnels Adobe Campaign Standard ont une échelle de 50 000 messages par heure maximum sur tous les canaux pour une instance donnée. Voir [Description du produit Adobe Campaign Standard](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
  

## Limites des événements

* Pour les événements générés par le système, les données en flux continu utilisées pour lancer un parcours client doivent d’abord être configurées dans la gestion des Parcours client pour obtenir un identifiant d’orchestration unique. Cet Identifiant d’orchestration doit être ajouté à la payload de diffusion en continu entrant dans Adobe Experience Platform. Cette limitation ne s’applique pas aux événements basés sur des règles.
 

## Limites des sources de données

* Les sources de données externes peuvent être exploitées au cours d’un parcours client pour rechercher des données externes en temps réel. Ces sources doivent être utilisables via l’API REST, prendre en charge JSON et être en mesure de gérer le volume de requêtes.

## Parcours commençant en même temps qu’une création de profil {#journeys-limitation-profile-creation}

Un délai est associé à la création/la mise à jour de profils basés sur l’API dans Adobe Experience Platform. La cible de niveau de service (TSL) en termes de latence est d’atteindre moins de 1 minute entre l&#39;ingestion et le profil unifié pour 95 % des demandes, avec un volume de 20K demandes par seconde (DPS).

Si un parcours est déclenché simultanément à la création d’un profil et qu’il vérifie/récupère immédiatement des informations auprès du service de profil, il est possible qu&#39;il ne fonctionne pas correctement.

Vous pouvez choisir l’une des deux solutions suivantes :

* Ajouter une activité d’attente après le premier événement pour donner à Adobe Experience Platform le temps nécessaire pour exécuter l’ingestion sur le service de profil.

* Configurer un parcours qui n’utilise pas immédiatement le profil. Par exemple, si le parcours est conçu pour confirmer la création d’un compte, l’événement d’expérience peut contenir les informations nécessaires à l’envoi du premier message de confirmation (prénom, nom, adresse électronique, etc.).