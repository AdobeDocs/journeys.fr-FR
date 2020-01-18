---
title: Activité de condition
description: En savoir plus sur les activités de condition
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
source-git-commit: 4871550d1608f4ffdee3b56d38b08f808eb2281c

---


# Activité de condition{#section_e2n_pft_dgb}

Quatre types de conditions sont disponibles :

* [Condition de source de données](#data_source_condition)
* [Condition de temps](#time_condition)
* [Division en pourcentage](#percentage_split)
* [Condition de date](#date_condition)

![](../assets/journey49.png)

## A propos de l’activité Condition {#about_condition}

Cliquez sur **[!UICONTROL Ajouter un chemin]**si vous souhaitez définir plusieurs conditions. Pour chaque condition, un nouveau chemin est ajouté dans la trame après l’activité.

![](../assets/journey47.png)

Notez que la conception des voyages a des impacts fonctionnels. Lorsque plusieurs chemins sont définis après une condition, seul le premier chemin éligible est exécuté. Cela signifie que vous pouvez modifier la définition des priorités des chemins en les plaçant au-dessus ou en dessous les uns des autres. Par exemple, si la condition du premier chemin est &quot;La personne est un VIP&quot; et la condition du second chemin est &quot;La personne est un homme&quot;. Si une personne répondant aux deux conditions (un homme qui est un VIP) franchit cette étape, le premier chemin sera choisi même s&#39;il est également éligible au second, parce que le premier chemin est &quot;au-dessus&quot;. Pour modifier cette priorité, déplacez vos activités dans un autre ordre vertical.

![](../assets/journey48.png)

Vous pouvez créer un autre chemin pour les audiences qui ne sont pas éligibles aux conditions définies en cochant **[!UICONTROL Afficher le chemin pour d’autres cas que ceux ci-dessus]**. Notez que cette option n’est pas disponible dans les conditions de division. Voir Séparation[du](#percentage_split)pourcentage.

Le mode simple vous permet d’exécuter des requêtes simples basées sur une combinaison de champs. Tous les champs disponibles s’affichent sur le côté gauche de l’écran. Faites glisser des champs dans la zone principale. Pour combiner les différents éléments, imbriquez-les les uns dans les autres afin de créer différents groupes et/ou niveaux de groupe. Vous pouvez alors sélectionner un opérateur logique afin de combiner les éléments de même niveau :

* ET : intersection de deux critères. Seuls les éléments correspondant à tous les critères sont pris en compte.
* OU : union de deux critères. Les éléments répondant à au moins l&#39;un des deux critères sont comptabilisés.

![](../assets/journey64.png)

>[!NOTE]
>
>Vous ne pouvez pas effectuer de requêtes sur des séries chronologiques (par exemple, une liste d’achats, des clics précédents sur des messages) avec l’éditeur simple. Pour ce faire, vous devez utiliser l’éditeur avancé. Voir la section [](../expression/expressionadvanced.md).

## Data Source condition {#data_source_condition}

Cela vous permet de définir une condition en fonction des champs des sources de données ou des événements précédemment positionnés dans le parcours. Pour savoir comment utiliser l’éditeur d’expression, voir [](../expression/expressionadvanced.md). A l’aide de l’éditeur d’expression avancé, vous pouvez configurer des conditions plus avancées pour manipuler des collections ou utiliser des sources de données nécessitant la transmission de paramètres. Voir la section [](../datasource/external-data-sources.md).

![](../assets/journey50.png)

## Time condition{#time_condition}

Vous pouvez ainsi effectuer différentes actions selon l’heure du jour et/ou le jour de la semaine. Par exemple, vous pouvez décider d’envoyer des messages SMS pendant la journée et des courriels la nuit pendant la semaine. Vous pouvez définir un fuseau horaire spécifique pour cette condition. Voir la section [](../building-journeys/timezone-management.md).

![](../assets/journey51.png)

## Division en pourcentage {#percentage_split}

Cette option vous permet de fractionner l’audience de manière aléatoire afin de définir une action différente pour chaque groupe. Définissez le nombre de divisions et la répartition pour chaque chemin. Le calcul du fractionnement est statistique, car le système ne peut pas anticiper le nombre de personnes qui vont suivre cette activité du voyage. Par conséquent, la marge d’erreur est très faible pour le fractionnement. Cette fonction est basée sur un mécanisme aléatoire Java (voir cette [page](https://docs.oracle.com/javase/7/docs/api/java/util/Random.html)).

>[!NOTE]
>
>Notez qu’il n’existe aucun bouton pour ajouter un chemin dans la condition de fractionnement du pourcentage. Le nombre de chemins dépend du nombre de divisions. Dans les conditions de division, vous ne pouvez pas ajouter de chemin pour d’autres cas, car cela ne peut pas se produire. Les gens iront toujours dans l&#39;un des chemins divisés.


![](../assets/journey52.png)

## Date condition {#date_condition}

Cela vous permet de définir un flux différent en fonction de la date. Par exemple, si la personne entre dans l’étape pendant la période &quot;ventes&quot;, vous lui enverrez un message spécifique. Le reste de l&#39;année, vous enverrez un autre message. Lorsque vous définissez une condition de date, vous devez spécifier un fuseau horaire. Voir la section [](../building-journeys/timezone-management.md).

![](../assets/journey53.png)
