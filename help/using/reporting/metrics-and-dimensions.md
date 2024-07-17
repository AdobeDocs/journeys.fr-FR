---
product: adobe campaign
title: Mesures et dimensions
description: En savoir plus sur les dimensions et les mesures disponibles pour Journey Orchestration
feature: Journeys
role: User
level: Intermediate
exl-id: f6897011-0a5e-4094-a18e-ba2aa25f902c
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '1038'
ht-degree: 100%

---

# Mesures et dimensions {#concept_rfj_wpt_52b}

>[!NOTE]
>
>Les données de diffusion ne seront renseignées que si vous disposez d’Adobe Campaign Standard.

Cette section contient la liste de tous les composants disponibles dans les rapports dynamiques et leurs définitions.

Le tableau ci-dessous contient la liste des dimensions utilisées dans les différents rapports de parcours et leurs définitions.

Pour en savoir plus sur la compatibilité entre les dimensions et les mesures, consultez [cette page](../assets/do-not-localize/dynamic_report_compatibility_journey.pdf).

## Dimensions de parcours {#MBE_table_wk4_bnj_w2b}

Le tableau ci-dessous contient la liste des dimensions utilisées dans les différents rapports de parcours, ainsi que leurs définitions et leurs formules.

| Dimensions | Définition |
|--- |--- |
| **Action** | Liste de chaque action (**nom de l’action - libellé de l’action**) utilisée dans les parcours, par exemple Push – Confirmation de passage en caisse, E-mail - Fidélité récompensée. |
| **Source de données** | Liste des sources de données (**nom de la source de données**) utilisées pour enrichir les données des parcours, par exemple Adobe Experience Platform, système de réservation. |
| **[!UICONTROL Événement]** | Liste de chaque événement (**nom de l’événement - libellé de l’événement**) utilisé dans les parcours, par exemple Événement Geometrixx - Passage en caisse Geometrixx. |
| **Groupe de champs** | Liste des groupes de champs (**nom du groupe de champs**) utilisés pour enrichir les données des parcours, par exemple groupe de champs Profil, système de réservation Geometrixx. |
| **Parcours** | Liste de chaque parcours (**nom du parcours**) en mode test et actif, par exemple abandon de panier, notification de réservation d’hôtel. |
| **Version du parcours** | Liste de chaque version publiée d’un parcours (**nom du parcours + numéro de version**), par exemple abandon de panier v1, notification de réservation d’hôtel v2. |
| **Orchestration** | Liste de chaque activité d’orchestration (**Condition, Fin, Attente**) définie et utilisée dans les parcours. |

## Dimensions de diffusion {#delivery-dimensions}

Le tableau ci-dessous contient la liste des dimensions de diffusion utilisées dans les différents rapports de parcours, ainsi que leurs définitions et leurs formules.

| Dimension | Définition |
|--- |--- |
| **Browser** (Navigateur) | Navigateur dans lequel le message a été ouvert ou a fait l’objet d’un clic. |
| **Nom de la diffusion** | Libellé et identifiant de la diffusion. |
| **Appareil** | Appareil sur lequel l’email/le SMS/la notification push ont été ouverts/vus ou ont fait l’objet d’un clic. |
| **Type de message** | Canal utilisé pour la diffusion, par exemple e-mail, SMS, notification push ou In-App. |
| **Nom de l’application mobile** | Nom de l’application mobile. |
| **Plateforme** | Plateforme de l’appareil sur lequel le message a été ouvert/vu ou a fait l’objet d’un clic. |
| **[!UICONTROL Plateforme push]** | Plateforme de l’appareil sur lequel la notification push a été ouverte (iOS ou Android, par exemple). |
| **Domaine du destinataire** | Domaine utilisé pour ouvrir l’email. |
| **URL de tracking** | URL sur laquelle a cliqué l’utilisateur dans le message. |
| **Catégorie de l’URL de tracking** | Catégorie affectée à l’URL de tracking. |
| **Libellé de l’URL de tracking** | Libellé de l’URL (page miroir, contactez-nous, ou ouverture, par exemple). |
| **Variante** | Variante de l’email en cas de test A/B. |

## Mesures de parcours {#MBE_p_p22_c4j_w2b}

Le tableau ci-dessous contient la liste des mesures utilisées dans les différents rapports de parcours, ainsi que leurs définitions et leurs formules.

