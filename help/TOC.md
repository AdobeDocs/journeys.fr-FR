---
product: Journeys
audience: end-user
user-guide-title: Aide de Journey Orchestration
index: true
translation-type: tm+mt
source-git-commit: 8a9c6e4f70ff88e60a85caff5e18a05070cf3f93
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 99%

---


# [!DNL Journey Orchestration] Aide {#using}

+ [Documentation du produit](journey-orchestration-home.md)
+ Nouveautés{#release-notes}
   + [Notes de mise à jour](using/release-notes/release-notes.md)
   + [Mises à jour de la documentation](using/release-notes/documentation-updates.md)
+ Prise en main de [!DNL Journey Orchestration] {#starting-with-journeys}
   + [À propos de [!DNL Journey Orchestration]](using/about/about-journey-orchestration.md)
   + [Prise en main](using/about/get-started.md)
   + [Interface utilisateur](using/about/user-interface.md)
   + [Gestion des accès](using/about/access-management.md)
   + [Résolution des problèmes](using/about/troubleshooting.md)
+ Configuration d’un événement {#events-journeys}
   + [À propos des événements](using/event/about-events.md)
   + [À propos des schémas ExperienceEvent](using/event/experience-event-schema.md)
   + [Définition des champs de payload](using/event/defining-the-payload-fields.md)
   + [Sélection de l’espace de noms](using/event/selecting-the-namespace.md)
   + [Définition de la clé d’événement](using/event/defining-the-event-key.md)
   + [Ajout d’une condition](using/event/adding-a-condition.md)
   + [Aperçu de la payload](using/event/previewing-the-payload.md)
   + [Étapes supplémentaires pour l’envoi d’événements](using/event/additional-steps-to-send-events-to-journey-orchestration.md)
+ Configuration d’une source de données {#data-source-journeys}
   + [À propos des sources de données](using/datasource/about-data-sources.md)
   + [Groupes de champs](using/datasource/field-groups.md)
   + [Source de données Adobe Experience Platform](using/datasource/adobe-experience-platform-data-source.md)
   + [Sources de données externes](using/datasource/external-data-sources.md)
+ Configuration d’une action {#action-journeys}
   + [À propos des actions](using/action/action.md)
   + [Utilisation d’Adobe Campaign](using/action/working-with-adobe-campaign.md)
   + Utilisation d’un système tiers {#action-third-party}
      + [À propos de la configuration des actions personnalisées](using/action/about-custom-action-configuration.md)
      + [Restrictions relatives aux actions personnalisées](using/action/custom-action-limitations.md)
      + [Configuration d’URL](using/action/url-configuration.md)
      + [Définition des paramètres de message](using/action/defining-the-message-parameters.md)
+ Utilisation des segments Plaform {#configuring-segment}
   + [À propos des segments Platform](using/segment/about-segments.md)
   + [Création d’un segment](using/segment/creating-a-segment.md)
   + [Utilisation de segments dans des conditions](using/segment/using-a-segment.md)
+ Création d’un parcours {#building-journeys}
   + À propos de la création de parcours {#about-journey-building}
      + [Création d’un parcours](using/building-journeys/journey.md)
      + [Utilisation du concepteur de parcours](using/building-journeys/using-the-journey-designer.md)
      + [Modification des propriétés](using/building-journeys/changing-properties.md)
      + [Versions de parcours](using/building-journeys/journey-versions.md)
      + [Terminaison d’un parcours](using/building-journeys/terminating-a-journey.md)
      + [Gestion des fuseaux horaires](using/building-journeys/timezone-management.md)
   + Activités {#about-journey-building}
      + Activités d’événement {#events-activities}
         + [À propos des activités d’événement](using/building-journeys/event-activities.md)
         + [Événements généraux](using/building-journeys/general-events.md)
         + [Événements de réaction](using/building-journeys/reaction-events.md)
         + [Événements de qualification de segment](using/building-journeys/segment-qualification-events.md)
      + Activités d’orchestration {#orchestration-activities}
         + [À propos des activités d’orchestration](using/building-journeys/about-orchestration-activities.md)
         + [Activité de condition](using/building-journeys/condition-activity.md)
         + [Activité de fin](using/building-journeys/end-activity.md)
         + [Activité d’attente](using/building-journeys/wait-activity.md)
      + Activités d’action {#action-activities}
         + [À propos des activités d’action](using/building-journeys/about-action-activities.md)
         + [Utilisation d’actions Adobe Campaign](using/building-journeys/using-adobe-campaign-actions.md)
         + [Utilisation d’actions personnalisées](using/building-journeys/using-custom-actions.md)
   + [Test du parcours](using/building-journeys/testing-the-journey.md)
   + [Publication du parcours](using/building-journeys/publishing-the-journey.md)
   + Partage d’étapes de parcours avec Adobe Experience Platform {#sharing-journey-steps}
      + [Présentation du partage des étapes du parcours](using/building-journeys/sharing-overview.md)
      + [Champs communs aux événements journeySteps](using/building-journeys/sharing-common-fields.md)
      + [Champs d’exécution d’action des événements journeyStep](using/building-journeys/sharing-execution-fields.md)
      + [Champs de récupération des données des événements journeyStep](using/building-journeys/sharing-fetch-fields.md)
      + [Champs d’identité des événements journeyStep](using/building-journeys/sharing-identity-fields.md)
      + [Champs du parcours](using/building-journeys/sharing-journey-fields.md)
+ Utilisation de l’éditeur d’expression avancé {#building-advanced-conditions-journeys}
   + [À propos de l’éditeur d’expression avancé](using/expression/expressionadvanced.md)
   + Syntaxe {#syntax}
      + [Généralités](using/expression/generalities.md)
      + [Instruction conditionnelle](using/expression/conditional-instruction.md)
      + [Types des données](using/expression/data-types.md)
      + [Références de champ](using/expression/field-references.md)
      + [Fonctions de gestion des collections](using/expression/collection-management-functions.md)
      + [Opérateurs](using/expression/operators.md)
      + [Exemples](using/expression/advanced-editor-use-cases.md)
   + Fonctions {#main-functions-journey}
      + [Fonctions principales](using/expression/functions.md)
      + Adobe Experience Platform {#adobe-experience-platform}
         + [inSegment](using/functions/functioninsegment.md)
      + Agrégation {#aggregation}
         + [avg](using/functions/functionavg.md)
         + [count](using/functions/functioncount.md)
         + [countOnlyNull](using/functions/functioncountonlynull.md)
         + [countWithNull](using/functions/functioncountwithnull.md)
         + [distinctCount](using/functions/functiondistinctcount.md)
         + [distinctCountWithNull](using/functions/functiondistinctcountwithnull.md)
         + [max](using/functions/functionmax.md)
         + [min](using/functions/functionmin.md)
         + [sum](using/functions/functionsum.md)
      + Conversion {#conversion}
         + [toBool](using/functions/functiontobool.md)
         + [toDateTime](using/functions/functiontodatetime.md)
         + [toDateTimeOnly](using/functions/functiontodatetimeonly.md)
         + [toDecimal](using/functions/functiontodecimal.md)
         + [toDuration](using/functions/functiontoduration.md)
         + [toInteger](using/functions/functiontointeger.md)
         + [toString](using/functions/functiontostring.md)
      + Date {#date}
         + [currentTime&#x200B;InMillis](using/functions/functioncurrenttimeinmillis.md)
         + [inLastDays](using/functions/functioninlastdays.md)
         + [inLastHours](using/functions/functioninlasthours.md)
         + [inLastMonths](using/functions/functioninlastmonths.md)
         + [inLastYears](using/functions/functioninlastyears.md)
         + [inNextDays](using/functions/functioninnextdays.md)
         + [inNextHours](using/functions/functioninnexthours.md)
         + [inNextMonths](using/functions/functioninnextmonths.md)
         + [inNextYears](using/functions/functioninnextyears.md)
         + [now](using/functions/functionnow.md)
         + [nowWithDelta](using/functions/functionnowwithdelta.md)
         + [setHours](using/functions/functionsethours.md)
         + [setDays](using/functions/functionsetdays.md)
      + Liste {#list}
         + [distinct](using/functions/functiondistinct.md)
         + [distinctWithNull](using/functions/functiondistinctwithnull.md)
         + [in](using/functions/functionin.md)
         + [listSize](using/functions/functionlistsize.md)
         + [serializeList](using/functions/functionserializelist.md)
         + [sort](using/functions/functionsort.md)
      + Mathématiques {#math}
         + [random](using/functions/functionrandom.md)
         + [round](using/functions/functionround.md)
      + Chaîne {#string}
         + [concat](using/functions/functionconcat.md)
         + [contain](using/functions/functioncontain.md)
         + [containWithIgnoreCase](using/functions/functioncontainwithignorecase.md)
         + [endWith](using/functions/functionendwith.md)
         + [endWithIgnorecase](using/functions/functionendwithignorecase.md)
         + [equalWithIgnoreCase](using/functions/functionequalignorecase.md)
         + [indexOf](using/functions/functionindexof.md)
         + [isEmpty](using/functions/functionisempty.md)
         + [isNotEmpty](using/functions/functionisnotempty.md)
         + [lastIndexOf](using/functions/functionlastindexof.md)
         + [length](using/functions/functionlength.md)
         + [lower](using/functions/functionlower.md)
         + [matchRegExp](using/functions/functionmatchregexp.md)
         + [notEqualWithIgnoreCase](using/functions/functionnotequalignorecase.md)
         + [replace](using/functions/functionreplace.md)
         + [replaceAll](using/functions/functionreplaceall.md)
         + [startWith](using/functions/functionstartwith.md)
         + [startWithIgnoreCase](using/functions/functionstartwithignorecase.md)
         + [substr](using/functions/functionsubstr.md)
         + [trim](using/functions/functiontrim.md)
         + [upper](using/functions/functionupper.md)
         + [uuid](using/functions/functionuuid.md)
+ Création de rapports{#journey-reports}
   + [À propos des rapports de parcours](using/reporting/about-journey-reports.md)
   + [Création de rapports de parcours](using/reporting/creating-your-journey-reports.md)
   + [Mesures et dimensions](using/reporting/metrics-and-dimensions.md)
+ Intégration des Services intelligents{#use-case-advanced}
   + [À propos de l’intégration de l’IA](using/ai-services/ai-services-overview.md)
   + [Utilisation de l’IA dédiée aux clients](using/ai-services/leveraging-customer-ai.md)
+ Cas d’utilisation{#use-cases-journeys}
   + Cas d’utilisation simple{#use-case-simple}
      + [À propos du cas d’utilisation simple](using/usecase/about-the-simple-use-case.md)
      + [Configuration de l’événement](using/usecase/configuring-the-event.md)
      + [Configuration de la source de données](using/usecase/configuring-the-data-source.md)
      + [Création du parcours](using/usecase/simple-uc-building-the-journey.md)
   + Cas d’utilisation avancé{#use-case-advanced}
      + [À propos du cas d’utilisation avancé](using/usecase/about-the-advanced-use-case.md)
      + [Configuration des événements](using/usecase/configuring-the-events.md)
      + [Configuration des sources de données](using/usecase/configuring-the-data-sources.md)
      + [Création du parcours](using/usecase/building-the-journey.md)
+ Utilisation des API{#working-with-apis}
   + [API de limitation](using/api/capping.md)
+ Fonctionnalités Alpha {#alpha}
   + [Présentation des fonctionnalités Alpha](using/alpha/alpha-overview.md)
   + [Interface utilisateur](using/alpha/alpha-interface.md)
   + [Lire l’activité de segment](using/alpha/alpha-segment-trigger.md)
   + [Événements basés sur des règles](using/alpha/alpha-events.md)

