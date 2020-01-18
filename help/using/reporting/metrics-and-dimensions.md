---
title: Mesures et dimensions
description: En savoir plus sur les dimensions et les mesures disponibles pour l’orchestration du voyage
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# Mesures et dimensions {#concept_rfj_wpt_52b}

>[!NOTE]
>
>Les données de remise ne seront renseignées que si vous disposez d’Adobe Campaign Standard.

Vous trouverez ici la liste de tous les composants disponibles dans les rapports dynamiques ainsi que leurs définitions.

Le tableau ci-dessous présente la liste des dimensions utilisées dans les rapports de voyage et leurs définitions.

To learn more on compatibility between dimensions and metrics, refer to [this page](../assets/do-not-localize/dynamic_report_compatibility_journey.pdf).

## Dimensions du parcours {#MBE_table_wk4_bnj_w2b}

Le tableau ci-dessous présente la liste des dimensions utilisées dans les rapports de voyage, leurs définitions et leurs formules.

| Dimensions | Définition |
|--- |--- |
| **Action** | Liste de chaque action (nom de l&#39;**action - étiquette** d&#39;action) utilisée dans les voyages, par exemple Push - Check out confirmation, Email - Rewards fidelity. |
| **Source de données** | Liste des sources de données (nom **de la source de** données) utilisées pour enrichir les données lors d’un voyage, par exemple, plateforme d’expérience, système de réservation. |
| **[!UICONTROL Event]** | Liste de chaque événement (nom de l’**événement - étiquette** de l’événement) utilisé dans les voyages, par exemple événement Geometrixx - Extraction de Geometrixx. |
| **Groupe de champs** | Liste des groupes de champs (nom **du groupe de** champs) utilisés pour enrichir les données dans les voyages, par exemple le groupe de champs Profil, le système de réservation Geometrixx. |
| **Parcours** | Liste de chaque voyage (nom **du** voyage) en mode test et en direct, par exemple abandon de panier, notification de réservation d&#39;hôtel. |
| **Version de voyage** | Liste de chaque version publiée d&#39;un voyage (nom du **voyage + numéro** de la version), par exemple abandon de panier v1, notification de réservation d&#39;hôtel v2. |
| **Orchestration** | Liste de chaque activité d’orchestration (**Condition, Fin, Attente**) définie et utilisée dans les voyages. |

## Dimensions de remise {#delivery-dimensions}

Le tableau ci-dessous présente la liste des dimensions de livraison utilisées dans les rapports de voyage, leurs définitions et leurs formules.

| Dimension | Définition |
|--- |--- |
| **Navigateur** | Navigateur dans lequel le message a été ouvert ou a fait l&#39;objet d&#39;un clic. |
| **Nom de remise** | Libellé et identifiant de la diffusion. |
| **Appareil** | Appareil sur lequel l&#39;email/le SMS/la notification push ont été ouverts/vus ou ont fait l&#39;objet d&#39;un clic. |
| **Type de message** | Canal utilisé pour la diffusion, par exemple email, SMS, notification push ou In-App. |
| **Nom de l&#39;application mobile** | Nom de l&#39;application mobile. |
| **Plate-forme** | Plateforme de l&#39;appareil sur lequel le message a été ouvert/vu ou a fait l&#39;objet d&#39;un clic. |
| **[!UICONTROL Plateforme push]** | Plateforme de l&#39;appareil sur lequel la notification push a été ouverte (iOS ou Android, par exemple). |
| **Domaine du destinataire** | Domaine utilisé pour ouvrir l&#39;email. |
| **URL de tracking** | URL sur laquelle a cliqué l&#39;utilisateur dans le message. |
| **Catégorie de l&#39;URL de tracking** | Catégorie affectée à l&#39;URL de tracking. |
| **Libellé de l&#39;URL de tracking** | Libellé de l&#39;URL (page miroir, contactez-nous ou ouvrir, par exemple). |
| **Variante** | Variante de l&#39;email en cas de test A/B. |


## Mesures de parcours {#MBE_p_p22_c4j_w2b}

Le tableau ci-dessous présente la liste des mesures utilisées dans les rapports de voyage, leurs définitions et leurs formules.

| Mesure | Définition |
|--- |---|
| **Terminé** | Nombre total de personnes qui ont normalement terminé le voyage. |
| **Taux d&#39;achèvement** | Nombre total de personnes qui ont normalement terminé le voyage par rapport au nombre total de personnes qui sont entrées dans le voyage. |
| **Actuel** | Nombre total de personnes actuellement en cours de voyage, c&#39;est-à-dire combien de personnes sont entrées moins les personnes qui sont sorties, ont commis des erreurs et ont dépassé le délai d&#39;expiration. |
| **Taux actuel** | Nombre total de personnes actuellement en voyage par rapport au nombre de personnes qui sont entrées dans le voyage. |
| **Entré** | Nombre total d&#39;événements qui se sont produits pour démarrer une entrée individuelle dans le voyage. |
| **Erreur** | Nombre total d&#39;erreurs survenues au cours d&#39;un voyage, mais qui n&#39;ont pas empêché le parcours de réussir. |
| **Erreur en action** | Nombre total d’erreurs survenues pour les actions. |
| **Erreur d&#39;enrichissement** | Nombre total d’erreurs survenues pour un enrichissement de données lors de l’appel d’une source de données/d’un groupe de champs. |
| **Erreur dans l&#39;événement** | Nombre total d’erreurs survenues pour les événements. |
| **Taux d&#39;erreur** | Nombre total d’erreurs survenues au cours d’un voyage par rapport au nombre total d’occurrences du voyage. |
| **Action exécutée** | Nombre total d’actions exécutées pour un voyage. |
| **Enrichissement exécuté** | Nombre total d&#39;enrichissements exécutés en appelant une source de données pour obtenir des groupes de champs spécifiques. |
| **Événement exécuté** | Nombre total d’actions exécutées pour un voyage. |
| **Orchestration exécutée** | Nombre total d’objets d’orchestration (fin, attente, condition) exécutés pour un voyage. |
| **En échec** | Nombre total de voyages qui n&#39;ont pas été exécutés avec succès. |
| **Taux d&#39;échec** | Nombre total de voyages qui n&#39;ont pas été exécutés avec succès par rapport au nombre de voyages d&#39;exécution. |

## Mesures de diffusion {#delivery-metrics}

Le tableau ci-dessous présente la liste des mesures utilisées dans les rapports de voyage, leurs définitions et leurs formules.

| Mesure | Définition |
|--- |--- |
| **En blackliste** | Nombre de destinataires ayant déclaré un email comme étant un spam ou un courrier indésirable. |
| **Taux d&#39;éléments en blackliste** | Nombre total de messages marqués comme bloqués par rapport aux messages envoyés. |
| **Bounces + erreurs** | Nombre total d&#39;erreurs cumulées lors des diffusions et du traitement automatique des retours par rapport au nombre total de messages envoyés. |
| **Rebonds + taux d’erreur** | Nombre total de messages qui rebondissent par rapport aux messages envoyés. |
| **Clic** | Nombre de clics sur un contenu dans une diffusion. |
| **Taux de clics** | Nombre total de clics dans une remise par rapport au nombre de messages remis. |
| **Delivrés** | Nombre de messages envoyés avec succès, par rapport au nombre total de messages envoyés. |
| **Taux de délivrabilité** | Nombre total de messages transmis avec succès par rapport aux messages envoyés. |
| **Erreur** | Nombre total d&#39;erreurs survenues au cours d&#39;un voyage, mais qui n&#39;ont pas empêché le parcours de réussir. |
| **Hard bounce** | Nombre total d&#39;erreurs permanentes, telles qu&#39;une adresse email incorrecte. |
| **Taux de hard bounce** | Nombre total de remises ayant échoué en raison d’erreurs permanentes par rapport aux messages envoyés. |
| **Page miroir** | Nombre de destinataires ayant cliqué sur le lien de la page miroir. |
| **Taux de page miroir** | Nombre total de clics sur le lien de la page miroir par rapport au nombre total de messages distribués. |
| **Ouvertures** | Nombre d&#39;ouvertures d&#39;un message dans une diffusion. |
| **Taux d&#39;ouverture** | Nombre total de messages ouverts par rapport au nombre de messages remis. |
| **Quarantaine** | Nombre de messages qui ont fait l&#39;objet d&#39;un bounce et qui ont entraîné la mise en quarantaine de l&#39;adresse. |
| **Taux de mise en quarantaine** | Nombre total de mises en quarantaine par rapport aux messages envoyés. |
| **Rejetés** | Nombre de messages classés comme spam par les serveurs SMTP. |
| **Taux de rejet** | Nombre total de messages marqués comme rejetés par rapport aux messages envoyés. |
| **Traités/envoyés** | Nombre total d&#39;envois pour la diffusion. |
| **Soft bounce** | Nombre total d&#39;erreurs permanentes, telles qu&#39;une boîte de réception pleine. |
| **Taux de soft bounces** | Nombre total de remises ayant échoué en raison d’une raison temporaire par rapport aux messages envoyés. |
| **Clics uniques** | Nombre de destinataires ayant cliqué sur un contenu dans une diffusion. |
| **Ouvertures uniques** | Nombre de destinataires ayant ouvert la diffusion. |
| **Désabonné** | Nombre de clics sur le lien de désinscription. |
| **Taux de désabonnement** | Nombre total de désabonnements par destinataire par rapport aux messages diffusés. |
