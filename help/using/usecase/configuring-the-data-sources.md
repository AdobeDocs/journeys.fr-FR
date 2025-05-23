---
product: adobe campaign
title: Configuration des sources de données
description: Découvrez comment configurer la source de données pour un cas d’utilisation avancé de parcours
feature: Journeys
role: User
level: Intermediate
exl-id: 2cfa4397-fe8f-44b3-b219-2fd5d3bdd156
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '520'
ht-degree: 100%

---

# Configuration des sources de données {#concept_vml_hdy_w2b}


>[!CAUTION]
>
>**Vous recherchez Adobe Journey Optimizer** ? Cliquez [ici](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/ajo-home){target="_blank"} pour consulter la documentation de Journey Optimizer.
>
>
>_Cette documentation se rapporte aux anciens contenus de Journey Orchestration qui ont été remplacés par Journey Optimizer. Pour toute question concernant votre accès à Journey Orchestration ou Journey Optimizer, contactez votre équipe en charge des comptes._


Dans notre cas d’utilisation, nous voulons utiliser des données de personnalisation pour nos messages. Nous devons aussi vérifier si la personne est un membre du programme de fidélité et si elle n’a pas été contactée au cours des dernières 24 heures. Ces informations sont stockées dans la base de données des profils clients en temps réel. Un **utilisateur technique** doit configurer la source de données Adobe Experience Platform pour récupérer ces champs.

Pour plus d’informations sur la configuration des sources de données, consultez [cette page](../datasource/about-data-sources.md).

1. Dans le volet de menus, sélectionnez **[!UICONTROL Admin]**. Dans la section **[!UICONTROL Sources de données]**, cliquez sur **[!UICONTROL Gérer]**.
1. Sélectionnez la source de données Adobe Experience Platform intégrée.

   ![](../assets/journey23.png)

1. Dans les champs de groupe préconfigurés, vérifiez que les champs suivants sont sélectionnés :

   * _person > name > firstName_
   * _person > name > lastName_
   * _personalEmail > address_

1. Cliquez sur **[!UICONTROL Ajouter un nouveau groupe de champs]**, sélectionnez un schéma **[!UICONTROL Profiles]** et ajoutez le champ **Loyalty member** pour notre condition. Le champ personnalisé **Loyalty member** a été ajouté dans XDM : &quot;_customer > marlton > loyaltyMember&quot;

   ![](../assets/journeyuc2_6.png)

1. Cliquez sur **[!UICONTROL Ajouter un nouveau groupe de champs]**, sélectionnez un schéma **[!UICONTROL ExperienceEvent]** et choisissez les champs nécessaires à notre condition sur le nombre de messages envoyés au cours d’une période donnée : _timestamp_ pour la date et _directMarketing > sends > value_ pour le nombre de messages envoyés.

   ![](../assets/journeyuc2_7.png)

1. Cliquez sur **[!UICONTROL Enregistrer]**.

Nous devons aussi vérifier si la personne a une réservation dans le système de réservation d’hôtel. Un **utilisateur technique** doit configurer une deuxième source de données pour récupérer ce champ.

1. Dans la liste des sources de données, cliquez sur **[!UICONTROL Ajouter]** pour ajouter une nouvelle source de données externe afin de définir la connexion à votre système de réservation d’hôtel.

   ![](../assets/journeyuc2_9.png)

1. Saisissez le nom de la source de données ainsi que l’URL du service externe, par exemple : _https://marlton.com/reservation_

   >[!CAUTION]
   >
   >Nous vous recommandons vivement d&#39;utiliser le protocole HTTPS pour des raisons de sécurité.

1. Configurez l’authentification en fonction de la configuration du service externe : **[!UICONTROL Aucune authentification]**, **[!UICONTROL Simple]**, **[!UICONTROL Personnalisé]** ou **[!UICONTROL Clé API]**. Dans notre exemple, nous choisissons le type « Simple » et spécifions le nom d’utilisateur et le mot de passe pour l’appel d’API.

   ![](../assets/journeyuc2_10.png)

1. Cliquez sur **[!UICONTROL Ajouter un nouveau groupe de champs]** pour définir les informations à récupérer et les paramètres de l’API. Dans notre exemple, il n’existe qu’un seul paramètre (l’identifiant). Nous devons donc créer un groupe de champs contenant les informations suivantes :

   * **[!UICONTROL Méthode]** : sélectionnez la méthode POST ou GET. Dans notre cas, nous sélectionnons la méthode GET.
   * **[!UICONTROL Payload en réponse]** : cliquez dans le champ **[!UICONTROL Payload]** et collez un exemple de payload. Vérifiez que les types de champ sont corrects. À chaque appel de l’API, le système récupère tous les champs contenus dans l’exemple de payload. Dans notre exemple, la payload ne contient que le statut de réservation :

   ```
   {
       "reservation" : true
   }
   ```

   * **[!UICONTROL Valeurs dynamiques]** : entrez le paramètre correspondant à la clé utilisée pour identifier chaque client, « id » dans cet exemple. La valeur de ce paramètre sera définie pendant le parcours.

   ![](../assets/journeyuc2_11.png)

1. Cliquez sur **[!UICONTROL Enregistrer]**.

   Les sources de données sont maintenant configurées et prêtes à être utilisées dans le parcours.
