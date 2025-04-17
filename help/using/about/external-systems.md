---
product: adobe campaign
solution: Journey Orchestration
title: Intégration avec des systèmes externes
description: Découvrez les bonnes pratiques à appliquer lors de l'intégration de systèmes externes
feature: Journeys
role: User
level: Beginner
exl-id: e39218bd-fa6e-443f-9843-92b7a07070fa
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '1084'
ht-degree: 100%

---

# Intégration de systèmes externes {#external-systems}


>[!CAUTION]
>
>**Vous recherchez Adobe Journey Optimizer** ? Cliquez [ici](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/ajo-home){target="_blank"} pour consulter la documentation de Journey Optimizer.
>
>
>_Cette documentation se rapporte aux anciens contenus de Journey Orchestration qui ont été remplacés par Journey Optimizer. Pour toute question concernant votre accès à Journey Orchestration ou Journey Optimizer, contactez votre équipe en charge des comptes._



Cette page présente les différents mécanismes de sécurisation fournis par Journey Orchestration lors de l’intégration d’un système externe, ainsi que les bonnes pratiques : comment optimiser la protection de votre système externe à l’aide de l’API de limitation, comment configurer le délai d’expiration du parcours et comment les reprises fonctionnent.

Journey Orchestration vous permet de configurer des connexions à des systèmes externes par le biais de sources de données et d’actions personnalisées. Vous pouvez ainsi, par exemple, enrichir vos parcours de données provenant d&#39;un système de réservation externe ou envoyer des messages à l&#39;aide d&#39;un système tiers tel qu&#39;Epsilon ou Facebook.

Lors de l&#39;intégration d&#39;un système externe, vous pouvez rencontrer plusieurs problèmes : le système peut être lent, il peut arrêter de répondre ou ne pas être en mesure de gérer un volume important. Journey Orchestration propose plusieurs mécanismes de sécurisation pour protéger votre système contre le surchargement.

Tous les systèmes externes sont différents en termes de performances. Vous devez adapter la configuration à vos cas d&#39;utilisation.

Lorsque Journey Orchestration exécute un appel à une API externe, les mécanisme de sécurisation sont exécutés comme suit :

1. Les règles de limitation sont appliquées : si le taux maximum est atteint, les appels restants sont ignorés.

2. Temporisation et reprise : si la règle de limitation est remplie, Journey Orchestration tente d’effectuer l’appel jusqu’à ce que la fin de la durée de temporisation soit atteinte.

## Limitation{#capping}

L&#39;API de limitation native offre un mécanisme de sécurisation technique en amont qui permet de protéger votre système externe.

Pour les sources de données externes, le nombre maximal d’appels par seconde est défini sur 15. Si le nombre d’appels dépasse 15 par seconde, les appels restants sont ignorés. Vous pouvez augmenter cette limite pour les sources de données externes privées. Contactez Adobe pour inclure le point d’entrée dans la liste autorisée. Cela n’est pas possible pour les sources de données externes publiques.

Pour les actions personnalisées, vous devez évaluer la capacité de votre API externe. Par exemple, si Journey Optimizer envoie 1 000 appels par seconde et que votre système ne peut prendre en charge que 100 appels par seconde, vous devez définir une règle de limitation afin que votre système ne sature pas.

Les règles de limitation sont définies au niveau de l’environnement Sandbox pour un point d’entrée spécifique (l’URL appelée). Au moment de l’exécution, Journey Orchestration vérifie si une règle de limitation est définie et applique le taux défini lors des appels à ce point d’entrée. Si le nombre d&#39;appels dépasse le taux défini, les appels restants sont ignorés et comptabilisés comme des erreurs dans les rapports.

Une règle de limitation est spécifique à un point d’entrée, mais commune à tous les parcours d’un environnement Sandbox. Cela signifie que les emplacements de limitation sont partagés entre tous les parcours d’un sandbox.

Supposons, par exemple, que vous ayez défini une règle de limitation de 100 appels par seconde pour votre système externe. Votre système est appelé par une action personnalisée dans 10 parcours différents. Si un parcours reçoit 200 appels par seconde, il utilise les 100 emplacements disponibles et rejette les 100 emplacements restants. Comme le taux maximum a été dépassé, il ne restera plus aucun emplacement pour les 9 autres parcours. Cette granularité permet de protéger le système externe contre la surcharge et la panne.

