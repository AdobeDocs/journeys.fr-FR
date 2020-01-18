---
title: Résolution des problèmes
description: En savoir plus sur le dépannage
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# Résolution des problèmes{#concept_nlv_bcv_2fb}

Dans cette section, vous trouverez comment dépanner les voyages avant de les tester ou de les publier. Toutes les vérifications énumérées ci-dessous peuvent être effectuées lorsque le voyage est en mode test ou lorsque le voyage est en cours. La recommandation consiste à effectuer toutes les vérifications ci-dessous en mode test, puis à procéder à la publication. Voir la section [](../building-journeys/testing-the-journey.md).

## Vérification des erreurs avant le test{#section_h3q_kqk_fhb}

Avant de tester et de publier votre parcours, vérifiez que toutes les activités sont correctement configurées. Vous ne pouvez pas effectuer de tests ou de publications si des erreurs sont toujours détectées par le système.

Les erreurs s’affichent avec un symbole d’avertissement affiché sur les activités elles-mêmes sur la trame. Placez votre curseur sur le point d’exclamation pour afficher le message d’erreur. Si vous cliquez sur l’activité, vous devriez voir la ligne en erreur avec un avertissement. Par exemple, si un champ obligatoire est vide, une erreur s’affiche.

![](../assets/journey63.png)

En regard de la bascule **[!UICONTROL Test]**et du bouton**[!UICONTROL  Publier]** , un signe d’avertissement s’affiche. Ce signe d&#39;avertissement affiche les erreurs détectées par le système et empêche l&#39;activation du mode de test ou la publication du voyage. La plupart du temps, les erreurs détectées par le système sont liées à des erreurs visibles sur les activités, mais elles sont parfois liées à d’autres problèmes. Dans ce cas, vous pouvez les afficher, essayer d’identifier le problème à l’aide de la description de l’erreur. Si vous ne parvenez pas à identifier le problème, vous pouvez copier les détails et les envoyer à l’administrateur ou à l’assistance technique. Notez que les erreurs qui bloquent le test et celles qui bloquent la publication sont similaires.

Le système détecte deux types de problèmes : erreurs et avertissements. Les erreurs bloquent la publication et l’activation des tests. Les avertissements indiquent les problèmes potentiels qui ne bloquent pas l’activation ou la publication des tests. Vous verrez une description du problème et un ID de journal des publications du type ERR_XXX_XXX. Cela aidera le support technique à identifier le problème.

Deux couleurs différentes peuvent être affichées sur le panneau en regard de la bascule **[!UICONTROL Test]**et du bouton**[!UICONTROL  Publier]** . Le signe est affiché en rouge en cas d’erreur. Il s’affiche en orange en cas d’avertissement.

![](../assets/journey75.png)

Les erreurs et les avertissements globaux pour le voyage apparaissent en premier dans la liste. Les erreurs et les avertissements liés à des activités spécifiques sont répertoriés après, par ordre d’activité ou par apparence dans le parcours de gauche à droite. Le bouton **[!UICONTROL Copier les détails]**copie les informations techniques sur le parcours que l&#39;équipe d&#39;assistance peut utiliser pour résoudre les problèmes.

## Vérification de l’envoi correct des événements{#section_rqz_11t_dgb}

Le point de départ d&#39;un voyage est toujours un événement. Vous pouvez effectuer des tests à l’aide d’outils tels que Postman.

Vous pouvez vérifier si l’appel d’API que vous envoyez via ces outils est envoyé correctement ou non. Si vous recevez une erreur, cela signifie que votre appel a un problème. Vérifiez à nouveau la charge utile, l’en-tête (et en particulier l’ID d’organisation) et l’URL de destination. Vous pouvez demander à votre administrateur quelle est l’URL appropriée pour l’accès.

Les événements ne sont pas directement transmis de la source à l’orchestration du voyage. En effet, Journey Orchestration repose sur les API d’assimilation de flux continu de la plateforme d’expérience. Par conséquent, en cas de problèmes liés aux événements, vous pouvez vous référer à cette [page](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingestion_FAQ.md) pour le dépannage des API d’assimilation en flux continu.

## Vérifier si les gens entrent dans le voyage{#section_x4v_zzs_dgb}

Les reportages de l&#39;Orchestre de Journey mesurent les entrées des gens dans un voyage en temps réel.

Si vous envoyez l&#39;événement avec succès mais que vous ne voyez pas d&#39;entrée dans le voyage, cela signifie que quelque chose ne va pas entre l&#39;envoi de l&#39;événement et la réception de l&#39;événement dans le voyage.

Voici quelques éléments que l’administrateur doit vérifier :

* Êtes-vous sûr du voyage où vous vous attendez à ce que l&#39;événement entrant soit en mode test ou en direct ?
* Avez-vous enregistré votre événement avant de copier la charge utile depuis l’aperçu de la charge utile ?
* Votre charge d’événement contient-elle un ID d’événement ?
* As-tu atteint la bonne URL ?
* Avez-vous suivi la structure de la charge utile des API d&#39;importation en flux continu à l&#39;aide de l&#39;aperçu de la structure de la charge utile dans le volet de configuration des événements ? Voir la section [](../event/previewing-the-payload.md).
* Avez-vous utilisé les paires clé/valeur appropriées dans l’en-tête de votre événement ?

   ```
   X-gw-ims-org-id - your ORGID
   Content-type - application/json
   ```

## Vérification de la manière dont les gens naviguent dans le parcours{#section_l5y_yzs_dgb}

Les rapports d&#39;orchestration du voyage mesurent le progrès des individus dans un voyage. C&#39;est facile d&#39;identifier où et pourquoi une personne a été arrêtée.

Voici quelques éléments à vérifier :

* Est-ce dû à une condition excluant la personne? Par exemple, la condition est &quot;sexe = homme&quot; et la personne est une femme. Cette vérification peut être effectuée par un utilisateur de l’entreprise si la condition n’est pas trop complexe.
* Est-ce dû à un appel à une source de données qui ne répond pas ? Lorsque le voyage est en test, ces informations peuvent être affichées dans les journaux du mode test. Lorsque le voyage est en cours, un administrateur peut tester les appels directs à la source de données et vérifier la réponse reçue. Un administrateur peut également dupliquer le voyage et le tester.

## Vérification de l’envoi des messages{#section_qb1_yzs_dgb}

Si les personnes suivent le bon chemin dans le voyage sans recevoir de messages, vous pouvez vérifier si :

* La messagerie transactionnelle a correctement pris en compte la demande d&#39;envoi du message. Un utilisateur professionnel peut accéder au message transactionnel supposé être envoyé et vérifier si l’heure de la dernière exécution correspond à l’heure d’exécution de votre voyage. Il peut également vérifier les derniers appels/événements API reçus par les messages transactionnels.
* La messagerie transactionnelle a bien envoyé le message. Dans les journaux d’envoi du message transactionnel, vous pouvez voir l’état de chaque exécution. Vous pouvez voir si c&#39;est vert, rouge et quel était le problème. Un utilisateur d’entreprise peut accéder à cet écran et envoyer les journaux à un administrateur pour plus d’informations.

Dans le cas d’un message envoyé par le biais d’une action personnalisée, la seule chose qui peut être vérifiée pendant le test de voyage est le fait que l’appel du système de l’action personnalisée entraîne ou non une erreur. Si l’appel au système externe associé à l’action personnalisée n’entraîne pas d’erreur mais ne conduit pas à l’envoi d’un message, certaines enquêtes doivent être effectuées du côté du système externe.

