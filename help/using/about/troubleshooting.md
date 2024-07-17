---
product: adobe campaign
title: Dépannage
description: En savoir plus sur la résolution des problèmes
feature: Journeys
role: User
level: Intermediate
exl-id: c678ba01-c868-49f2-99f3-1abe0302779e
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '1048'
ht-degree: 100%

---

# Dépannage{#concept_nlv_bcv_2fb}

Cette section décrit comment résoudre les problèmes liés aux parcours avant de les tester ou de les publier. Il est possible d&#39;effectuer les vérifications répertoriées ci-dessous lorsque le parcours est en mode test ou actif. Il est recommandé de les réaliser en mode test, puis d&#39;effectuer la publication. Voir [cette page](../building-journeys/testing-the-journey.md).

## Vérification des erreurs avant le test{#section_h3q_kqk_fhb}

Avant de tester et de publier votre parcours, vérifiez que toutes les activités sont correctement configurées. Vous ne pouvez pas effectuer de tests ou de publications si des erreurs sont détectées par le système.

Les erreurs sont représentées par un symbole d&#39;avertissement, affiché sur l&#39;activité elle-même, dans la zone de travail. Placez le curseur sur le point d&#39;exclamation pour afficher le message d&#39;erreur. Si vous cliquez sur l&#39;activité, vous devez voir la ligne contenant l&#39;erreur associée à un avertissement. Par exemple, si un champ obligatoire est vide, une erreur s&#39;affiche.

![](../assets/journey63.png)

Par exemple, dans la zone de travail, lorsque deux activités sont déconnectées, un avertissement s&#39;affiche.

![](../assets/canvas-disconnected.png)

En regard du bouton bascule **[!UICONTROL Test]** et du bouton **[!UICONTROL Publier]**, un signe d&#39;avertissement peut s&#39;afficher. Il indique les erreurs détectées par le système et empêche l&#39;activation du mode test ou la publication du parcours. La plupart du temps, les erreurs détectées par le système sont liées à des dysfonctionnements visibles relatifs aux activités. Cependant, elles sont parfois associées à d&#39;autres problèmes. Dans ce cas, vous pouvez les afficher en essayant d&#39;identifier le problème à l&#39;aide de la description de l&#39;erreur. Si vous ne parvenez pas à l&#39;identifier, vous pouvez copier les détails et les envoyer à l&#39;administrateur ou à l&#39;assistance technique. Notez que les erreurs qui bloquent le test et celles qui bloquent la publication sont similaires.

Le système détecte deux types de problèmes : les erreurs et les avertissements. Les erreurs bloquent la publication et l&#39;activation des tests. Les avertissements indiquent des problèmes potentiels qui ne bloquent pas l&#39;activation ou la publication des tests. Vous verrez une description du problème et un identifiant de journal des problèmes du type ERR_XXX_XXX. Ce format facilite l&#39;identification du problème par l&#39;assistance technique.

Le signe en regard du bouton bascule **[!UICONTROL Test]** et du bouton **[!UICONTROL Publier]** peut apparaître dans deux couleurs différentes. Il est rouge en cas d&#39;erreur, et orange pour un avertissement.

![](../assets/journey75.png)

Les erreurs et les avertissements globaux du parcours apparaissent en tête de liste. Ceux liés à des activités spécifiques sont répertoriés ensuite, par ordre d&#39;activité ou d&#39;apparition dans le parcours, de gauche à droite. Le bouton **[!UICONTROL Copier les détails]** copie les informations techniques relatives au parcours qui seront utiles à l&#39;équipe d&#39;assistance technique pour résoudre les problèmes.

Lorsqu&#39;une erreur se produit dans une action ou une condition, le parcours d&#39;un individu s&#39;arrête. La seule façon de le faire continuer est de cocher la case **[!UICONTROL Ajouter un chemin alternatif en cas de temporisation ou d’erreur]**. Consultez [cette section](../building-journeys/using-the-journey-designer.md#paths).

## Vérification de l&#39;envoi correct des événements{#section_rqz_11t_dgb}

Le point de départ d&#39;un parcours est toujours un événement. Il est possible d&#39;effectuer des tests à l&#39;aide d&#39;outils tels que Postman.

