---
title: Configuration des sources de données
description: Découvrez comment configurer la source de données pour le cas d'utilisation avancée du voyage
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# Configuration des sources de données {#concept_vml_hdy_w2b}

Dans notre cas d&#39;utilisation, nous voulons utiliser des données de personnalisation pour nos messages. Nous devons aussi vérifier si la personne est un membre fidèle et n&#39;a pas été contactée au cours des dernières 24 heures. Ces informations sont stockées dans la base de données Profil du client en temps réel. L’utilisateur **** technique doit configurer la source de données de la plateforme d’expérience pour récupérer ces champs.

Pour plus d’informations sur la configuration de la source de données, voir [](../datasource/about-data-sources.md).

1. Dans le menu supérieur, cliquez sur l’onglet Sources **[!UICONTROL de]**données et sélectionnez la source de données de plateforme d’expérience intégrée.

   ![](../assets/journey23.png)

1. Dans les champs de groupe préconfigurés, vérifiez que les champs suivants sont sélectionnés :

   * _personne > nom > firstName_
   * _personne > nom > nom_famille_
   * _PersonalEmail > address_

1. Cliquez sur **[!UICONTROL Ajouter un nouveau groupe]**de champs, sélectionnez un schéma**[!UICONTROL  Profils]** et ajoutez le champ du membre **Fidélité** pour notre condition. Le champ de membre **** Fidélité est un champ personnalisé qui a été ajouté dans XDM : &quot;_customer > marlton > loyaltyMember&quot;

   ![](../assets/journeyuc2_6.png)

1. Cliquez sur **[!UICONTROL Ajouter un nouveau groupe]**de champs, sélectionnez un schéma**[!UICONTROL  ExperienceEvent]** et choisissez les champs nécessaires à notre condition sur le nombre de messages envoyés au cours d’une période donnée : _horodatage_ de la date et du _marketing direct > envoie > valeur_ pour le nombre de messages envoyés.

   ![](../assets/journeyuc2_7.png)

1. Cliquez sur **[!UICONTROL Enregistrer]**.

Nous devons aussi vérifier si la personne a une réservation dans le système de réservation d&#39;hôtel. L’utilisateur **** technique doit configurer une seconde source de données pour récupérer ce champ.

1. Dans la liste des sources de données, cliquez sur **[!UICONTROL Ajouter]**pour ajouter une nouvelle source de données externe afin de définir la connexion à votre système de réservation d’hôtel.

   ![](../assets/journeyuc2_9.png)

1. Entrez un nom pour votre source de données et l’URL du service externe, par exemple : _https://marlton.com/reservation_

   >[!CAUTION]
   >
   >Nous vous recommandons vivement d’utiliser HTTPS pour des raisons de sécurité.

1. Configurez l’authentification en fonction de la configuration du service externe : **[!UICONTROL Aucune clé d’authentification]**,**[!UICONTROL  de base]**, **[!UICONTROL personnalisée]**ou**[!UICONTROL  API. ]** Dans notre exemple, nous choisissons &quot;Élémentaire&quot; pour le type et spécifions le nom d’utilisateur et le mot de passe de l’appel API.

   ![](../assets/journeyuc2_10.png)

1. Cliquez sur **[!UICONTROL Ajouter un nouveau groupe]**de champs pour définir les informations à récupérer et les paramètres de l’API. Dans notre exemple, il n’existe qu’un seul paramètre (l’id). Nous devons donc créer un groupe de champs contenant les informations suivantes :

   * **[!UICONTROL Méthode]**: sélectionnez la méthode POST ou GET. Dans notre cas, nous choisissons la méthode GET.
   * **[!UICONTROL Durée]**du cache : cela varie en fonction de la fréquence des appels d’API. Dans notre cas, le système de réservation est mis à jour toutes les 10 minutes.
   * **[!UICONTROL Charge utile]**de réponse : cliquez dans le champ**[!UICONTROL  Charge]** utile et collez un exemple de charge utile. Vérifiez que les types de champ sont corrects. Chaque fois que l’API est appelée, le système récupère tous les champs inclus dans l’exemple de charge utile. Dans notre exemple, la charge utile contient uniquement l’état de réservation :

   ```
   {
       "reservation" : true
   }
   ```

   * **[!UICONTROL Valeurs]**dynamiques : entrez le paramètre correspondant à la clé utilisée pour identifier chaque client, &quot;id&quot; dans notre exemple. La valeur de ce paramètre sera définie dans le parcours.
   ![](../assets/journeyuc2_11.png)

1. Cliquez sur **[!UICONTROL Enregistrer]**.

   Les sources de données sont maintenant configurées et prêtes à être utilisées dans votre voyage.
