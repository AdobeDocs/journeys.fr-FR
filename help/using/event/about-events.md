---
product: adobe campaign
title: À propos des événements
description: En savoir plus sur les événements
feature: Journeys
role: User
level: Intermediate
exl-id: 2115ab1d-1084-4429-8315-0357c8525c47
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '446'
ht-degree: 100%

---

# Principe général {#concept_gfj_fqt_52b}


>[!CAUTION]
>
>**Vous recherchez Adobe Journey Optimizer** ? Cliquez [ici](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/ajo-home){target="_blank"} pour consulter la documentation de Journey Optimizer.
>
>
>_Cette documentation se rapporte aux anciens contenus de Journey Orchestration qui ont été remplacés par Journey Optimizer. Pour toute question concernant votre accès à Journey Orchestration ou Journey Optimizer, contactez votre équipe en charge des comptes._



>[!CONTEXTUALHELP]
>id="jo_events"
>title="À propos des événements"
>abstract="Un événement est lié à une personne. Il est associé au comportement d&#39;une personne ou à quelque chose qui se passe en rapport avec une personne. C’est ce type d’élément que [!DNL Journey Orchestration] écoute dans les parcours pour orchestrer les meilleures actions qu’il convient de prendre ensuite."

Un événement est lié à une personne. Il s’agit du comportement d’une personne (par exemple, une personne a acheté un produit, a visité un magasin, est sortie d’un site web, etc.) ou d’un élément lié à une personne (par exemple, une personne a atteint 10 000 points de fidélité). C’est ce type d’élément que [!DNL Journey Orchestration] écoute dans les parcours pour orchestrer les meilleures actions qu’il convient de prendre ensuite.

Cette configuration est **obligatoire** dans la mesure où [!DNL Journey Orchestration] a été conçu pour « écouter » des événements. Elle est toujours effectuée par un **utilisateur technique**.

La configuration d’événement vous permet de définir les informations que [!DNL Journey Orchestration] recevra en tant qu’événements. Vous pouvez utiliser plusieurs événements (à différentes étapes d’un parcours) et plusieurs parcours peuvent utiliser un même événement.

Si vous modifiez un événement utilisé dans un parcours actif ou dans un état de brouillon, vous pouvez uniquement en modifier le nom ou la description, ou ajouter des champs de payload. La modification des parcours actifs ou dans un état de brouillon est strictement limitée pour éviter de les interrompre.

Vous pouvez définir deux types d’événements :

* Événements **basés sur des règles** : ce type d’événement ne génère pas d’eventID. En utilisant l’éditeur d’expression simple, vous définissez simplement une règle qui sera utilisée par le système pour identifier les événements pertinents qui déclencheront vos parcours. Cette règle peut être basée sur n’importe quel champ disponible dans le payload de l’événement, par exemple l’emplacement du profil ou le nombre d’éléments ajoutés au panier du profil.

  >[!CAUTION]
  >
  >Une règle de limitation est définie pour les événements basés sur des règles. Il limite à 5 000 le nombre d’événements qualifiés qu’un parcours peut traiter par seconde pour une organisation donnée (ORG). Il correspond à des contrats de niveau de service Journey Orchestration. Consultez cette [page](https://helpx.adobe.com/fr/legal/product-descriptions/journey-orchestration.html).

* **Événements** générés par le système : ces événements nécessitent un eventID. Ce champ eventID est généré automatiquement lors de la création de l’événement. Le système à l’origine de l’envoi de l’événement ne doit pas générer d’identifiant, mais plutôt transmettre celui indiqué dans la prévisualisation de la payload.

Journey Orchestration nécessite que les événements soient diffusés en continu ou par lots dans Adobe Experience Platform. Ces données n&#39;ont pas nécessairement besoin d&#39;accéder au profil en temps réel. Si vous souhaitez utiliser les événements pour la segmentation ou la recherche dans un parcours distinct, nous vous recommandons d&#39;activer le jeu de données pour profile.

Pour savoir comment créer un événement, consultez cette [page](../event/about-creating.md).