Vous pouvez ainsi vérifier si l&#39;appel d&#39;API émis via ces outils est correctement envoyé ou non. Si vous obtenez une erreur en retour, cela signifie que votre appel a rencontré un problème. Vérifiez à nouveau la payload, l&#39;en-tête (et en particulier l&#39;identifiant d&#39;organisation) et l&#39;URL de destination. Vous pouvez demander à votre administrateur l&#39;URL appropriée pour l&#39;accès.

Les événements ne sont pas directement transmis de la source à [!DNL Journey Orchestration]. En effet, [!DNL Journey Orchestration] s’appuie sur les API d’ingestion en flux continu d’Adobe Experience Platform. En cas de problèmes relatifs aux événements, vous pouvez donc consulter [cette page](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html?lang=fr) pour la résolution des problèmes concernant les API d&#39;ingestion en flux continu.

## Vérification de l&#39;entrée des visiteurs dans le parcours{#section_x4v_zzs_dgb}

Les rapports produits par [!DNL Journey Orchestration] donnent des mesures en temps réel des entrées des visiteurs dans un parcours.

Si l&#39;événement a été envoyé avec succès, mais que vous ne voyez pas d&#39;entrée dans le parcours, cela signifie qu&#39;une erreur s&#39;est produite entre l&#39;envoi de l&#39;événement et la réception de l&#39;événement dans le parcours.

En tant qu&#39;administrateur, vous devez vérifier les points suivants :

* Êtes-vous certain que le parcours où vous attendez l&#39;événement entrant est en mode test ou actif ?
* Avez-vous enregistré l&#39;événement avant de copier la payload depuis l&#39;aperçu de la payload ?
* La payload d&#39;événement contient-elle un identifiant d&#39;événement ?
* Avez-vous atteint la bonne URL ?
* Avez-vous appliqué la structure de payload des API d&#39;ingestion en flux continu en utilisant l&#39;aperçu de la structure de payload dans le volet de configuration des événements ? Voir [cette page](../event/previewing-the-payload.md).
* Avez-vous utilisé les paires clé/valeur appropriées dans l’en-tête de l’événement ?

  ```
  X-gw-ims-org-id - your ORGID
  Content-type - application/json
  ```

## Vérification de la manière dont les visiteurs naviguent dans le parcours{#section_l5y_yzs_dgb}

Les rapports produits par [!DNL Journey Orchestration] mesurent la progression des individus dans un parcours. Il est très facile d&#39;identifier où et pourquoi une personne s&#39;est arrêtée.

Les éléments à vérifier sont les suivants :

* La situation est-elle due à une condition excluant la personne concernée ? Par exemple, la condition est « genre = masculin » et la personne est une femme. Si la condition n&#39;est pas trop complexe, un utilisateur chargé de la conception de parcours peut effectuer cette vérification.
* La situation est-elle due à une source de données qui ne répond pas ? Lorsque le parcours est en test, ces informations apparaissent dans les journaux du mode test. Lorsque le parcours est actif, un administrateur peut tester les appels directs à la source de données et vérifier la réponse reçue. Il peut également dupliquer le parcours et le tester.

## Vérification de l&#39;envoi des messages{#section_qb1_yzs_dgb}

Si les individus suivent le bon chemin dans le parcours sans recevoir de messages, vous pouvez vérifier les points suivants :

* La messagerie transactionnelle a correctement pris en compte la demande d’envoi du message. Un utilisateur chargé de la conception de parcours peut accéder au message transactionnel censé être envoyé et vérifier si l’heure de la dernière exécution correspond à l’heure d’exécution de votre parcours. Il peut également vérifier les derniers appels/événements d’API reçus par la messagerie transactionnelle.
* La messagerie transactionnelle a bien envoyé le message. Dans les journaux d’envoi des messages transactionnels, vous pouvez voir le statut de chaque exécution, en vert ou en rouge, et la nature du problème. Un utilisateur chargé de la conception de parcours peut accéder à cet écran et envoyer les journaux à un administrateur pour plus d&#39;informations.

Dans le cas d&#39;un message envoyé par le biais d&#39;une action personnalisée, le seul élément vérifiable pendant le test du parcours est l&#39;apparition ou non d&#39;une erreur suite à l&#39;appel du système à l&#39;aide d&#39;une action personnalisée. Si l&#39;appel au système externe associé à l&#39;action personnalisée n&#39;entraîne pas d&#39;erreur, mais ne déclenche pas l&#39;envoi d&#39;un message, certaines vérifications doivent être effectuées du côté du système externe.
