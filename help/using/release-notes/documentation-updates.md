---
title: Mises à jour de la documentation
description: En savoir plus sur les mises à jour de la documentation
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
source-git-commit: 71b5b1ecd20056d0103ae1a8b83a31478449e844
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 91%

---


# Mises à jour de la documentation

Cette page répertorie toutes les mises à jour de la documentation de [!DNL Journey Orchestration].
Vous pouvez également consulter les [notes de mise à jour](../release-notes/release-notes.md) de [!DNL Journey Orchestration].

## Juillet 2020 {#july-2020}

* Ajouté un lien vers un nouveau didacticiel vidéo sur les événements pas rapports à Adobe Experience Platform. [En savoir plus](../building-journeys/sharing-overview.md)
* La section activités des événements a été réorganisée en sous-sections dédiées à chaque type de événement. [En savoir plus](../building-journeys/event-activities.md)
* Meilleures pratiques Ajoutées pour éviter la surcharge avec la classification des segments. [En savoir plus](../building-journeys/segment-qualification-events.md#speed-segment-qualification)
* Ajouté une note expliquant comment poursuivre un voyage après une erreur dans une action ou une condition. [En savoir plus](../about/troubleshooting.md#section_h3q_kqk_fhb)
* Ajout d’une nouvelle section sur les fonctionnalités Alpha qui sont testées auprès d’un nombre limité de clients. [En savoir plus](../alpha/alpha-overview.md)
* Ajout d’une nouvelle section sur l’intégration avec les Services intelligents. [En savoir plus](../ai-services/ai-services-overview.md)
* Ajout d’une nouvelle section sur la création de profils de test. [En savoir plus](../building-journeys/testing-the-journey.md#create-test-profile)
* Ajout d’informations sur l’utilisation du nœud **[!UICONTROL Qualification de segment]** dans une condition ou une action de parcours. [En savoir plus](../building-journeys/segment-qualification-events.md)
* Ajout d’une note à la publication des messages transactionnels et des événements de Campaign. Voir [Utilisation d’Adobe Campaign](../action/working-with-adobe-campaign.md) et [Utilisation d’actions Adobe Campaign](../building-journeys/using-adobe-campaign-actions.md).
* Des informations ont été ajoutées sur les vérifications effectuées lors du test de l’URL de l’instance Campaign Standard. [En savoir plus](../action/working-with-adobe-campaign.md)
* Des informations ont été ajoutées sur la compatibilité des événements de réaction avec les instances Campaign Standard hébergées sur des serveurs AWS ou Azure. [En savoir plus](../building-journeys/reaction-events.md)
* Une note a été ajoutée sur la nécessité de configurer une règle de limitation lors de l’utilisation de la messagerie transactionnelle Campaign Standard. [En savoir plus](../action/working-with-adobe-campaign.md)
* Une note a été ajoutée sur la génération d’événements réels lors du déclenchement des événements à l’aide du mode test. [En savoir plus](../building-journeys/testing-the-journey.md#firing_events)

## Juin 2020 {#june-2020}

* Ajout d’informations concernant la modification de la durée de mise en cache du jeton pour une source de données d’authentification personnalisée. [En savoir plus](../datasource/external-data-sources.md#section_wjp_nl5_nhb)
* Mise à jour des captures d’écran et du texte pour prendre en compte le changement de nom de l’état de parcours **[!UICONTROL Terminé]** en **[!UICONTROL Fermé (aucune entrée)]**.
* Ajout d’informations concernant la définition de la langue pour l’interface. [En savoir plus](../about/user-interface.md)
* Déplacement de la liste des statuts du parcours d’un individu vers la section [Journaux du mode test](../building-journeys/testing-the-journey.md#viewing_logs).

## Avril 2020 {#april-2020}

* Ajout d’une nouvelle section concernant la définition du schéma des événements d’expérience pour aider les utilisateurs à configurer leur premier événement. [En savoir plus](../event/experience-event-schema.md)
* Mise à jour de la page d’accueil de la documentation [!DNL Journey Orchestration] avec des liens utiles supplémentaires. [En savoir plus](../../journey-orchestration-home.md)

## Mars 2020 {#march-2020}

* Ajout de descriptions de paramètre pour _actionExecutionErrors_ et _fetchErrors_ dans la section des journaux de test. [En savoir plus](../building-journeys/testing-the-journey.md#viewing_logs)
* Les limites des actions personnalisées utilisées dans un parcours ont été mises à jour. Vous pouvez également modifier le champ **[!UICONTROL URL]** et les paramètres d’**[!UICONTROL authentification]**. [En savoir plus](../action/about-custom-action-configuration.md)
* De nouvelles entrées d’aide contextuelle ont été ajoutées. Le volet relatif à la payload de l’authentification personnalisée (dans les actions et les sources de données) comprend maintenant une icône d’aide qui pointe vers cette [section](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
* Il est maintenant possible d’arrêter les parcours fermés. [En savoir plus](../building-journeys/using-the-journey-designer.md)
* La section de description de l’interface a été réorganisée. [En savoir plus](../about/user-interface.md)
* Des informations sur le déclenchement de plusieurs événements ont été ajoutées à la section sur le mode test [En savoir plus](../building-journeys/testing-the-journey.md#firing_events)
* La section sur le mode test a été mise à jour avec des informations concernant le nouveau paramètre **[!UICONTROL Temps d’attente en test]**. [En savoir plus](../building-journeys/testing-the-journey.md)
* La section sur les journaux de test a été mise à jour avec des informations sur les codes d’erreur et les réponses des appels externes. [En savoir plus](../building-journeys/testing-the-journey.md#viewing_logs)
* La gestion des fuseaux horaires est maintenant centralisée dans le panneau des propriétés du parcours. En savoir plus [ici](../building-journeys/changing-properties.md#timezone) et [ici](../building-journeys/timezone-management.md)
* La section Concepteur de parcours a été mise à jour pour prendre en compte les améliorations récentes. [En savoir plus](../building-journeys/using-the-journey-designer.md)
* La description de l’interface a été mise à jour avec des informations sur l’aide contextuelle. [En savoir plus](../about/user-interface.md#section_ksq_zr1_ffb)
* Lorsque vous parcourez les **champs XDM**, le nom convivial s’affiche désormais. Les sections connexes ont été mises à jour. [En savoir plus](../about/user-interface.md#friendly-names-display)

## Février 2020 {#february-2020}

* La section concernant les raccourcis a été mise à jour. Le raccourci clavier **C** vous permet de créer un élément dans tous les écrans de liste. [En savoir plus](../about/user-interface.md#section_ksq_zr1_ffb)
* Amélioration des pages de vue d’ensemble des sections [source de données](../datasource/about-data-sources.md) et [action](../action/action.md).

## Janvier 2020 {#january-2020}

* Des limites de récupération ont été ajoutées pour les [événements d’expérience](../datasource/adobe-experience-platform-data-source.md) et les [segments](../functions/functioninsegment.md).
* La [documentation getBestSendTime](../functions/functiongetbestsendtime.md) a été mise à jour.

## Décembre 2019 {#december-2019}

* Toutes les captures d’écran ont été mises à jour afin de prendre en compte les modifications de l’interface.
* La section du mode test a été mise à jour. [En savoir plus](../building-journeys/testing-the-journey.md)
* Un avertissement a été ajouté dans les sections [Optimisation de l’heure d’envoi des emails](../building-journeys/wait-activity.md) et [Score de fatigue prédictif](../ai-services/leveraging-fatigue-scores.md). Ces fonctionnalités ne sont disponibles que pour les clients qui utilisent la fonction Service de données d’Adobe Campaign Standard.
* Il est maintenant possible de supprimer les parcours arrêtés. Les pages de documentation connexes ont été mises à jour.
* Deux couleurs s’affichent maintenant lorsque des problèmes sont détectés dans un parcours. Rouge pour les erreurs et orange pour les avertissements. [En savoir plus](../about/troubleshooting.md)
* La section de l’éditeur d’expression avancé a été mise à jour. [En savoir plus](../expression/expressionadvanced.md).
* Les sections [Instructions conditionnelles](../expression/conditional-instruction.md) et [Gestion des collections](../expression/collection-management-functions.md) ont été déplacées et mises à jour.
* La section [Fonctions](../expression/functions.md) a été mise à jour avec de nouveaux exemples.
* La documentation de la [fonction toDateTime](../functions/functiontodatetime.md) a été mise à jour pour prendre en compte les modifications de la syntaxe des fuseaux horaires.