| Mesure | Définition |
|--- |---|
| **Terminé** | Nombre total d’individus qui ont normalement terminé le parcours. |
| **Taux d’achèvement** | Nombre total d’individus qui ont normalement terminé le parcours par rapport au nombre total qui sont entrés dans le parcours. |
| **Actuel** | Nombre total d’individus actuellement engagés dans le parcours, à savoir le nombre de personnes entrées moins celles qui sont sorties, les erreurs et les expirations de délai. |
| **Taux d’encours** | Nombre total d’individus actuellement engagés dans le parcours par rapport au nombre total qui sont entrés dans le parcours. |
| **Entrés** | Nombre total d’événements qui se sont produits pour démarrer une entrée individuelle dans le parcours. |
| **Erreur** | Nombre total d’erreurs survenues au cours d’un parcours, mais qui n’ont pas empêché sa réussite. |
| **Erreurs dans les actions** | Nombre total d’erreurs s’étant produites pour les actions. |
| **Erreurs dans un enrichissement** | Nombre total d’erreurs s’étant produites pour un enrichissement de données lors de l’appel d’une source de données/d’un groupe de champs. |
| **Erreurs dans les événements** | Nombre total d’erreurs s’étant produites pour les événements. |
| **Taux d’erreur** | Nombre total d’erreurs s’étant produites dans un parcours par rapport au nombre total des occurrences du parcours. |
| **Actions exécutées** | Nombre total d’actions exécutées pour un parcours. |
| **Enrichissements exécutés** | Nombre total d’enrichissements exécutés en appelant une source de données pour obtenir des groupes de champs spécifiques. |
| **Événements exécutés** | Nombre total d’actions exécutées pour un parcours. |
| **Orchestrations exécutées** | Nombre total d’objets d’orchestration (fin, attente, condition) exécutés pour un parcours. |
| **Échec** | Nombre total de parcours qui n’ont pas été exécutés avec succès. |
| **Taux d’échec** | Nombre total de parcours qui n’ont pas été exécutés avec succès par rapport au nombre de parcours exécutés. |

## Mesures de diffusion {#delivery-metrics}

Le tableau ci-dessous contient la liste des mesures utilisées dans les
différents rapports de parcours, ainsi que leurs définitions et leurs formules.

| Mesure | Définition |
|--- |--- |
| **Sur la liste bloquée** | Nombre de destinataires ayant déclaré un e-mail comme étant un spam ou un courrier indésirable. |
| **Taux de placement sur la liste bloquée** | Nombre total de messages sur la liste bloquée par rapport aux messages envoyés. |
| **Rebonds + erreurs** | Nombre total d’erreurs cumulées lors des diffusions et du traitement automatique des retours par rapport au nombre total de messages envoyés. |
| **Taux de rebond + erreurs** | Nombre total de messages qui ont fait l’objet d’un rebond par rapport aux messages envoyés. |
| **Cliquez sur** | Nombre de clics sur un contenu dans une diffusion. |
| **Taux de clics** | Nombre total de clics dans une diffusion par rapport au nombre de messages diffusés. |
| **Délivrés** | Nombre de messages envoyés avec succès, par rapport au nombre total de messages envoyés. |
| **Taux de délivrabilité** | Nombre total de messages diffusés avec succès par rapport aux messages envoyés. |
| **Erreur** | Nombre total d’erreurs s’étant produites au cours d’un parcours, mais qui n’ont pas empêché sa réussite. |
| Rebond définitif **** | Nombre total d’erreurs permanentes, telles qu’une adresse e-mail incorrecte. |
| **Taux de rebond définitif** | Nombre total de diffusions ayant échoué en raison d’erreurs permanentes par rapport aux messages envoyés. |
| **Page miroir** | Nombre de destinataires ayant cliqué sur le lien de la page miroir. |
| **Taux de page miroir** | Nombre total de clics sur le lien de la page miroir par rapport au nombre total de messages diffusés. |
| **Ouvrir** | Nombre d’ouvertures d’un message dans une diffusion. |
| **Taux d’ouverture** | Nombre total de messages ouverts par rapport au nombre de messages diffusés. |
| **Quarantaine** | Nombre de messages qui ont fait l’objet d’un rebond et qui ont entraîné la mise en quarantaine de l’adresse. |
| **Taux de mise en quarantaine** | Nombre total de mises en quarantaine par rapport aux messages envoyés. |
| **Rejetés** | Nombre de messages classés comme spam par les serveurs SMTP. |
| **Taux de rejet** | Nombre total de messages marqués comme rejetés par rapport aux messages envoyés. |
| **Traités/envoyés** | Nombre total d’envois pour la diffusion. |
| Rebond temporaire **** | Nombre total d’erreurs temporaires, telles qu’une boîte de réception pleine. |
| **Taux de rebonds temporaires** | Nombre total de diffusions ayant échoué en raison d’erreurs temporaires par rapport aux messages envoyés. |
| **Clics uniques** | Nombre de destinataires ayant cliqué sur un contenu dans une diffusion. |
| **Ouvertures uniques** | Nombre de destinataires ayant ouvert la diffusion. |
| **Désabonné** | Nombre de clics sur le lien de désabonnement. |
| **Taux de désabonnement** | Nombre total de désabonnements par destinataire par rapport au nombre de messages délivrés. |
