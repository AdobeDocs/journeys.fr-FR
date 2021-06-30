---
product: adobe campaign
solution: Journey Orchestration
title: Intégration avec des systèmes externes
description: Découvrez les bonnes pratiques à appliquer lors de l’intégration de systèmes externes
feature: Parcours
role: Business Practitioner
level: Beginner
exl-id: 27859689-dc61-4f7a-b942-431cdf244455
source-git-commit: 5346c3a25900b1e167ea5b199e1873adab39d07d
workflow-type: tm+mt
source-wordcount: '1011'
ht-degree: 90%

---

# Intégration avec des systèmes externes {#external-systems}

Cette page présente les différentes barrières de sécurité fournies par Journey Orchestration lors de l’intégration d’un système externe, ainsi que les bonnes pratiques : comment optimiser la protection de votre système externe à l’aide de l’API de limitation, comment configurer le délai d’expiration du parcours et comment les reprises fonctionnent.

Journey Orchestration vous permet de configurer des connexions à des systèmes externes par le biais de sources de données et d’actions personnalisées. Vous pouvez ainsi, par exemple, enrichir vos parcours de données provenant d’un système de réservation externe ou envoyer des messages à l’aide d’un système tiers tel qu’Epsilon ou Facebook.

Lors de l’intégration d’un système externe, vous pouvez rencontrer plusieurs problèmes, le système peut être lent, il peut arrêter de répondre ou ne pas être en mesure de gérer un volume important. Journey Orchestration propose plusieurs barrières de sécurité pour protéger votre système contre le surchargement.

Tous les systèmes externes sont différents en termes de performances. Vous devez adapter la configuration à vos cas d’utilisation.

Lorsque Journey Orchestration exécute un appel à une API externe, les barrières techniques sont exécutées comme suit :

1. Les règles de limitation sont appliquées : si le taux maximum est atteint, les appels restants sont ignorés.

2. Temporisation et reprise : si la règle de limitation est remplie, Journey Orchestration tente d’effectuer l’appel jusqu’à ce que la fin de la durée de temporisation soit atteinte.

## Limitation{#capping}

L’API de limitation intégrée offre une barrière de sécurité technique en amont qui permet de protéger votre système externe.

Pour les sources de données externes, le nombre maximal d’appels par seconde est défini sur 15. Si le nombre d’appels dépasse 15 par seconde, les appels restants sont ignorés. Vous pouvez augmenter cette limite pour les sources de données externes privées. Contactez l’Adobe pour placer sur la liste autorisée le point de terminaison . Cela n’est pas possible pour les sources de données externes publiques.

Pour les actions personnalisées, vous devez évaluer la capacité de votre API externe. Par exemple, si Journey Optimizer envoie 1 000 appels par seconde et que votre système ne peut prendre en charge que 100 appels par seconde, vous devez définir une règle de limitation afin que votre système ne se satue pas.

Les règles de limitation sont définies au niveau de l’environnement de sandbox pour un point d’entrée spécifique (l’URL appelée). Au moment de l’exécution, Journey Orchestration vérifie si une règle de limitation est définie et applique le taux défini lors des appels à ce point d’entrée. Si le nombre d’appels dépasse le taux défini, les appels restants sont ignorés et comptabilisés comme des erreurs dans les rapports.

Une règle de limitation est spécifique à un point d’entrée, mais globale à tous les parcours d’un environnement de sandbox. Cela signifie que les emplacements de limitation sont partagés entre tous les parcours d’un environnement de sandbox.

Supposons, par exemple, que vous ayez défini une règle de limitation de 100 appels par seconde pour votre système externe. Votre système est appelé par une action personnalisée dans 10 parcours différents. Si un parcours reçoit 200 appels par seconde, il utilise les 100 emplacements disponibles et rejette les 100 emplacements restants. Comme le taux maximum a été dépassé, il ne restera plus aucun emplacement pour les 9 autres parcours. Cette granularité permet de protéger le système externe contre le surchargement et la panne.