Pour en savoir plus sur l&#39;API de limitation et sur la configuration des règles de limitation, consultez [cette page](../api/capping.md).

## Temporisation et reprises{#timeout}

Si la règle de limitation est remplie, la règle de temporisation est appliquée.

Dans chaque parcours, vous pouvez définir un délai de temporisation. Vous pouvez ainsi définir une durée maximale lors de l&#39;appel d&#39;un système externe. Le délai de temporisation est configuré dans les propriétés d&#39;un parcours. Voir [cette page](../building-journeys/changing-properties.md#timeout_and_error).

Cette temporisation est commune à tous les appels externes (appels API externes dans les actions personnalisées et les sources de données personnalisées). Par défaut, elle est définie sur 5 secondes.

Pendant la durée de temporisation définie, Journey Orchestration tente d’appeler le système externe. Après le premier appel, trois reprises au maximum peuvent être effectuées jusqu&#39;à la fin du délai de temporisation. Le nombre de reprises ne peut pas être modifié.

Chaque nouvelle reprise utilise un emplacement. Si vous avez une limitation de 100 appels par seconde et que chacun de vos appels nécessite deux reprises, le taux chute à 30 appels par seconde (chaque appel utilise 3 emplacements : le premier appel et deux reprises).

La valeur du délai de temporisation dépend du cas d&#39;utilisation. Si vous souhaitez envoyer votre message rapidement, par exemple lorsque le client entre dans le magasin, le délai de temporisation ne doit pas être long. En outre, plus le délai de temporisation est long, plus les éléments sont placés en file d&#39;attente. Cela peut avoir un impact considérable sur les performances. Si Journey Orchestration effectue 1 000 appels par seconde, le fait de conserver 5 ou 15 secondes de données peut rapidement submerger le système.

Prenons un exemple pour une temporisation de 5 secondes.

* Le premier appel dure moins de 5 secondes : l&#39;appel a réussi, aucune nouvelle reprise n&#39;a été effectuée.
* Le premier appel dure plus de 5 secondes : l&#39;appel est annulé et il n&#39;y a aucune reprise. Il est compté comme une erreur de temporisation dans les rapports.
* Le premier appel échoue après 2 secondes (le système externe renvoie une erreur) : 3 secondes restent pour les reprises, si des emplacements de limitation sont disponibles.
   * Si l&#39;une des trois reprises réussit avant la fin des 5 secondes, l&#39;appel est effectué et aucune erreur ne se produit.
   * Si la fin du délai de temporisation est atteinte lors des nouvelles reprises, l&#39;appel est annulé et compté comme une erreur de temporisation dans les rapports.

## Questions fréquentes{#faq}

**Comment configurer une règle de limitation ? Existe-t-il une règle de limitation par défaut ?**

Par défaut, il n&#39;existe aucune règle de limitation. Les règles de limitation sont définies au niveau de l’environnement Sandbox pour un point d’entrée spécifique (l’URL appelée), à l’aide de l’API de limitation. Consultez [cette section](../about/external-systems.md#capping) et [cette page](../api/capping.md).

**Combien de reprises sont effectuées ? Puis-je modifier le nombre de reprises ou définir une période d&#39;attente minimale entre deux reprises ?**

Pour un appel donné, trois reprises au maximum peuvent être effectuées jusqu&#39;à la fin du délai de temporisation. Le nombre de reprises et la durée entre chaque reprise ne peuvent pas être modifiés. Reportez-vous à [cette section](../about/external-systems.md#timeout).

**Où puis-je configurer la temporisation ? Existe-t-il une valeur maximale ?**

Dans chaque parcours, vous pouvez définir un délai de temporisation. Le délai de temporisation est configuré dans les propriétés d&#39;un parcours. Le délai de temporisation doit être compris entre 1 et 30 secondes. Consultez [cette section](../about/external-systems.md#timeout) et [cette page](../building-journeys/changing-properties.md#timeout_and_error).
