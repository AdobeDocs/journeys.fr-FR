---
product: adobe campaign
title: Mises à jour de la documentation
description: En savoir plus sur les mises à jour de la documentation
feature: Journeys
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: ac5d2cec-0b48-4863-afe3-19ac5f61c9fd
source-git-commit: af224593ca69f79c3e4458f26f77b92197ad73a2
workflow-type: tm+mt
source-wordcount: '1021'
ht-degree: 100%

---

# Mises à jour de la documentation

Cette page répertorie toutes les mises à jour de la documentation d&#39;[!DNL Journey Orchestration].
Vous pouvez également consulter les [notes de mise à jour](../release-notes/release-notes.md) de [!DNL Journey Orchestration].

## Juillet 2022 {#july-2022}

* Dans les propriétés du parcours, l’option **Fuseau horaire du profil** est désormais désactivée par défaut. [En savoir plus](../building-journeys/timezone-management.md#timezone-from-profiles)
* Dans l’activité **Attente**, l’option **Date fixe** n’est plus disponible. [En savoir plus](../building-journeys/wait-activity.md)

## Juin 2022 {#june-2022}

* De nouveaux exemples de requête ont été ajoutés à cette [page](../building-journeys/query-examples.md).

## Mars 2022 {#march-2022}

* Ajout d’un exemple sur l’ajout d’une expression en tant que valeur par défaut dans l’éditeur d’expression. [En savoir plus](../expression/field-references.md#default-value)

## Février 2022 {#feb-2022}

* Les pages de documentation des fonctions [replace](../functions/functionreplace.md#example_2) et [replaceAll](../functions/functionreplaceall.md#example) ont été mises à jour avec des informations supplémentaires et des exemples concernant le paramètre cible.
* Les bonnes pratiques ont été ajoutées à la page [Opérateurs](../expression/operators.md#important-notes).

## Septembre 2021

* Les pages de fonctions suivantes ont été mises à jour : [sethours](../functions/functionsethours.md), [getListItem](../functions/functiongetlistitem.md), [inSegment](../functions/functioninsegment.md)

* Les fonctions suivantes ont été ajoutées : [filter](../functions/functionfilter.md), [intersect](../functions/functionintersect.md), [toDateOnly](../functions/functiontodateonly.md)

* Le type de date dateOnly a été ajouté à la documentation de l’éditeur d’expression. [En savoir plus](../expression/data-types.md)

* Ajout d’informations sur la durée de mise en cache des actions personnalisées. [En savoir plus](../datasource/external-data-sources.md#section_wjp_nl5_nhb)

* Ajout d’informations sur les ports par défaut des actions personnalisées. [En savoir plus](../action/url-configuration.md)

* Ajout d’exemples fréquemment utilisés pour interroger les événements d’étape de parcours dans le lac de données. [En savoir plus](../building-journeys/query-examples.md)

## Août 2021

* Mise à jour de la procédure de configuration pour les actions personnalisées avec les chemins d’URL dynamiques et les en-têtes dynamiques. [En savoir plus](../action/url-configuration.md)
* Ajout d’une section sur les fonctionnalités d’accessibilité. [En savoir plus](../about/user-interface.md#accessibility)
* Ajout d’une section sur les méthodes d’évaluation de segment. [En savoir plus](../segment/about-segments.md#evaluation-method-in-journey-orchestration)

## Mars 2021 {#march-2021}

* Nous avons détaillé la procédure complète de création de profils de test dans Adobe Experience Platform. [En savoir plus](../building-journeys/creating-test-profiles.md).

## Janvier 2021 {#january-2021}

* Bonnes pratiques ajoutées lors du déclenchement d’un parcours en même temps qu’une création de profil. [En savoir plus](../about/limitations.md#journeys-limitation-profile-creation).

## Octobre 2020 {#october-2020}

* Ajout d’informations sur la façon de configurer un délai d’expiration pour un événement. [En savoir plus](../building-journeys/event-activities.md#listening-to-events-during-a-specific-time).

## Septembre 2020 {#september-2020}

* Mise à jour de la section de description de l’interface pour prendre en compte le nouveau menu **Tout sélecteur**. [En savoir plus](../about/user-interface.md)
* Ajout d’une note sur les nouvelles versions des parcours basés sur les segments qui ne sont pas récurrents.

## Août 2020 {#august-2020}

* Ajout d’informations sur le tri et la sélection des colonnes à afficher dans la liste des segments. [En savoir plus](../building-journeys/segment-qualification-events.md)
* Ajout d’informations sur la copie du nom et de l’identifiant d’un segment après sa sélection. [En savoir plus](../building-journeys/segment-qualification-events.md)
* Harmonisation des occurrences d’Experience Platform dans les différentes pages.

## Juillet 2020 {#july-2020}

* Ajout à Adobe Experience Platform d’un lien vers un nouveau tutoriel vidéo sur les rapports des événements d’étape. [En savoir plus](../building-journeys/sharing-overview.md)
* La section sur les activités des événements a été réorganisée en sous-sections dédiées à chaque type d’événement. [En savoir plus](../building-journeys/event-activities.md)
* Ajout de bonnes pratiques pour éviter la surcharge avec la qualification de segment. [En savoir plus](../building-journeys/segment-qualification-events.md#speed-segment-qualification)
* Ajout d’une note expliquant comment faire pour qu’un parcours continue après une erreur dans une action ou une condition. [En savoir plus](../about/troubleshooting.md#section_h3q_kqk_fhb)
* Ajout d’une nouvelle section sur les fonctionnalités Alpha qui sont testées auprès d’un nombre limité de clients.
* Ajout d’une nouvelle section sur l’intégration avec les Services intelligents. [En savoir plus](../ai-services/ai-services-overview.md)
* Ajout d’une nouvelle section sur la création de profils de test. [En savoir plus](../building-journeys/testing-the-journey.md)
* Ajout d’informations sur l’utilisation du nœud **[!UICONTROL SegmentQualification]** dans une condition ou une action de parcours. [En savoir plus](../building-journeys/segment-qualification-events.md)
* Ajout d’une note à la publication des messages transactionnels et des événements de Campaign. Voir [Utilisation d’Adobe Campaign](../action/working-with-adobe-campaign.md) et [Utilisation d’actions Adobe Campaign](../building-journeys/using-adobe-campaign-actions.md).
* Des informations ont été ajoutées sur les vérifications effectuées lors du test de l’URL de l’instance Campaign Standard. [En savoir plus](../action/working-with-adobe-campaign.md)
* Des informations ont été ajoutées sur la compatibilité des événements de réaction avec les instances Campaign Standard hébergées sur des serveurs AWS ou Azure. [En savoir plus](../building-journeys/reaction-events.md)
* Une note a été ajoutée sur la nécessité de configurer une règle de limitation lors de l’utilisation de la messagerie transactionnelle Campaign Standard. [En savoir plus](../action/working-with-adobe-campaign.md)
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
  <!--* The [getBestSendTime documentation](../functions/functiongetbestsendtime.md) has been updated.-->

## Décembre 2019 {#december-2019}

* Toutes les captures d’écran ont été mises à jour afin de prendre en compte les modifications de l’interface.
* La section du mode test a été mise à jour. [En savoir plus](../building-journeys/testing-the-journey.md)
  <!--* A warning has been added in the [email send time optimization](../building-journeys/wait-activity.md) and [predictive fatigue scores](../ai-services/leveraging-fatigue-scores.md) sections. These capabilities are only available to customers who use the [Adobe Experience Platform Data Connector](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-about-data-connector.html).-->
* Il est maintenant possible de supprimer les parcours arrêtés. Les pages de documentation connexes ont été mises à jour.
* Deux couleurs s’affichent maintenant lorsque des problèmes sont détectés dans un parcours. Rouge pour les erreurs et orange pour les avertissements. [En savoir plus](../about/troubleshooting.md)
* La section de l’éditeur d’expression avancé a été mise à jour. [En savoir plus](../expression/expressionadvanced.md).
* Les sections [Instructions conditionnelles](../expression/conditional-instruction.md) et [Gestion des collections](../expression/collection-management-functions.md) ont été déplacées et mises à jour.
* La section [Fonctions](../expression/functions.md) a été mise à jour avec de nouveaux exemples.
* La documentation de la [fonction toDateTime](../functions/functiontodatetime.md) a été mise à jour pour prendre en compte les modifications de la syntaxe des fuseaux horaires.
