---
product: adobe campaign
solution: Journey Orchestration
title: Intégration avec les systèmes externes
description: Découvrez les bonnes pratiques à appliquer lors de l’intégration de systèmes externes
feature: Parcours
role: Business Practitioner
level: Beginner
exl-id: 27859689-dc61-4f7a-b942-431cdf244455
source-git-commit: 5d2e82c10dd22b5b4bac15a78a2f6f592aedd371
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 1%

---

# Intégration aux systèmes externes {#external-systems}

Cette page présente les différentes barrières de sécurité fournies par Journey Orchestration lors de l’intégration d’un système externe, ainsi que les bonnes pratiques : comment optimiser la protection de votre système externe à l’aide de l’API de limitation, comment configurer le délai d’expiration du parcours et comment les reprises fonctionnent.

Journey Orchestration vous permet de configurer des connexions à des systèmes externes par le biais de sources de données personnalisées et d’actions personnalisées. Cela vous permet, par exemple, d’enrichir vos parcours de données provenant d’un système de réservation externe ou d’envoyer des messages à l’aide d’un système tiers tel qu’Epsilon ou Facebook.

Lors de l’intégration d’un système externe, vous pouvez rencontrer plusieurs problèmes, le système peut être lent, peut arrêter de répondre ou peut ne pas être en mesure de gérer un volume important. Journey Orchestration propose plusieurs barrières de sécurité pour protéger votre système contre le surchargement.

Tous les systèmes externes sont différents en termes de performances. Vous devez adapter la configuration à vos cas d’utilisation.

Lorsque Journey Orchestration exécute un appel vers une API externe, les barrières techniques sont exécutées comme suit :

1. Les règles de limitation sont appliquées : si le taux maximum est atteint, les appels restants sont ignorés.

2. Timeout et reprise : si la règle de limitation est remplie, Journey Orchestration tente d’effectuer l’appel jusqu’à ce que la fin du délai d’expiration soit atteinte.

## Limitation{#capping}

L’API de limitation intégrée offre une barrière de sécurité technique en amont qui permet de protéger votre système externe. Au préalable, vous devez évaluer la capacité de votre API externe. Par exemple, si Journey Orchestration envoie 1 000 appels par seconde et que votre système ne peut prendre en charge que 100 appels par seconde, vous devez définir une règle de limitation afin que votre système ne se satue pas.

Les règles de limitation sont définies au niveau de l’environnement de test pour un point de terminaison spécifique (l’URL appelée). Au moment de l’exécution, Journey Orchestration vérifie si une règle de limitation est définie et applique le taux défini lors des appels à ce point de terminaison. Si le nombre d’appels dépasse le taux défini, les appels restants sont ignorés et comptabilisés comme des erreurs dans les rapports.

Une règle de limitation est spécifique à un point de terminaison, mais globale à tous les parcours d’un environnement de test. Cela signifie que les emplacements de limitation sont partagés entre tous les parcours d’un environnement de test.

Supposons, par exemple, que vous ayez défini une règle de limitation de 100 appels par seconde pour votre système externe. Votre système est appelé par une action personnalisée dans 10 parcours différents. Si un parcours reçoit 200 appels par seconde, il utilise les 100 emplacements disponibles et rejette les 100 emplacements restants. Comme le taux maximum a été dépassé, il ne restera plus aucun créneau pour les 9 autres parcours. Cette granularité permet de protéger le système externe contre le surchargement et la panne.

Pour en savoir plus sur l’API de limitation et sur la configuration des règles de limitation, consultez [cette page](../api/capping.md).

## Délai d’expiration et reprises{#timeout}

Si la règle de limitation est remplie, la règle de délai d’expiration est appliquée.

Dans chaque parcours, vous pouvez définir une durée d’expiration. Vous pouvez ainsi définir une durée maximale lors de l’appel d’un système externe. La durée d’expiration est configurée dans les propriétés d’un parcours. Voir [cette page](../building-journeys/changing-properties.md#timeout_and_error).

Ce délai d’expiration est global pour tous les appels externes (appels API externes dans les actions personnalisées et les sources de données personnalisées). Par défaut, elle est définie sur 5 secondes.

Pendant le délai d’expiration défini, Journey Orchestration tente d’appeler le système externe. Après le premier appel, trois reprises au maximum peuvent être effectuées jusqu’à la fin du délai d’expiration. Le nombre de reprises ne peut pas être modifié.

Chaque nouvelle tentative utilise un emplacement. Si vous plafonnez à 100 appels par seconde et que chacun de vos appels nécessite deux reprises, le taux chute à 30 appels par seconde (chaque appel utilise 3 emplacements : le premier appel et deux reprises).

La valeur du délai d’expiration dépend du cas d’utilisation. Si vous souhaitez envoyer votre message rapidement, par exemple lorsque le client entre dans le magasin, vous ne souhaitez pas configurer de délai d’expiration long. En outre, plus le délai d’expiration est long, plus les éléments sont placés en file d’attente. Cela peut avoir un impact considérable sur les performances. Si Journey Orchestration effectue 1 000 appels par seconde, le fait de conserver 5 ou 15 secondes de données peut rapidement submerger le système.

Prenons un exemple pour un délai d’attente de 5 secondes.

* Le premier appel dure moins de 5 secondes : l’appel a réussi, aucune nouvelle tentative n’a été effectuée.
* Le premier appel dure plus de 5 secondes : l’appel est annulé et il n’y a aucune reprise. Il est compté comme une erreur de dépassement de délai dans les rapports.
* Le premier appel échoue après 2 secondes (le système externe renvoie une erreur) : 3 secondes restent pour les reprises, si des plages de limitation sont disponibles.
   * Si l’une des trois reprises réussit avant la fin des 5 secondes, l’appel est effectué et aucune erreur n’est survenue.
   * Si la fin du délai d’expiration est atteinte lors des nouvelles tentatives, l’appel est annulé et compté comme une erreur de délai d’expiration dans les rapports.

## Forum aux questions{#faq}

**Comment configurer une règle de limitation ? Existe-t-il une règle de limitation par défaut ?**

Par défaut, il n’existe aucune règle de limitation. Les règles de limitation sont définies au niveau de l’environnement de test pour un point de terminaison spécifique (l’URL appelée), à l’aide de l’API de limitation. Consultez [cette section](../about/external-systems.md#capping) et [cette page](../api/capping.md).

**Combien de reprises sont effectuées ? Puis-je modifier le nombre de reprises ou définir une période d’attente minimale entre deux reprises ?**

Pour un appel donné, trois reprises au maximum peuvent être effectuées après le premier appel, jusqu’à la fin du délai d’expiration. Le nombre de reprises et la durée entre chaque reprise ne peuvent pas être modifiés. Consultez [cette section](../about/external-systems.md#timeout).

**Où puis-je configurer le délai d’expiration ? Existe-t-il une valeur maximale ?**

Dans chaque parcours, vous pouvez définir une durée d’expiration. La durée d’expiration est configurée dans les propriétés d’un parcours. Le délai d’expiration doit être compris entre 1 seconde et 30 secondes. Consultez [cette section](../about/external-systems.md#timeout) et [cette page](../building-journeys/changing-properties.md#timeout_and_error).