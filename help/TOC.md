---
product: Journeys
audience: end-user
user-guide-title: Journey Orchestration Help
index: true
translation-type: tm+mt
source-git-commit: 22569d66acb1637efc346f77864302b9e2cb6070

---


# Aide sur l’orchestration du voyage {#using}

+ [Documentation du produit](journey-orchestration-home.md)
+ What&#39;s new {#release-notes}
   + [Notes de mise à jour](using/release-notes/release-notes.md)
   + [Mises à jour de la documentation](using/release-notes/documentation-updates.md)
+ Commencer par Orchestration du voyage {#starting-with-journeys}
   + [À propos de l&#39;orchestration du voyage](using/about/about-journey-orchestration.md)
   + [Prise en main](using/about/get-started.md)
   + [Interface utilisateur](using/about/user-interface.md)
   + [Gestion des accès](using/about/access-management.md)
   + [Résolution des problèmes](using/about/troubleshooting.md)
+ Configuration d’un événement {#events-journeys}
   + [A propos des événements](using/event/about-events.md)
   + [Définition des champs de charge utile](using/event/defining-the-payload-fields.md)
   + [Sélection de l’espace de noms](using/event/selecting-the-namespace.md)
   + [Définition de la clé d’événement](using/event/defining-the-event-key.md)
   + [Ajout d’une condition](using/event/adding-a-condition.md)
   + [Aperçu de la charge utile](using/event/previewing-the-payload.md)
   + [Autres étapes pour envoyer des événements](using/event/additional-steps-to-send-events-to-journey-orchestration.md)
+ Configuration d’une source de données {#data-source-journeys}
   + [A propos des sources de données](using/datasource/about-data-sources.md)
   + [Groupes de champs](using/datasource/field-groups.md)
   + [Source de données Adobe Experience Platform](using/datasource/adobe-experience-platform-data-source.md)
   + [Sources de données externes](using/datasource/external-data-sources.md)
+ Configuration d’une action {#action-journeys}
   + [A propos des actions](using/action/action.md)
   + [Utilisation d’Adobe Campaign](using/action/working-with-adobe-campaign.md)
   + Utilisation d’un système tiers {#action-third-party}
      + [A propos de la configuration des actions personnalisées](using/action/about-custom-action-configuration.md)
      + [Limitations des actions personnalisées](using/action/custom-action-limitations.md)
      + [Configuration de l’URL](using/action/url-configuration.md)
      + [Définition des paramètres du message](using/action/defining-the-message-parameters.md)
+ Construire un voyage {#building-journeys}
   + A propos de la création de parcours {#about-journey-building}
      + [Création d&#39;un voyage](using/building-journeys/journey.md)
      + [Utilisation du concepteur du voyage](using/building-journeys/using-the-journey-designer.md)
      + [Modification des propriétés](using/building-journeys/changing-properties.md)
      + [Versions de voyage](using/building-journeys/journey-versions.md)
      + [Arrêt d&#39;un voyage](using/building-journeys/terminating-a-journey.md)
      + [Gestion des fuseaux horaires](using/building-journeys/timezone-management.md)
   + Activities {#about-journey-building}
      + [Activités d’événements](using/building-journeys/event-activities.md)
      + Activités d’orchestration {#orchestration-activities}
         + [A propos des activités d’orchestration](using/building-journeys/about-orchestration-activities.md)
         + [Activité de condition](using/building-journeys/condition-activity.md)
         + [Activité Fin](using/building-journeys/end-activity.md)
         + [Activité d’attente](using/building-journeys/wait-activity.md)
      + Activités d&#39;action {#action-activities}
         + [A propos des activités d’action](using/building-journeys/about-action-activities.md)
         + [Utilisation des actions Adobe Campaign](using/building-journeys/using-adobe-campaign-actions.md)
         + [Utilisation d’actions personnalisées](using/building-journeys/using-custom-actions.md)
   + [Test du parcours](using/building-journeys/testing-the-journey.md)
   + [Publication du voyage](using/building-journeys/publishing-the-journey.md)
+ Utilisation de l’éditeur d’expression avancé {#building-advanced-conditions-journeys}
   + [A propos de l’éditeur d’expression avancé](using/expression/expressionadvanced.md)
   + Syntaxe {#syntax}
      + [Généralités](using/expression/generalities.md)
      + [Instruction conditionnelle](using/expression/conditional-instruction.md)
      + [Types des données](using/expression/data-types.md)
      + [Références de champ](using/expression/field-references.md)
      + [Fonctions de gestion des collections](using/expression/collection-management-functions.md)
      + [Les opérateurs](using/expression/operators.md)
   + Fonctions {#main-functions-journey}
      + [Fonctions principales](using/expression/functions.md)
      + Adobe Experience Platform {#adobe-experience-platform}
         + [getBestSendTime](using/functions/functiongetbestsendtime.md)
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
         + [currentTime &#x200B; InMillis](using/functions/functioncurrenttimeinmillis.md)
         + [inLastDays](using/functions/functioninlastdays.md)
         + [inLastHours](using/functions/functioninlasthours.md)
         + [inLastMonths](using/functions/functioninlastmonths.md)
         + [inLastYears](using/functions/functioninlastyears.md)
         + [inNextDays](using/functions/functioninnextdays.md)
         + [inNextHours](using/functions/functioninnexthours.md)
         + [inNextMonths](using/functions/functioninnextmonths.md)
         + [inNextYears](using/functions/functioninnextyears.md)
         + [maintenant](using/functions/functionnow.md)
         + [nowWithDelta](using/functions/functionnowwithdelta.md)
         + [setHours](using/functions/functionsethours.md)
         + [setDays](using/functions/functionsetdays.md)
      + Liste {#list}
         + [distinct](using/functions/functiondistinct.md)
         + [distinctAvecNull](using/functions/functiondistinctwithnull.md)
         + [in](using/functions/functionin.md)
         + [listSize](using/functions/functionlistsize.md)
         + [sérializeList](using/functions/functionserializelist.md)
         + [trier](using/functions/functionsort.md)
      + Maths {#math}
         + [aléatoire](using/functions/functionrandom.md)
         + [round](using/functions/functionround.md)
      + Chaîne {#string}
         + [concat](using/functions/functionconcat.md)
         + [contains](using/functions/functioncontain.md)
         + [containsWithIgnoreCase](using/functions/functioncontainwithignorecase.md)
         + [endWith](using/functions/functionendwith.md)
         + [endWithIgnorecase](using/functions/functionendwithignorecase.md)
         + [equelWithIgnoreCase](using/functions/functionequalignorecase.md)
         + [indexOf](using/functions/functionindexof.md)
         + [isEmpty](using/functions/functionisempty.md)
         + [isNotEmpty](using/functions/functionisnotempty.md)
         + [lastIndexOf](using/functions/functionlastindexof.md)
         + [length](using/functions/functionlength.md)
         + [lower](using/functions/functionlower.md)
         + [matchRegExp](using/functions/functionmatchregexp.md)
         + [notEqualWithIgnoreCase](using/functions/functionnotequalignorecase.md)
         + [remplacer](using/functions/functionreplace.md)
         + [replaceAll](using/functions/functionreplaceall.md)
         + [startWith](using/functions/functionstartwith.md)
         + [startWithIgnoreCase](using/functions/functionstartwithignorecase.md)
         + [previous](using/functions/functionsubstr.md)
         + [rogner](using/functions/functiontrim.md)
         + [supérieur](using/functions/functionupper.md)
         + [uuid](using/functions/functionuuid.md)
+ Création de rapports{#journey-reports}
   + [A propos des rapports de voyage](using/reporting/about-journey-reports.md)
   + [Création de rapports de voyage](using/reporting/creating-your-journey-reports.md)
   + [Mesures et dimensions](using/reporting/metrics-and-dimensions.md)
+ Cas pratiques{#use-cases-journeys}
   + Cas d&#39;utilisation simple{#use-case-simple}
      + [A propos du cas d’utilisation simple](using/usecase/about-the-simple-use-case.md)
      + [Configuration de l’événement](using/usecase/configuring-the-event.md)
      + [Configuration de la source de données](using/usecase/configuring-the-data-source.md)
      + [Construire le voyage](using/usecase/simple-uc-building-the-journey.md)
   + Cas d&#39;utilisation avancé{#use-case-advanced}
      + [A propos du cas d’utilisation avancé](using/usecase/about-the-advanced-use-case.md)
      + [Configuration des événements](using/usecase/configuring-the-events.md)
      + [Configuration des sources de données](using/usecase/configuring-the-data-sources.md)
      + [Construire le voyage](using/usecase/building-the-journey.md)
   + [Tirer parti des scores de fatigue](using/usecase/leveraging-fatigue-scores.md)

