---
product: adobe campaign
solution: Journey Orchestration
title: À propos des événements
description: En savoir plus sur les événements
translation-type: tm+mt
source-git-commit: c66c09441f69e7026c60c37f87972e1e4ac9f7f8
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 70%

---


# Principe général {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="À propos des événements"
>abstract="Un événement est associé à une personne. Il décrit son comportement (par exemple, cette personne a acheté un produit, a visité un magasin, a quitté un site web, etc.) ou un événement qui s’est produit en rapport avec cette personne (par exemple, elle a accumulé 10 000 points de fidélité). C’est ce type d’élément que [!DNL Journey Orchestration] écoute dans les parcours pour orchestrer les meilleures actions qu’il convient de prendre ensuite."

Un événement est associé à une personne. Il décrit son comportement (par exemple, cette personne a acheté un produit, a visité un magasin, a quitté un site web, etc.) ou un événement qui s’est produit en rapport avec cette personne (par exemple, elle a accumulé 10 000 points de fidélité). C’est ce type d’élément que [!DNL Journey Orchestration] écoute dans les parcours pour orchestrer les meilleures actions qu’il convient de prendre ensuite.

Cette configuration est **obligatoire**[!DNL Journey Orchestration], dans la mesure où est conçu pour « écouter » les événements. Elle est toujours effectuée par un **utilisateur technique**.

La configuration d’événement vous permet de définir les informations que [!DNL Journey Orchestration] recevra en tant qu’événements. Vous pouvez utiliser plusieurs événements (à différentes étapes d’un parcours) et plusieurs parcours peuvent utiliser un même événement.

Si vous modifiez un événement utilisé dans un parcours actif ou dans un état de brouillon, vous pouvez uniquement en modifier le nom ou la description, ou ajouter des champs de payload. La modification des parcours actifs ou dans un état de brouillon est strictement limitée pour éviter de les interrompre.

Vous pouvez définir deux types de événements :

* **Événements basés sur** des règles : ce type de événement ne génère pas d’eventID. En utilisant l&#39;éditeur d&#39;expressions simple, vous définissez simplement une règle qui sera utilisée par le système pour identifier les événements pertinents qui déclencheront vos voyages. Cette règle peut être basée sur n’importe quel champ disponible dans le payload, par exemple l’emplacement du profil ou le nombre d’éléments ajoutés au panier du profil.

   >[!CAUTION]
   >
   >Une règle de limitation est définie pour les événements basés sur des règles. Elle limite à 400 000 par minute le nombre d’événements qualifiés qu’un parcours peut traiter. Pour plus d’informations, contactez votre point de contact du programme Alpha. Outre cette règle de plafonnement, une limite de 5 000 événements pour les secondes est définie au niveau du parcours.

* **Événements générés** par le système : ces événements nécessitent un eventID. Ce champ eventID est généré automatiquement lors de la création du événement. Le système qui pousse le événement ne doit pas générer d’identifiant, il doit transmettre celui disponible dans la prévisualisation de charge utile.

Pour savoir comment créer un événement, reportez-vous à cette [page](../event/about-creating.md).

