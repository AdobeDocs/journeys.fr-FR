---
product: adobe campaign
title: Notes de mise à jour
description: En savoir plus sur les notes de mise à jour
feature: Journeys
role: User
level: Beginner
exl-id: b923f7e3-997b-483b-b6ac-eef62fc81a84
source-git-commit: 4f6c5f9326b4d1cc4a1a02a036b51e4ad1ae68c4
workflow-type: ht
source-wordcount: '4458'
ht-degree: 100%

---

# Notes de mise à jour {#release-notes}

>[!CAUTION]
>
>**Vous recherchez Adobe Journey Optimizer** ? Cliquez [ici](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/ajo-home){target="_blank"} pour consulter la documentation de Journey Optimizer.
>
>
>_Cette documentation se rapporte aux anciens contenus de Journey Orchestration qui ont été remplacés par Journey Optimizer. Pour toute question concernant votre accès à Journey Orchestration ou Journey Optimizer, contactez votre équipe en charge des comptes._

Cette page répertorie toutes les nouvelles fonctionnalités et améliorations de Journey Orchestration. Consultez les [notes de mise à jour](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=fr) pour découvrir les nouvelles fonctionnalités d’Experience Platform.

Pour les fonctionnalités publiées après 2022, les liens renvoient à la [documentation d’Adobe Journey Optimizer](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/ajo-home){target="_blank"}.

## Version de mars 2024 {#mar-rn-2024}

### Améliorations {#mar-2024-improvements}

De nouveaux statuts intermédiaires ont été ajoutés au cycle de vie de création de parcours :

* Statut **Publication** entre le statut **Brouillon** et le statut **Actif**
* Statut **Arrêt en cours** entre le statut **Actif** et le statut **Arrêté**
* Statuts **Activer le mode test** ou **Désactiver le mode test** entre le statut **Brouillon** et le statut **Brouillon (test)**

