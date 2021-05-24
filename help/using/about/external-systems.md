---
product: adobe campaign
solution: Journey Orchestration
title: Intégration avec les systèmes externes
description: Découvrez les bonnes pratiques à appliquer lors de l’intégration de systèmes externes
feature: Parcours
role: Business Practitioner
level: Beginner
exl-id: 27859689-dc61-4f7a-b942-431cdf244455
source-git-commit: a25ff95e0b74d3a0693310179670c7fe7b0de51c
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 0%

---

# Intégration aux systèmes externes {#external-systems}

Cette page présente les différentes barrières de sécurité fournies par Journey Orchestration lors de l’intégration d’un système externe, ainsi que les bonnes pratiques : comment optimiser la protection de votre système externe avec l’API de limitation, comment configurer le délai d’expiration du parcours et comment les reprises fonctionnent.

Journey Orchestration vous permet de configurer des connexions à des systèmes externes par le biais de sources de données personnalisées et d’actions personnalisées. Cela vous permet, par exemple, d’enrichir vos parcours de données provenant d’un système de réservation externe ou d’envoyer des messages à l’aide de systèmes tiers tels qu’Epsilon ou Facebook.

Lors de l’intégration d’un système externe, vous pouvez rencontrer plusieurs problèmes, le système peut être lent, peut arrêter de répondre ou peut ne pas être en mesure de gérer un volume important. Journey Orchestration propose plusieurs barrières de sécurité pour protéger votre système contre le surchargement.

Tous les systèmes externes sont différents en termes de performances. Vous devez adapter la configuration à chaque cas d’utilisation.

Lorsque Journey Orchestration exécute un appel vers une API externe, les barrières techniques sont exécutées comme suit :

1. Limitation : les règles de limitation sont appliquées ;
2. Timeout et reprise :

## Limitation

L’API de limitation intégrée offre une barrière de sécurité technique en amont qui aidera à protéger votre système externe. Au préalable, vous devez évaluer la capacité de votre API externe. Par exemple, si Journey Orchestration envoie 1 000 appels par seconde et que votre système ne peut prendre en charge que 100 appels par seconde, vous devez définir une règle de limitation afin que votre système ne se satue pas.

Les règles de limitation sont définies au niveau sanddox pour un point de terminaison spécifique (URL appelée ). Au moment de l’exécution, Journey Orchestration vérifie si une règle de limitation est définie et applique le taux défini lors des appels à ce point de terminaison. Si le nombre d’appels dépasse le taux défini, les appels restants sont ignorés.

Une règle de limitation est spécifique à un point de terminaison, mais globale à tous les parcours d’un environnement de test. Cela signifie que les emplacements d’appel sont partagés entre tous les parcours d’un environnement de test. Supposons, par exemple, que votre système externe dispose d’un plafonnement défini de 100 appels par seconde et qu’il soit appelé par une action personnalisée dans 10 parcours différents. Si un parcours reçoit 200 appels par seconde, il garde les 100 emplacements disponibles et rejette les 100 emplacements restants. Le taux maximum étant déjà dépassé, aucun emplacement n&#39;est disponible pour les 9 autres parcours. Cette granularité permet de protéger le système externe contre le surchargement et la panne.

Un appel ignoré en raison des limites de limitation est comptabilisé comme une erreur dans les rapports.

Pour savoir comment configurer des règles de limitation, consultez [cette page](../api/timezone-management.md).

## Délai d’expiration et reprises

Ensuite -> définition du délai d’expiration, et qui définir le temps maximum qu’on a lappel au sys . Pendant ce temps là, sur le blog de politique des appels. Sur fait un appel si l&#39;appel dure moinlongtemps que le timeout ca marche, si plus longtemps on ca s&#39;une timeout error, et coté reporting compabilisé comme une erreur. si l&#39;appel echoue, (planter sur 500 ou autre), réessayer. 3 reprise max., pas configurable. SI peut excéder le timeoutglobal (par exemple 2 essais, depasse le timeout) erreur de dépassement de délai. plsu de temps que nécessaire. durée du délai d&#39;expiration max. qu&#39;on a appel et aux retries est en.