Pour en savoir plus sur l’API de limitation et sur la configuration des règles de limitation, consultez [cette page](../api/capping.md).

## Temporisation et reprises{#timeout}

Si la règle de limitation est remplie, la règle de temporisation est appliquée.

Dans chaque parcours, vous pouvez définir une durée de temporisation. Vous pouvez ainsi définir une durée maximale lors de l’appel d’un système externe. La durée de temporisation est configurée dans les propriétés d’un parcours. Voir [cette page](../building-journeys/changing-properties.md#timeout_and_error).

Cette temporisation est globale pour tous les appels externes (appels d’API externes dans les actions et les sources de données personnalisées). Par défaut, elle est définie sur 5 secondes.

Pendant la durée de temporisation définie, Journey Orchestration tente d’appeler le système externe. Après le premier appel, trois reprises au maximum peuvent être effectuées jusqu’à la fin de la durée de temporisation. Le nombre de reprises ne peut pas être modifié.

Chaque reprise utilise un emplacement. Si vous avez une limitation de 100 appels par seconde et que chacun de vos appels nécessite deux reprises, le taux chute à 30 appels par seconde (chaque appel utilise 3 emplacements : le premier appel et deux reprises).

La valeur de la durée de temporisation dépend du cas d’utilisation. Si vous voulez envoyer votre message rapidement, par exemple lorsque le client entre dans le magasin, vous ne souhaiterez pas configurer une durée de temporisation longue. En outre, plus la temporisation est longue, plus les éléments sont placés en file d’attente. Cela peut avoir un impact considérable sur les performances. Si Journey Orchestration effectue 1 000 appels par seconde, le fait de conserver 5 ou 15 secondes de données peut rapidement submerger le système.

Prenons un exemple pour une temporisation de 5 secondes.

* Le premier appel dure moins de 5 secondes : l’appel a réussi, aucune reprise n’a été effectuée.
* Le premier appel dure plus de 5 secondes : l’appel est annulé et il n’y a aucune reprise. Ceci est comptabilisé comme une erreur de temporisation dans les rapports.
* Le premier appel échoue après 2 secondes (le système externe renvoie une erreur) : 3 secondes restent pour les reprises, si des emplacements de limitation sont disponibles.
   * Si l’une des trois reprises réussit avant la fin des 5 secondes, l’appel est effectué et aucune erreur ne se produit.
   * Si la fin de la durée de temporisation est atteinte lors des reprises, l’appel est annulé et comptabilisé comme une erreur de temporisation dans les rapports.

## Forum aux questions{#faq}

**Comment configurer une règle de limitation ? Existe-t-il une règle de limitation par défaut ?**

Par défaut, il n’existe aucune règle de limitation. Les règles de limitation sont définies au niveau de l’environnement de sandbox pour un point d’entrée spécifique (l’URL appelée), à l’aide de l’API de limitation. Consultez [cette section](../about/external-systems.md#capping) et [cette page](../api/capping.md).

**Combien de reprises sont effectuées ? Puis-je modifier le nombre de reprises ou définir une période d’attente minimale entre deux reprises ?**

Pour un appel donné, trois reprises au maximum peuvent être effectuées après le premier appel, jusqu’à la fin de la durée de temporisation. Le nombre de reprises et la durée entre chaque reprise ne peuvent pas être modifiés. Consultez [cette section](../about/external-systems.md#timeout).

**Où puis-je configurer la temporisation ? Existe-t-il une valeur maximale ?**

Dans chaque parcours, vous pouvez définir une durée de temporisation. La durée de temporisation est configurée dans les propriétés d’un parcours. La durée de temporisation doit être comprise entre 1 seconde et 30 secondes. Consultez [cette section](../about/external-systems.md#timeout) et [cette page](../building-journeys/changing-properties.md#timeout_and_error).