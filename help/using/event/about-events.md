---
product: adobe campaign
solution: Journey Orchestration
title: À propos des événements
description: En savoir plus sur les événements
translation-type: tm+mt
source-git-commit: 3dd7cd4dc4e4398b029dd1becd11c8dd7e7c3542
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 100%

---


# Principe général {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="À propos des événements"
>abstract="Un événement est associé à une personne. Il décrit son comportement (par exemple, cette personne a acheté un produit, a visité un magasin, a quitté un site web, etc.) ou un événement qui s’est produit en rapport avec cette personne (par exemple, elle a accumulé 10 000 points de fidélité). C’est ce type d’élément que [!DNL Journey Orchestration] écoute dans les parcours pour orchestrer les meilleures actions qu’il convient de prendre ensuite."

Un événement est associé à une personne. Il décrit son comportement (par exemple, cette personne a acheté un produit, a visité un magasin, a quitté un site web, etc.) ou un événement qui s’est produit en rapport avec cette personne (par exemple, elle a accumulé 10 000 points de fidélité). C’est ce type d’élément que [!DNL Journey Orchestration] écoute dans les parcours pour orchestrer les meilleures actions qu’il convient de prendre ensuite.

Cette configuration est **obligatoire** dans la mesure où [!DNL Journey Orchestration] a été conçu pour « écouter » des événements. Elle est toujours effectuée par un **utilisateur technique**.

La configuration d’événement vous permet de définir les informations que [!DNL Journey Orchestration] recevra en tant qu’événements. Vous pouvez utiliser plusieurs événements (à différentes étapes d’un parcours) et plusieurs parcours peuvent utiliser un même événement.

Si vous modifiez un événement utilisé dans un parcours actif ou dans un état de brouillon, vous pouvez uniquement en modifier le nom ou la description, ou ajouter des champs de payload. La modification des parcours actifs ou dans un état de brouillon est strictement limitée pour éviter de les interrompre.

Vous pouvez définir deux types d’événements :

* **Événements** basés sur des règles : ce type d’événement ne génère pas d’eventID. En utilisant l’éditeur d’expression simple, vous définissez simplement une règle qui sera utilisée par le système pour identifier les événements pertinents qui déclencheront vos parcours. Cette règle peut être basée sur n’importe quel champ disponible dans la payload, par exemple l’emplacement du profil ou le nombre d’éléments ajoutés au panier du profil.

   >[!CAUTION]
   >
   >Une règle de limitation est définie pour les événements basés sur des règles. Il limite à 5 000 le nombre d’événements qualifiés qu’un parcours peut traiter par seconde pour une organisation donnée (ORG). Il correspond à des contrats de niveau de service Journey Orchestration. Voir cette [page](https://helpx.adobe.com/legal/product-descriptions/journey-orchestration.html).

* **Événements** générés par le système : ces événements nécessitent un eventID. Ce champ eventID est généré automatiquement lors de la création de l’événement. Le système à l’origine de l’envoi de l’événement ne doit pas générer d’identifiant, mais plutôt transmettre celui indiqué dans la prévisualisation de la payload.

Pour savoir comment créer un événement, consultez cette [page](../event/about-creating.md).