Lorsqu’un parcours se trouve dans un état intermédiaire, il est en lecture seule. [En savoir plus](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/orchestrate-journeys/create-journey/journey-gs#filter){target="_blank"}

## Version de février 2024 {#feb-rn-2024}

### Améliorations {#feb-2024-improvements}

* **Filtrer vos parcours** : vous pouvez désormais utiliser les **dates personnalisées pour filtrer l’inventaire des parcours**, en plus des filtres de dates prédéfinis existants. Vous pouvez ainsi affiner la liste en affichant les parcours créés ou publiés à une date spécifique, au cours d’un mois donné, sur une année entière ou dans des périodes spécifiées. [En savoir plus](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/journey-gs.html?lang=fr#filter){target="_blank"}
* **Actions personnalisées** : vous pouvez maintenant mettre à jour l’en-tête **content-type**. Ce nouveau **content-type** doit référencer le contenu JSON. [En savoir plus](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configure-journeys/action-journeys/about-custom-action-configuration.html?lang=fr#url-configuration){target="_blank"}
* **Configuration** : l’attribut identityMap dans stepEvents est maintenant prérenseigné. L’identité principale est définie comme « primary = true ». [En savoir plus](https://experienceleague.adobe.com/docs/journey-optimizer/using/reporting/reports/sharing-field-list.html?lang=fr){target="_blank"}
* **Interface utilisateur** : la barre supérieure, dans les écrans de parcours, a été réorganisée pour une expérience améliorée. Parmi les différentes mises à jour, l’icône « crayon » permettant d’accéder aux propriétés du parcours s’affiche désormais à gauche de la barre supérieure, en regard du nom du parcours. [En savoir plus](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/journey-gs.html?lang=fr#change-properties){target="_blank"}

## Version de janvier 2024 {#jan-rn-2024}

### Améliorations {#jan-2024-improvements}

* **Durée des événements de réaction** - La durée maximale que vous pouvez définir dans les **Événements de réaction** est désormais de 29 jours au lieu de 30. [En savoir plus](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/about-journey-building/reaction-events.html?lang=fr){target="_blank"}
* **Groupes de champs** - Cette version corrige un problème qui empêchait l’enregistrement de groupes de champs dans certains cas.
* La prise en charge de `<listObject>` a été modifiée dans plusieurs fonctions.

## Version d’août 2023 {#aug-rn-2023}

### Améliorations {#aug-2023-improvements}

* Vous pouvez désormais utiliser les réponses d’appel API dans des actions personnalisées et orchestrer votre parcours en fonction de ces réponses. Cette fonctionnalité est publiée sous forme de version Beta privée. Consultez la [documentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configure-journeys/action-journeys/action-response.html?lang=fr){target="_blank"} de Journey Optimizer.

## Version d’avril 2023 {#apr-rn-2023}

### Améliorations {#april-2023-improvements}

* La disposition du volet de configuration, qui s’affiche dans les actions, les sources de données, les événements et les parcours, a été améliorée.
* Vous pouvez désormais définir des paramètres de requête statiques ou dynamiques dans vos actions personnalisées. Consultez la [documentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configure-journeys/action-journeys/about-custom-action-configuration.html?lang=fr#url-configuration){target="_blank"} de Journey Optimizer.
* De nouveaux mécanismes de sécurisation ont été définis afin de gérer la croissance des expériences fournies par les parcours :
   * Nous vous recommandons de limiter le nombre de nœuds à 50 ou moins afin d’assurer les performances et de faciliter la lecture, le contrôle qualité et la résolution de problèmes de vos parcours. Le nombre d’activités s’affiche dans la section supérieure gauche de la zone de travail du parcours. Consultez la [documentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/guardrails.html?lang=fr#journeys-guardrails-journeys){target="_blank"} de Journey Optimizer.
   * Développez et lancez vos premiers parcours. Dès que la barre des 100 parcours actifs à la fois se profile à l’horizon, nous ne manquerons pas de vous en informer. Si vous prévoyez d’emblée de lancer 100 parcours à la fois, créez un ticket de support après avoir reçu la notification et nous vous aiderons à concrétiser vos projets. Consultez la [documentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/guardrails.html?lang=fr#journeys-guardrails-journeys){target="_blank"} de Journey Optimizer.

## Version de mars 2023 {#mar-2023}

### Améliorations {#mar-2023-improvements}

* La nouvelle **API de limitation** vous permet de limiter le nombre d’événements envoyés par seconde. Vous pouvez ainsi éviter les pics de trafic importants sur vos systèmes ou API externes. Lorsque la limite définie est atteinte, tous les appels API suivants sont placés en file d’attente et traités dès que possible, dans l’ordre dans lequel ils ont été reçus. Notez que cette fonctionnalité ne prend en charge qu’une seule configuration de limitation pour toutes vos sandbox. [En savoir plus](../api/throttling.md).
* Amélioration de la zone de travail Parcours pour offrir une expérience utilisateur plus fluide et épurée. Suppression des espaces réservés vides à la fin de chaque chemin de la zone de travail. Vous pouvez maintenant simplement ajouter vos activités en les faisant glisser à la fin d’un chemin.
* Dans la zone de travail Parcours, la balise **Fin** n’est plus définie automatiquement avec le nom de l’activité précédente. Si nécessaire, les utilisateurs et utilisatrices peuvent indiquer un libellé personnalisé manuellement.
* Le délai d’expiration par défaut et la durée d’erreur dans les propriétés du parcours passent de 5 à 30 secondes. Consultez la [documentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configure-journeys/external-systems/external-systems.html?lang=fr#timeout){target="_blank"} de Journey Optimizer.
* Un mécanisme de sécurisation a été ajouté au mode test pour n’écouter que les événements envoyés via l’interface. Les événements envoyés par l’intermédiaire d’un outil externe ne sont pas pris en compte. Consultez la [documentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/testing-the-journey.html?lang=fr){target="_blank"} de Journey Optimizer.

## Version de février 2023 {#feb-2023}

### Améliorations {#feb-2023-improvements}

* Le champ **Période d’attente de reprise** a été ajouté aux propriétés du parcours. Ce champ vous permet de définir le temps d’attente avant d’autoriser un profil à entrer à nouveau dans le parcours en parcours unitaires (en commençant par un événement ou une qualification de segment). Cela empêche les parcours d’être déclenchés plusieurs fois par erreur pour le même événement. Par défaut, le champ est défini sur 5 minutes. Consultez la [documentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/journey-gs.html?lang=fr#entrance){target="_blank"} de Journey Optimizer.
* Des améliorations ont été apportées aux **dates de début et de fin de parcours**. Si vous n’avez pas spécifié de date de début, elle est désormais automatiquement ajoutée au moment de la publication. Cela permet aux profils de se fermer automatiquement lorsque la date est atteinte. Consultez la [documentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/journey-gs.html?lang=fr#dates){target="_blank"} de Journey Optimizer.

## Version de janvier 2023 {#jan-2023-release}

### Améliorations {#jan-2023-improvements}

* Lors de l’ajout d’une **qualification de segment** dans un parcours, l’espace de noms est maintenant prérempli par défaut avec le dernier espace de noms utilisé. Consultez la [documentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/about-journey-building/segment-qualification-events.html?lang=fr#about-segment-qualification){target="_blank"} de Journey Optimizer.
* Dans la zone de travail du parcours, un nouveau bouton est disponible dans la barre d’outils. Il permet de télécharger une copie d’écran de votre parcours.

## Version de septembre 2022{#sept-2022-release}

### Nouvelles fonctionnalités{#sept-2022-features}


<table>
<thead>
<tr>
<th><strong>Gouvernance et confidentialité des données</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Grâce à son cadre de gouvernance DULE (Data Usage Labelling and Enforcement), Journey Orchestration peut désormais tirer parti des politiques de gouvernance d’Adobe Experience Platform pour empêcher l’exportation de champs sensibles vers des systèmes tiers au moyen d’actions personnalisées. Si le système identifie un champ restreint dans les paramètres d’action personnalisée, une erreur s’affiche, vous empêchant de publier le parcours.</p>
<p>L’utilisation de l’outil DULE (Data Usage Labelling and Enforcement) est actuellement limitée à certains clients et sera déployée dans tous les environnements dans une prochaine version.</p>
<p>Pour plus d’informations, consultez la <a href="https://experienceleague.adobe.com/docs/journey-optimizer/using/privacy/action-privacy.html?lang=fr">documentation</a> de Journey Optimizer.
</td>
</tr>
</tbody>
</table>

### Améliorations{#sept-2022-improvements}

* Une nouveau mécanisme de sécurisation a été ajouté aux parcours unitaires (commençant par un événement ou une qualification de segment) pour empêcher que les parcours ne soient déclenchés par erreur plusieurs fois pour le même événement. La reprise du profil sera désormais temporairement bloquée par défaut pendant 5 minutes. Consultez la [documentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/guardrails.html?lang=fr#events-g){target="_blank"} de Journey Optimizer.

### Autres modifications{#sept-2022-other}

* Pour améliorer les performances, les groupes de champs d’événement d’expérience ne peuvent plus être utilisés dans les parcours commençant par une activité de qualification de segment. Cette modification s’applique uniquement aux nouveaux parcours. Ceux qui existent déjà conserveront le comportement actuel. Consultez la [documentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/guardrails.html?lang=fr#expression-editor){target="_blank"} de Journey Optimizer.

### Améliorations

* **Terminaison d’un parcours** : dans la zone de travail du parcours, l’activité **Fin** a été supprimée de la palette. Les balises de fin sont désormais ajoutées par défaut à la fin de chaque chemin et ne peuvent pas être supprimées. Cette amélioration permet de créer un rapport plus optimal sur le moment où un client a quitté le parcours, sans aucune action requise de la part du praticien de parcours. Consultez la [documentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/manage-journey/end-journey.html?lang=fr){target="_blank"} de Journey Optimizer.

* L’option **Fuseau horaire du profil** est désormais décochée par défaut dans les propriétés de parcours. [En savoir plus](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/manage-journey/timezone-management.html?lang=fr#timezone-from-profiles){target="_blank"}.

## Version de mai 2022 {#may-2022-release}

### Améliorations

* **Éditeur d’expression** : la fonction [limit](../functions/functionlimit.md) a été ajoutée pour vous permettre de limiter le nombre d’éléments d’une liste. La fonction [sort](../functions/functionsort.md) vous permet désormais de trier un objet de liste. La prise en charge de listObject a également été ajoutée aux fonctions [Disctinct](../functions/functiondistinct.md) et [distinctWithNull](../functions/functiondistinctwithnull.md).

## Version de mars 2022 {#feb-2022-release}

### Améliorations

* Pour éviter d’avoir des champs inutiles dans le schéma de profil unifié, le schéma Événement d’étape du parcours n’est plus activé par défaut pour les profils. Si nécessaire, vous pouvez l’activer. [En savoir plus](../building-journeys/sharing-overview.md)
* Les nouveaux événements d’étape liés aux traitements d’exportation sont désormais envoyés par Journey Optimizer à Adobe Experience Platform. Des exemples de requêtes ont été ajoutés à la documentation. [En savoir plus](../building-journeys/query-examples.md)

## Version de février 2022 {#february-2022-release}

### Améliorations

* Pour optimiser les performances et empêcher l’utilisation des ressources obsolètes, tous les parcours en mode test qui n’ont pas été déclenchés pendant une semaine repassent au statut Brouillon. [En savoir plus](../building-journeys/testing-the-journey.md#important_notes)

## Version de janvier 2022 {#january-2022-release}

### Améliorations

* Les événements d’étape Journey Orchestration peuvent désormais être liés à d’autres jeux de données dans [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=fr){target="_blank"}. Le champ **profileID**, dans le schéma d’événement d’étape du parcours intégré, est désormais défini comme un champ d’identité. [En savoir plus](../building-journeys/sharing-overview.md#integration-cja)
* La règle de limitation pour les actions Adobe Campaign Standard a été modifiée et passe à 4 000 appels/5 minutes. [En savoir plus](../action/working-with-adobe-campaign.md)

## Version d’octobre 2021 {#october-2021-release}

### Améliorations

* **Éditeur dʼexpression** : compte tenu de vos compétences techniques, vous pouvez désormais utiliser des fonctions pour travailler avec les cartes. [En savoir plus](../expression/field-references.md)
* **Accessibilité** : des améliorations d’accessibilité ont été apportées. Journey Orchestration répond désormais entièrement aux exigences en matière d’accessibilité.
* **Collections** : les tableaux d’objets contenant des sous-objets sont désormais pris en charge. [En savoir plus](../usecase/collections.md)
* **Surveillance** : les événements d’étape pour les parcours actifs et le mode test ont été améliorés. De [nouveaux champs](../building-journeys/sharing-field-list.md#serviceevents) ont été ajoutés en rapport avec les tâches d’exportation de profil. Pour une meilleure expérience utilisateur, les champs d’événement d’étape sont désormais organisés en différentes catégories dans le schéma d’événement d’étape du parcours pour Journey Orchestration. Tous les champs d’événements d’étape précédents sont toujours disponibles dans la catégorie [stepEvents](../building-journeys/sharing-legacy-fields.md).

## Version de septembre 2021 {#september-2021-release}

<table>
<thead>
<tr>
<th><strong>Transmission dynamique de listes de données à l’aide d’actions personnalisées</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Vous pouvez désormais transmettre des collections ou une liste de données dans vos paramètres d’action personnalisés qui seront renseignés dynamiquement au moment de l’exécution. Deux types de collections sont pris en charge : collections simples et collections d’objets. Les actions personnalisées créées précédemment continueront à fonctionner. </p>
<p>Pour plus d’informations sur les collections, consultez la <a href="../usecase/collections.md">documentation détaillée</a>. </p>
<p>Les fonctions filter et intersect ont été ajoutées à la liste des fonctions disponibles dans l’éditeur d’expression avancé. Cela offre davantage de possibilités de filtrage et de comparaison des collections.</p>
<p>Consultez la documentation sur les fonctions <a href="../functions/functionfilter.md">filter</a> et <a href="../functions/functionintersect.md">intersect</a>.</p>
</td>
</tr>
</tbody>
</table>

### Améliorations

* Les schémas et les jeux de données générés par le système qui ont été créés pendant l’approvisionnement des événements d’étape sont désormais en lecture seule, ce qui permet d’éviter toute modification involontaire des schémas critiques. [En savoir plus](../building-journeys/sharing-overview.md)
* Étiquetez de manière claire l’activité **Attente** avec un libellé qui s’affichera dans la zone de travail. Le libellé est également utilisé dans les journaux des modes de reporting et de test pour identifier clairement ce que vous faites. [En savoir plus](../building-journeys/using-the-journey-designer.md)
* Trouvez plus rapidement vos événements et actions en filtrant les éléments dans les catégories **Événements** et **Action** à l’aide de la recherche. Les activités d’orchestration ne sont plus filtrées. [En savoir plus](../building-journeys/using-the-journey-designer.md)
* Lors de la définition dʼune condition dʼidentifiant dʼévénement dans un événement basé sur des règles, lʼopérateur « contains » est désormais disponible pour les types de chaînes de champs. [En savoir plus](../event/about-creating.md)

## Version d’août 2021 {#august-2021-release}

### Améliorations

**Parcours**

* **En-têtes dynamiques** : vous pouvez désormais transmettre des données dynamiques dans les paramètres d’en-tête HTTP. Ces paramètres peuvent être utilisés par les systèmes d’intégration qui reçoivent les appels HTTP de l’action de parcours, par exemple l’horodatage ou l’ID de suivi. [En savoir plus](../action/url-configuration.md)
* **Chemins d’URL dynamiques** : vous pouvez désormais configurer des chemins d’URL dynamiques pour les actions personnalisées. [En savoir plus](../action/url-configuration.md)

## Version de juillet 2021 {#july-2021-release}

<table>
<thead>
<tr>
<th><strong>Utilisation des relations de schéma</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience Platform vous permet de définir des relations entre les schémas afin d’utiliser un jeu de données comme table de choix pour un autre. Journey Orchestration peut désormais exploiter les données provenant d’un schéma lié.</p>
<p>Ces champs sont disponibles dans la configuration d’événement unitaire, les conditions de parcours et la personnalisation d’action personnalisée.
<p>Pour plus d’informations, consultez la <a href="../event/experience-event-schema.md#leverage_schema_relationships">documentation détaillée</a>.</p>
</td>
</tr>
</tbody>
</table>

### Améliorations

* Le champ **Durée de mise en cache** a été supprimé du volet de configuration de la source de données. [En savoir plus](../datasource/about-data-sources.md)

## Version de juin 2021 {#june-2021-release}

<table>
<thead>
<tr>
<th><strong> Intégration d’Adobe Campaign Classic</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>L’intégration avec Adobe Campaign Classic est maintenant en version GA. Elle vous permet d’envoyer des e-mails, des notifications push et des SMS à l’aide des fonctionnalités de messagerie transactionnelle d’Adobe Campaign v7 ou v8.</p>
<p>La connexion entre les instances Journey Orchestration et Campaign est configurée par Adobe au moment de l’approvisionnement.</p>
<p>Pour plus d’informations, consultez la <a href="../action/acc-action.md">documentation détaillée</a>.</p>
</td>
</tr>
</tbody>
</table>

### Améliorations

* Pour les sources de données externes, une règle de limitation de 15 appels par seconde est maintenant définie automatiquement. [En savoir plus](../about/external-systems.md#capping)
* Les éditeurs d’expression simple et avancés prennent maintenant en charge le format de date XDM.
* Un nouveau filtre a été ajouté à l’écran de liste de parcours. Vous pouvez maintenant filtrer par type de parcours : **[!UICONTROL Événement unitaire]** ou **[!UICONTROL Qualification du segment]**. [En savoir plus](../about/user-interface.md#section_lgm_hpz_pgb)
* Pour les parcours actifs, l’écran des propriétés du parcours affiche maintenant la date de publication et le nom de l’utilisateur ou de l’utilisatrice qui a publié le parcours. Ces informations sont également disponibles lorsque vous copiez les détails techniques du parcours. [En savoir plus](../building-journeys/changing-properties.md#section_lgm_hpz_pgb)

## Version d’avril 2021 {#april-2021-release}

### Améliorations

* Dans l’écran **Configuration de l’événement** du mode test, une liste déroulante s’affiche désormais pour les champs qui prévoient une énumération. Il suffit de sélectionner l’une des valeurs disponibles. Ceci évite les erreurs lors du déclenchement de l’événement si une valeur incorrecte est définie. [En savoir plus](../building-journeys/testing-the-journey.md#firing_events)

## Version de mars 2021 {#march-2021-release}

### Améliorations

* Un nouveau statut a été ajouté aux parcours. Lorsqu’un parcours se termine ou est fermé manuellement, son statut passe de **Fermé** à **Terminé** 30 jours après sa fermeture. Ainsi, vous pouvez identifier plus facilement les parcours inactifs tout en vous assurant que chaque individu encore présent a le temps de terminer le parcours. [En savoir plus](../building-journeys/journey.md#ending_a_journey)
* Dans les volets d’activité à droite des parcours en version brouillon, les champs en lecture seule sont désormais masqués par défaut. Cette simplification de l’interface vous permettra de configurer vos activités plus facilement. Pour les afficher, cliquez sur l’icône **Afficher les champs en lecture seule**, disponible dans le coin supérieur gauche du volet de configuration de l’activité. [En savoir plus](../building-journeys/using-the-journey-designer.md#configuration_pane)
* En mode test, dans l’écran de **Configuration de l’événement**, le champ **Clé** utilisé pour définir l’identifiant du profil de test a été renommé **Identifiant du profil** afin d’offrir une meilleure expérience client. [En savoir plus](../building-journeys/testing-the-journey.md).
* Désormais, pour les événements de réaction, la durée de la temporisation ne peut être définie qu’entre 40 secondes et 30 jours. Lors du test d’un parcours qui a recours à un événement de réaction, la **[!UICONTROL Durée d’attente]** du mode test par défaut ainsi que sa valeur minimale sont désormais de 40 secondes. [En savoir plus](../building-journeys/reaction-events.md).

## Version de février 2021 {#february-2021-release}

<table>
<thead>
<tr>
<th><strong>Mettre à jour l’activité du profil</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Cette nouvelle activité d’action vous permet de mettre à jour un profil Adobe Experience Platform existant avec des informations provenant de l’événement, d’une source de données ou à l’aide d’une valeur spécifique.</p>
<p>Pour plus d’informations, consultez la <a href="../building-journeys/update-profiles.md">documentation détaillée</a>.</p>
</td>
</tr>
</tbody>
</table>

### Autres améliorations 

* Désormais, lors de la configuration d’un événement, seuls les champs obligatoires pour la validation XDM sont présélectionnés par défaut. Ces champs ne peuvent pas être désélectionnés.
* Un nouveau filtre a été ajouté à la palette du parcours. Il vous permet d’afficher uniquement les cinq derniers événements et actions utilisés, en plus de ceux d’usine. Il est spécifique à chaque utilisateur ou utilisatrice. Par défaut, tous les éléments s’affichent. [En savoir plus](../building-journeys/using-the-journey-designer.md#palette)
* Lors du démarrage d’un nouveau parcours, les éléments qui ne peuvent pas être déposés dans la zone de travail comme première étape sont désormais masqués. Cela concerne toutes les actions, l’activité de la condition, l’attente et la réaction.
* Dans la partie gauche de l’éditeur d’expression avancé, les fonctions sont désormais regroupées sous une section **Fonctions** en fin de liste.

## Version de janvier 2021 {#january-2021-release}

Lors de la sélection d’un schéma dans la configuration de l’événement, seuls les champs obligatoires pour que l’événement soit correctement reçu par Journey Orchestration sont sélectionnés. [En savoir plus](../event/defining-the-payload-fields.md)

Les attributs de propriétés du parcours sont désormais disponibles dans l’éditeur d’expression simple. [En savoir plus](../expression/journey-properties.md)

Deux nouveaux attributs de propriétés du parcours ont été ajoutés (sandboxName et organizationId). [En savoir plus](../expression/journey-properties.md)

Pour s’aligner sur les contrats de niveau de service Adobe Campaign Standard, une règle de limitation de 13 appels par seconde est désormais automatiquement définie pour les actions Adobe Campaign Standard dès que l’intégration Adobe Campaign Standard est configurée. [En savoir plus](../action/working-with-adobe-campaign.md)

La durée de la temporisation d’un événement est désormais spécifiée plus clairement sur le chemin de la temporisation. [En savoir plus](../building-journeys/event-activities.md#listening-to-events-during-a-specific-time)

Les fonctions [getListItem](../functions/functiongetlistitem.md) et [split](../functions/functionsplit.md) ont été ajoutées à la liste des fonctions disponibles dans l’éditeur d’expression avancé. Cet ajout apporte davantage de possibilités de cas d’utilisation pour les calculs sur les chaînes.

## Version de novembre 2020 {#november-release}

<table>
<thead>
<tr>
<th><strong>Passage d’un parcours à un autre</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Une nouvelle activité d’action vous permet d’inviter des individus à passer d’un parcours à un autre. L’activité <strong>Saut</strong> vous permet d’effectuer les opérations suivantes :
</p>
<ul>
<li>simplifier la conception de parcours très complexes en les divisant en plusieurs autres ; </li>
<li>créer des parcours basés sur des schémas de parcours communs et réutilisables.</li>
</ul>
<p>Pour plus d’informations, consultez la <a href="../building-journeys/jump.md">documentation détaillée</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Utilisation des propriétés de parcours dans l’éditeur d’expression</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Dans l’éditeur d’expression avancé, nous avons ajouté une nouvelle catégorie à la liste des champs et des fonctions. Il s’agit des informations récupérées par le système à partir de parcours dynamiques, telles que l’identifiant du parcours ou les erreurs spécifiques rencontrées. Vous aurez ainsi plus de possibilités lors de la création de vos parcours. Par exemple, vous pourrez alerter les systèmes tiers en cas d’erreurs rencontrées dans une condition ou une action.
</p>
<p>Pour plus d’informations, consultez la <a href="../expression/journey-properties.md">documentation détaillée</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Événements basés sur des règles (version bêta)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Une nouvelle méthode est maintenant disponible pour configurer vos événements plus facilement, sans utiliser d’identifiant d’événement eventID : des événements basés sur des règles évaluent si l’événement doit être déclenché selon une condition. Vous pouvez toujours utiliser la méthode existante, maintenant appelée « généré par le système ». Cette fonctionnalité, qui a été testée auprès d’un nombre limité de clientes et clients via le programme Alpha, est maintenant disponible en version bêta pour tout le monde.
</p>
</td>
</tr>
</tbody>
</table>

### Autres améliorations 

Des limites ont été ajoutées lors de la création de nouvelles versions d’un parcours. Ces limites évitent des changements trop radicaux dans le parcours pour maintenir une certaine cohérence entre les versions. [En savoir plus](../about/limitations.md#journey-versions-limitations)

L’activité **Qualification de segment** ne peut plus être utilisée dans un parcours qui inclut des activités de messages Campaign Standard. Cette restriction protège l’intégrité des instances Adobe Campaign Standard. En effet, l’utilisation de la qualification de segment peut conduire à des pics quotidiens d’envoi de messages qui surchargent les messages transactionnels de Campaign Standard. [En savoir plus](../about/limitations.md#segment-qualification)

## Version d’octobre 2020 {#october-release}

<table>
<thead>
<tr>
<th><strong>Temporisation d’un événement</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Vous pouvez maintenant configurer une temporisation d’un événement pour que le parcours ne l’écoute que pendant une certaine période. Pour ce faire, vous n’avez plus besoin d’ajouter une activité Attente parallèlement au chemin de l’événement.
</p>
<p>Pour plus d’informations, consultez la <a href="../building-journeys/event-activities.md#listening-to-events-during-a-specific-time">documentation détaillée</a>.</p>
</td>
</tr>
</tbody>
</table>

### Autres améliorations 

* Lorsque vous publiez une nouvelle version d’un parcours, la version précédente se termine automatiquement et passe au statut Fermé. [En savoir plus](../building-journeys/journey-versions.md)

## Version de septembre 2020 {#september-release}

### Mises à jour de la version GA{#september-ga-update}

<table>
<thead>
<tr>
<th><strong>Améliorations de l’activité de condition</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Lorsque vous ajoutez des conditions à votre parcours, vous pouvez maintenant définir un libellé. Si vous utilisez plusieurs conditions dans un parcours, vous pouvez ainsi les identifier plus facilement.
</p>
<p>Pour plus d’informations, consultez la <a href="../building-journeys/condition-activity.md#about_condition">documentation détaillée</a>.</p>
</td>
</tr>
</tbody>
</table>

### Mises à jour de la version Alpha{#september-alpha-update}

<table>
<thead>
<tr>
<th><strong>Amélioration de l’activité Lecture de segment</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Les améliorations suivantes ont été apportées à l’activité <strong>Lecture de segment</strong> :
</p>
<ul>
<li><p>Les parcours basés sur des segments affichent maintenant, au-dessus de la zone de travail, un rappel du type de planification du parcours Vous pouvez cliquer sur ce rappel pour accéder au menu de configuration des planifications.</p>
</li>
<li><p>La granularité des journaux du mode test a été améliorée pour afficher l’état d’avancement de l’export des segments.</p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

## Version d’août 2020 {#august-release}

### Mises à jour de la version GA{#august-ga-update}

La payload des événements de qualification de segment contient maintenant les informations contextuelles suivantes, que vous pouvez utiliser dans les conditions et actions : le comportement (entrée, sortie), l’horodatage de la qualification et l’identifiant du segment. [En savoir plus](../building-journeys/segment-qualification-events.md)

### Mises à jour de la version Alpha{#august-alpha-update}

<table>
<thead>
<tr>
<th><strong>Activité Déclencheur de segment</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Les améliorations suivantes ont été apportées à l’activité Déclencheur de segment :
</p>
<ul>
<li><p>Le nom de l’activité a été remplacé par « Lecture de segment ». </p>
</li>
<li><p>La configuration du planificateur de parcours a été supprimée des propriétés de l’activité. Elle est maintenant accessible directement à partir des propriétés du parcours, dans une section dédiée qui s’affichera si une activité de Lecture de segment a été déposée dans la zone de travail. </p>
</li>
<li><p>Vous pouvez maintenant tester le parcours sur un profil unitaire et suivre sa progression dans le parcours à l’aide du flux visuel.</p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Événements basés sur des règles       </strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Les améliorations suivantes ont été apportées aux événements basés sur des règles :
</p>
<ul>
<li><p>Vous pouvez maintenant utiliser toutes les données d’événement comportemental Adobe Analytics que vous capturez déjà et diffusez en continu dans Platform afin de déclencher des parcours et d’automatiser les expériences de vos clientes et clients. <a href="../event/about-analytics.md">En savoir plus</a></p>
</li>
<li><p>Lors du déclenchement d’un événement basé sur des règles en mode test, vous pouvez désormais afficher directement la condition d’identifiant d’événement. En outre, une info-bulle a été ajoutée en regard de chaque champ qui fait partie de l’évaluation des règles. <a href="../building-journeys/testing-the-journey.md#test-rule-based">En savoir plus</a></p>
</li>
<li><p>L’écran de définition des événements basés sur des règles a été réorganisé pour améliorer l’expérience. <a href="../event/about-creating.md">En savoir plus</a></p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

## Version Alpha - Juillet 2020 {#alpha-release---july-2020}

Le programme Alpha offre des fonctionnalités qui sont actuellement testées auprès d’un nombre limité de clientes et clients. Cela nous permet d’améliorer notre produit en fonction des commentaires reçus. Ces fonctionnalités ne sont pas disponibles pour toutes les personnes qui utilisent Journey Orchestration.

<table>
<thead>
<tr>
<th><strong>Interface utilisateur améliorée</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>La navigation dans les menus Journey Orchestration a été améliorée afin de fournir une interface en cohérence avec Adobe Experience Platform :
</p>
<ul>
<li><p>Menus déplacés du haut vers le côté gauche de l’interface </p>
</li>
<li><p>Regroupement des fonctionnalités d’administration en un seul tableau de bord</p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Activité Déclencheur de segment</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>L’activité Déclencheur de segment vous permet de faire en sorte que tous les individus appartenant à un segment Adobe Experience Platform rejoignent un parcours. L’entrée dans un parcours peut être effectuée une fois, ou régulièrement. 
</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Événements basés sur des règles       </strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nous avons simplifié la configuration des événements d’expérience. Nous proposons une nouvelle méthode qui ne nécessite pas l’utilisation d’un identifiant d’événement. Lorsque vous configurez votre événement dans Journey Orchestration, vous pouvez désormais définir un événement basé sur des règles. <a href="../event/about-events.md">En savoir plus</a>
</p>
</td>
</tr>
</tbody>
</table>


## Version du 2e trimestre - Juin 2020 {#q2-release---june-2020}

<table>
<thead>
<tr>
<th><strong>Améliorations de l’intégration d’Adobe Experience Platform</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Les améliorations suivantes ont été apportées à l’intégration d’Adobe Experience Platform :</p>
<ul>
<li><p>Une nouvelle activité permet d’écouter les entrées/sorties des segments d’Adobe Experience Platform pour que des personnes rejoignent un parcours ou y progressent. <a href="../building-journeys/segment-qualification-events.md">En savoir plus</a></p>
<img src="../assets/rn-segment7.png"/>
</li>
<li><p>Il est désormais possible de créer et modifier les segments Adobe Experience Platform sans quitter l’interface de Journey Orchestration, grâce au nouvel onglet <strong>Segments</strong>. <a href="../segment/about-segments.md">En savoir plus</a></p>
<img src="../assets/rn-segment1.png"/>
</li>
<li><p>Dans l’éditeur d’expression simple, les segments Adobe Experience Platform sont maintenant directement répertoriés dans l’arborescence de navigation pour faciliter la configuration de conditions telles que « cette personne appartient-elle au segment A ? ». <a href="../segment/using-a-segment.md">En savoir plus</a></p>
<img src="../assets/rn-segment4.png"/>
</li>
<li><p>Journey Orchestration transmet maintenant automatiquement à Adobe Experience Platform les étapes exécutées dans les parcours. Les erreurs potentielles rencontrées sont indiquées. Ces informations peuvent être utilisées à des fins de reporting et de dépannage en exécutant des requêtes sur les événements d’étape du parcours pour un parcours particulier ou pour tous les parcours. <a href="../building-journeys/sharing-overview.md">En savoir plus</a></p>
<img src="../assets/rn-journeystepevent.png"/>
</li>
<li><p>Il est maintenant possible de connecter Journey Orchestration aux sandbox Adobe Experience Platform pour la production et hors production. Notez que les sandbox sont une fonctionnalité en version bêta. <a href="../about/access-management.md#sandboxes">En savoir plus</a></p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Améliorations apportées au concepteur de parcours et au mode test</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Les améliorations suivantes ont été apportées au concepteur de parcours et au mode test :</p>
<ul>
<li><p>Vous pouvez maintenant copier/coller les activités d’un parcours vers un autre, en sélectionnant 1 ou N activités de parcours. <a href="../building-journeys/using-the-journey-designer.md#copy-paste">En savoir plus</a></p>
<img src="../assets/rn-copy-paste1.png"/>
</li>
<li><p>Après avoir déclenché un événement pour qu’un profil de test rejoigne un parcours, vous pouvez maintenant voir sa progression tout au long du parcours grâce à un flux visuel coloré. En cas d’erreur dans le parcours, les détails des erreurs s’affichent également. <a href="../building-journeys/testing-the-journey.md#firing_events">En savoir plus</a></p>
<img src="../assets/rn-journeytest6.png"/>
</li>
<li>L’état de parcours <strong>Terminé</strong> a été renommé <strong>Fermé (aucune entrée)</strong> pour mieux refléter le sens de cet état.</li>
</ul>
</td>
</tr>
</tbody>
</table>

**Autres améliorations**

Pour éviter d’envoyer un trop grand nombre d’appels d’API à des systèmes tiers, nous introduisons une nouvelle API publique pour configurer les règles de « limitation ». Les règles de limitation permettent de définir un nombre maximal d’appels à un point d’entrée d’API par millisecondes. [En savoir plus](../api/capping.md)

Le contrôle d’accès permet maintenant une plus grande granularité dans la gestion des accès des utilisateurs. Disponibilité effective : 30 juin 2020. [En savoir plus](../about/access-management.md#create-product-profile)

Journey Orchestration est maintenant disponible dans la zone APAC (centre de données australien). Disponibilité effective : 30 juin 2020

L’interface de Journey Orchestration est disponible en japonais.

## Version du 1er trimestre - Mars 2020 {#q1-release---march-2020}

<table>
<thead>
<tr>
<th><strong>Améliorations du mode test</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Les améliorations suivantes ont été apportées au mode test :</p>
<ul>
<li>Lorsqu’un parcours utilise plusieurs événements, vous pouvez maintenant les déclencher séparément depuis une liste déroulante dans l’écran <strong>Configuration d’événement</strong> du mode test. <a href="../building-journeys/testing-the-journey.md#firing_events">En savoir plus</a></p></li>
<li><p>Lorsqu’une ou plusieurs activités d’<strong>attente</strong> sont utilisées dans un parcours, vous pouvez maintenant définir la durée de chacune d’entre elles en mode test. La valeur par défaut est de 10 secondes. Vous pouvez la modifier à l’aide du paramètre <strong>Temps d’attente en test</strong>, dans le coin inférieur gauche. <a href="../building-journeys/testing-the-journey.md">En savoir plus</a></p><img src="../assets/rn-test.png"/>
</li>
<li>En cas d’erreur lors de l’appel d’un système tiers (source de données ou action), le code d’erreur et la réponse d’erreur s’affichent maintenant dans les <strong>journaux de test</strong>. <a href="../building-journeys/testing-the-journey.md#viewing_logs">En savoir plus</a>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Gestion centralisée des fuseaux horaires</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>La gestion des fuseaux horaires est maintenant centralisée dans le panneau des propriétés du parcours. Deux paramètres ont été ajoutés aux propriétés du parcours :</p>
<img src="../assets/rn-timezone.png"/>
<ul>
<li>La liste déroulante <strong>Fuseau horaire</strong> vous permet de sélectionner un fuseau horaire spécifique. Par défaut, le fuseau horaire du navigateur est utilisé. </li>
<li>La case à cocher <strong>Fuseau horaire du profil</strong> vous permet d’utiliser le fuseau horaire du profil Adobe Experience Platform de la personne qui rejoint le parcours, le cas échéant. Si ce fuseau horaire n’est pas disponible, le fuseau horaire défini dans la liste déroulante est utilisé. Cette fonctionnalité n’est pas compatible avec les parcours utilisant des événements qui n’ont pas d’espace de noms.</li>
</ul>
<p>Pour plus d’informations, consultez les sections <a href="../building-journeys/changing-properties.md#timezone">Modification des propriétés</a> et <a href="../building-journeys/timezone-management.md">Gestion des fuseaux horaires</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Améliorations du concepteur de parcours</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>La <strong>palette</strong> des parcours, dans la partie gauche du concepteur de parcours, a été améliorée :</p>
<ul>
<li>Une nouvelle icône, en regard de la barre <strong>Recherche</strong>, permet de masquer ou d’afficher les éléments indisponibles dans la palette, par exemple les événements qui utilisent un espace de noms différent de ceux utilisés dans votre parcours. Par défaut, les éléments non disponibles sont masqués.</li>
<li>Lors de l’utilisation du champ <strong>Recherche</strong>, le nombre de résultats s’affiche maintenant pour chaque catégorie d’activité de la zone de travail.</li>
<li>La navigation entre les différentes catégories d’activité a été améliorée.</li>
</ul>
<p>Dans le concepteur de parcours, vous pouvez maintenant vérifier que vous accédez à la dernière version d’un parcours. Cette information s’affiche en regard du numéro de version.</p>
<p>Dans la <strong>zone de travail</strong> des parcours, un message d’avertissement s’affiche maintenant lorsque deux activités sont déconnectées.</p>
<img src="../assets/rn-canvas.png"/>
<p>Pour plus d’informations, consultez la <a href="../building-journeys/using-the-journey-designer.md">documentation détaillée</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Aide contextuelle</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Une aide contextuelle est maintenant disponible dans les différents écrans des listes Journey Orchestration (parcours, événements, actions et sources de données). Vous pouvez ainsi afficher une description rapide de la fonctionnalité actuelle et accéder aux articles et vidéos connexes.</p>
<p>Pour afficher l’aide contextuelle, cliquez sur l’icône <img src="../assets/icon-context.png"/> dans le coin supérieur droit de l’écran. </p>
<img src="../assets/rn-context.png"/>
</td>
</tr>
</tbody>
</table>

**Autres améliorations**

* Outre les États-Unis, Journey Orchestration est maintenant disponible dans les pays de la zone **EMEA**. L’application et la documentation sont disponibles en français et en allemand.

* Le portail Experience League est maintenant intégré dans le produit. Cette intégration simplifie l’accès au contenu associé et vous permet de tirer le meilleur parti d’Experience Cloud. Vous pouvez accéder directement à la documentation de Journey Orchestration en bas de l’onglet Aide. De plus, vous pouvez cliquer sur Aide > Commentaires pour signaler des problèmes ou partager vos idées avec Adobe.

* Le raccourci clavier **C**, qui vous permet de créer un élément, est maintenant disponible dans tous les écrans de liste : parcours, sources de données, actions et événements. [En savoir plus](../about/user-interface.md#section_ksq_zr1_ffb)

* Vous pouvez maintenant **supprimer** les parcours arrêtés. Les rapports associés à ces parcours supprimés ne seront pas disponibles.

* Lorsque vous parcourez les **champs Adobe Experience Platform** (format XDM), le nom d’affichage s’affiche en plus du nom du champ. Ces informations sont récupérées à partir de la définition du schéma dans le modèle de données d’expérience. Lorsqu’il est disponible, l’autre nom d’affichage s’affiche. Cette description conviviale, particulièrement utile dans le cas des champs eVar, vous permet d’identifier vos champs plus facilement. [En savoir plus](../about/user-interface.md#friendly-names-display)

## Version GA - Décembre 2019 {#ga-release---december-2019}

Journey Orchestration est désormais en version GA.

Créez des cas d’utilisation d’orchestration en temps réel à l’aide de données contextuelles stockées dans des événements ou des sources de données.

Journey Orchestration permet une orchestration en temps réel et s’appuie sur les données contextuelles issues d’événements, les informations provenant d’Adobe Experience Platform ou les données issues de services d’API tiers. L’application détermine, dans les flux à plusieurs étapes appelés parcours, les meilleures actions spécifiques au client ou à la cliente, en fonction de son profil et de ses comportements. Elles consistent à conjuguer une synchronisation optimale et un type d’action, comme l’envoi d’une notification push à l’aide des fonctionnalités de messages transactionnels d’Adobe Campaign Standard (nécessite Adobe Campaign Standard), ou d’une notification d’un système tiers. Ces décisions sont prises en fonction de scores Sensei et de règles.

[En savoir plus](../action/working-with-adobe-campaign.md) sur Journey Orchestration.
