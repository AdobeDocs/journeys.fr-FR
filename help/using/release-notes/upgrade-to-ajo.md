---
title: Mise à niveau vers Adobe Journey Optimizer
description: Découvrez comment mettre à niveau vers Adobe Journey Optimizer
hide: true
hidefromtoc: true
source-git-commit: e7d1b6401f03603a56d963672da1b402d0fe5e80
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 3%

---


# Mise à niveau de votre environnement de Journey Orchestration vers Adobe Journey Optimizer{#ugrade-ajo}

## Qu’est-ce que Adobe Journey Optimizer ?

Adobe Journey Optimizer est une application agile et évolutive qui s’appuie sur Adobe Experience Platform pour orchestrer et diffuser des parcours client personnalisés, connectés et opportuns sur n’importe quelle application, périphérique, écran ou canal. &#x200B;

## Présentation de Journey Orchestration

Journey Orchestration est un service basé sur Adobe Experience Platform qui vous permet de personnaliser les parcours de chaque client en fonction de son comportement et de ses préférences. Journey Orchestration est le précurseur de l’application à Journey Optimizer.

## Pourquoi dois-je migrer vers Adobe Journey Optimizer ?

**Accès à une interface rationalisée** grâce aux fonctionnalités d’Experience Platform, vous pouvez accéder rapidement aux parcours, aux jeux de données, aux profils, aux alertes, etc. Plus besoin de faire d’aller-retour entre Adobe Experience Platform et Journey Orchestration pour accéder aux schémas ou aux jeux de données, tout est directement disponible depuis Adobe Journey Optimizer. Pour plus d’informations, consultez cette [page](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/user-interface.html).

<table>
<tr>
<th>Avant</th>
<th>Après</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-1.png"><p>Accès à la section Parcours, segments et administration (sources de données, événements et actions) dans Journey Orchestration. Les segments et les jeux de données sont accessibles dans Adobe Experience Platform. </p></td>
<td><img src="../assets/migration-ajo-2.png"><p>Accès aux Parcours, aux segments, à l’administration, aux segments et aux jeux de données, <strong>tous dans Adobe Journey Optimizer</strong>. <strong>Fonctionnalités Adobe Experience Platform supplémentaires</strong> sont également accessibles ici.</p></td>
</tr>
</table>

**Nouvelle interface de création de rapports** et accès aux nouvelles fonctionnalités de reporting :

<table>
<tr>
<th>Avant</th>
<th>Après</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-5.png"></td>
<td><img src="../assets/migration-ajo-6.png"><p><strong>Vue globale</strong> vous permet de mesurer l’impact de vos parcours et diffusions sur une période sélectionnée. Pour d’autres mesures en temps réel, vous pouvez accéder à la variable <strong>Vue en direct</strong>. Pour chaque canal de diffusion utilisé dans vos parcours (Email, SMS, Push), un <strong>section dédiée</strong> est disponible dans le rapport pour afficher les mesures. Cela s’applique uniquement si vous utilisez des <strong>Fonctionnalités de messagerie Adobe Journey Optimizer</strong>. Contactez l’équipe de votre compte pour plus d’informations.</p></td>
</tr>
</table>

Toute évolution visant à améliorer l’expérience de création de rapports ou à l’enrichir à la suite de nouvelles versions de fonctionnalités n’est disponible que dans la nouvelle interface de création de rapports. Commencez à l’utiliser pour obtenir une expérience Adobe Journey Optimizer plus complète.

Profitez des autres **Fonctionnalités Adobe Journey Optimizer** et les nouvelles qui apparaissent, telles que Contrôle d’accès au niveau du champ et Contrôle d’accès au niveau de l’objet. Contactez votre équipe de compte pour obtenir plus d’informations.

## Comment mettre à niveau mon environnement de Journey Orchestration ?

1. Contactez l’équipe de votre compte pour mettre à jour gratuitement votre contrat avec Adobe.

1. Attendez que notre équipe d’ingénierie termine le changement.

1. Mettez à jour vos autorisations à l’aide des profils de produit Journey Optimizer. Voir cette [page](https://experienceleague.adobe.com/docs/journey-optimizer/using/administration/ootb-product-profiles.html?lang=fr).

1. Vous avez maintenant accès à Adobe Journey Optimizer !

## Questions fréquentes

### Dois-je prévoir quoi que ce soit pour passer de Journey Orchestration à Adobe Journey Optimizer ?

Non, il n&#39;y a pas de migration, pas de travail nécessaire de votre part, pas de temps d&#39;arrêt et pas d&#39;investissement supplémentaire. Vous n&#39;avez qu&#39;à mettre à jour votre accord avec Adobe et nous faisons le reste. Veuillez contacter votre gestionnaire de compte pour obtenir des instructions sur la manière d’initier ce processus.

### Est-ce que je vais perdre quelque chose après le changement ?

Non, vous conserverez tous vos objets Journey Orchestration et Adobe Experience Platform existants : schémas, jeux de données, parcours, événements, sources de données, actions. Rien ne sera perdu, tous les parcours vivants continueront à travailler sans interruption.

<table>
<tr>
<th>Avant</th>
<th>Après</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-7.png"></td>
<td><img src="../assets/migration-ajo-8.png"></td>
</tr>
</table>

### Je vois toujours le Journey Orchestration dans le sélecteur d’applications, est-ce normal ?

![](../assets/migration-ajo-9.png)

Oui, c&#39;est normal. Vous conserverez l’accès à Journey Orchestration pendant un mois à compter de la mise à niveau. Vous aurez ainsi suffisamment de temps pour mettre à jour toutes les autorisations de vos utilisateurs et vous familiariser avec Adobe Journey Optimizer. Au bout d’un mois, l’accès est supprimé.

### Que se passe-t-il si j’utilise Journey Orchestration avec Adobe Campaign Standard aujourd’hui ?

En passant à Adobe Journey Optimizer, vous pourrez toujours utiliser l’intégration entre Parcours et Adobe Campaign Standard en concevant votre parcours client dans Adobe Journey Optimizer et en laissant Adobe Campaign Standard envoyer la diffusion.

Cependant, en raison du fonctionnement de la pile de rapports Adobe Journey Optimizer, la création de rapports ne combinera pas les données de Parcours et de Campaign Standard. Les informations de parcours seront disponibles dans les rapports Adobe Journey Optimizer et les informations de diffusion dans Adobe Campaign Standard. Une configuration de l’Experience Platform peut être effectuée pour ramener les données Adobe Campaign Standard dans Adobe Experience Platform, afin qu’elles soient disponibles pour le Customer Journey Analytics ([en savoir plus](https://business.adobe.com/products/experience-platform/customer-journey-analytics.html)) ou d’autres outils de reporting tiers tels que Tableau ou PowerBI.

Les rapports Adobe Journey Optimizer fonctionnent mieux lorsque vous utilisez Adobe Journey Optimizer pour  des fonctionnalités de messagerie prêtes à l’emploi (disponibles dans les offres Adobe Journey Optimizer dédiées). Pour plus d&#39;informations sur la création de messages dans le canevas de parcours, reportez-vous à cette section [page](https://experienceleague.adobe.com/docs/journey-optimizer/using/messages/messages-in-journeys.html).

Contactez l’équipe de votre compte pour plus d’informations.