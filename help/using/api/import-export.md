---
title: Importer la description de l’API d’exportation
description: En savoir plus sur l’API d’exportation d’importation.
contentOwner: sauviat
products: journeys
audience: audiences
content-type: reference
topic-tags: journeys
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '1103'
ht-degree: 35%

---


# Utilisation de l’API d’importation d’exportation

Exportez une version de voyage et tous ses objets associés (voyage, événements, sources de données, groupes de champs, actions personnalisées) avec un seul appel d’API. La charge utile résultante de l&#39;exportation peut être utilisée pour importer facilement le voyage dans un autre environnement (instance ou sandbox).
Cette fonctionnalité vous permet de gérer vos voyages sur plusieurs instances ou pour plusieurs environnements de test.


## Ressources

L’API d’exportation d’importation de Journey Orchestration est décrite dans un fichier Swagger disponible [ici](https://adobedocs.github.io/JourneyAPI/docs/).

Pour utiliser cette API avec votre instance de Journey Orchestration, vous devez utiliser la console AdobeI/O. Vous pouvez y accéder selon les indications de la section [Prise en main d’Adobe Developer Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md), puis les différentes sections de cette page.

Pour tester et préparer votre intégration, une collection Postman est disponible [ici](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json).


## Flux d’exportation et d’importation

Nous vous recommandons de suivre les étapes suivantes pour exporter et importer vos voyages entre les environnements :

1. Créez et paramétrez un voyage dans votre environnement de début. [Plus d&#39;infos ici](https://docs.adobe.com/content/help/fr-FR/journeys/using/building-journeys/about-journey-building/journey.html)
1. Vérifiez si la version du voyage ne comporte aucune erreur. [Plus d&#39;infos ici](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/testing-the-journey.html)
1. Appelez **/liste/Voyages** API pour récupérer le parcours UID et l&#39;UID de votre dernière version de voyage. Si nécessaire, vous pouvez appeler **/Voyages/`{uid}`/Dernière** pour trouver l&#39;UID de votre dernière version de voyage.
1. Appelez l’API **d’exportation** avec vos paramètres d’environnement d’début (orgID et sandboxName).
1. Ouvrez la charge utile de retour, puis vérifiez les éléments suivants :
   * Si votre voyage exporté contient des informations d’identification **** spécifiques, vous devez remplacer ces informations d’identification par celles correspondant au nouvel environnement.
   * Si votre voyage exporté contient **des événements** qui pointent vers un schéma **** XDM, vous devez mettre à jour manuellement la référence d&#39;ID de schéma avec l&#39;ID de schéma du nouvel environnement dans le noeud xdmEntity si les valeurs d&#39;ID sont différentes. Cette mise à jour doit être effectuée pour chaque événement. [Plus d&#39;infos ici](https://docs.adobe.com/content/help/en/journeys/using/events-journeys/experience-event-schema.html)
   * Si votre voyage contient des messages électroniques, des messages sms ou des actions Push, vous devrez peut-être mettre à jour le nom du modèle ou le nom de mobileApp si le nom figurant dans l’environnement de cible est différent de celui de votre environnement de début.
1. Appelez l’API **d’importation** avec votre environnement de cible. Notez que vous pouvez appeler l’API d’importation autant de fois que vous le souhaitez. L’UUID et le nom de chaque noeud contenu dans le parcours sont générés chaque fois que vous appelez l’API d’importation.
1. Une fois le voyage importé, vous pouvez le publier dans le nouveau sandbox ou environnement.


## Authentification

### Configuration de l’accès aux API

L’accès à l’API du Journey Orchestration est configuré par les étapes ci-dessous. Chacune de ces étapes est détaillée dans la [documentation Adobe I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Pour gérer les certificats dans Adobe I/O, assurez-vous de disposer des droits d’<b>administrateur système</b> sur l’organisation ou d’un [compte de développeur](https://helpx.adobe.com/fr/enterprise/using/manage-developers.html) dans Admin Console.

1. **Vérifiez que vous disposez d’un certificat numérique**, ou créez-en un si nécessaire. Les clés publique et privée fournies avec le certificat sont nécessaires dans les étapes suivantes.
1. **Créez une nouvelle intégration avec[!DNL Journey Orchestration]Service** dans Adobe I/O et configurez-la. L&#39;accès au profil du produit est nécessaire pour le Journey Orchestration et le Adobe Experience Platform. Vos informations d’identification seront alors générées (clé d’API, secret client...).
1. **Créez un jeton Web JSON (JWT)** à partir des informations d’identification précédemment générées, et signez-le avec votre clé privée. Le jeton JWT code toutes les informations d’identité et de sécurité dont Adobe a besoin pour vérifier votre identité et vous accorder l’accès à l’API. Cette étape est présentée dans cette [section](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Échangez votre jeton JWT pour un jeton d’accès** à l’aide d’une requête POST ou via l’interface de Developer Console. Ce jeton d’accès devra être utilisé dans chaque en-tête de vos requêtes d’API.

Pour établir une session d’API Adobe I/O de service à service sécurisée, chaque requête adressée à un service Adobe doit inclure les informations ci-dessous dans l’en-tête d’autorisation.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZATION>** : il s’agit de votre ORGANIZATION ID personnel, fourni par Adobe pour chacune de vos instances :

   * &lt;ORGANIZATION> : votre instance de production
   Pour obtenir votre valeur ORGANIZATION ID, contactez votre administrateur ou votre contact technique Adobe. Vous pouvez également la récupérer dans Adobe I/O lors de la création d’une nouvelle intégration, dans la liste des licences (voir la [documentation Adobe I/O](https://www.adobe.io/authentication.html)).

* **&lt;ACCESS_TOKEN>** : votre jeton d’accès personnel, récupéré lors de l’échange de votre JWT par le biais d’une requête POST.

* **&lt;API_KEY>** : votre clé d’API personnelle. Elle est fournie dans Adobe I/O après la création d’une nouvelle intégration avec [!DNL Journey Orchestration] Service.



## Exporter la description de l’API d’importation

Cette API vous permet d’exporter une version de voyage et tous les objets associés (parcours, événements, sources de données, groupes de champs, actions personnalisées) par son uid.
La charge utile résultante peut être utilisée pour importer la version du voyage dans un autre environnement (sandbox ou instance).

| Méthodologie | Chemin | Description |
|---|---|---|
| `[POST]` | /travelVersions/import | Importer un contenu de version de voyage résultant d’une exportation de version de voyage |
| `[GET]` | /travelVersions/`{uid}`/export | Exportation d’une version de voyage |
| `[GET]` | /journeys/`{uid}`/last | Obtenir la dernière version du voyage pour un voyage |
| `[POST]` | /liste/voyages | Liste des métadonnées des voyages et de leurs versions de parcours |


### Caractéristiques d&#39;exportation et garde-fous

* Les informations d’identification ne sont pas exportées et un espace réservé (INSERT_SECRET_HERE) est inséré.
Après l’exportation de la charge utile, vous devez insérer manuellement les nouvelles informations d’identification (correspondant à l’environnement de cible) avant d’importer la charge utile dans l’environnement de cible.

* Lorsque la source de données contient le paramètre **buildIn:true**, vous n’avez pas besoin de remplacer &quot;INSERT_SECRET_HERE&quot;. Il s&#39;agit d&#39;une source de données système automatiquement gérée par l&#39;environnement de voyage.

* Les objets suivants sont exportés, mais ils ne seront jamais importés dans l’environnement de cible :
   * **DataProviders**:  acsDataProvider et acppsDataProvider
   * **Groupes** de champs : acppsFieldGroup
   * **Actions** personnalisées : acsAction

* Le voyage doit être valide avant l&#39;exportation.

### Caractéristiques d&#39;importation

* Au cours de l’importation, les objets de voyage sont créés avec un nouvel identifiant UUID et un nouveau nom pour garantir l’unicité dans l’environnement de cible (instance ou sandbox).

* Si la charge utile d’importation contient des espaces réservés secrets, une erreur est générée. Vous devez remplacer les informations d’identification avant l’appel du POST pour importer le voyage.

## Avertissement et erreurs

Les erreurs potentielles sont les suivantes :

* Lors de l’ **exportation**, si la version du voyage n’est pas valide : erreur 500

* Au moment **de l’** importation, si la charge utile n’est pas valide après modification ou si les informations d’identification ne sont pas correctement définies dans la charge utile : erreur 400

* Après l’étape d’importation, si vous tentez de publier le voyage dans l’environnement de cible sans modifier l’identifiant de Schéma XDM pour vos événements, une erreur s’affiche.

