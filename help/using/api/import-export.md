---
product: adobe campaign
solution: Journey Orchestration
title: Description de l’API d’import-export
description: En savoir plus sur l’API d’import-export.
products: journeys
translation-type: tm+mt
source-git-commit: 8da1d4a6c01279bf502c3ec39bdaba8fcc8e64f8
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 76%

---


# Utilisation de l’API Export-Import

Exportez une version de parcours et tous ses objets associés (parcours, événements, sources de données, groupes de champs, actions personnalisées) avec un seul appel API. La payload obtenue de l’export peut être utilisée pour importer facilement le parcours dans un autre environnement (instance ou sandbox).
Cette fonctionnalité permet de gérer vos parcours sur plusieurs instances ou pour plusieurs workflows d’environnements de test.


## Ressources

The Journey Orchestration Export-Import API is described within a Swagger file available [here](https://adobedocs.github.io/JourneyAPI/docs/).

Pour utiliser cette API avec votre instance Journey Orchestration, vous devez utiliser la console Adobe I/O. Vous pouvez y accéder selon les indications de la section [Prise en main d’Adobe Developer Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md), puis les différentes sections de cette page.

Pour tester et préparer votre intégration, une collection Postman est disponible [ici](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json).


## Flux d’export-import

Il est recommandé de suivre les étapes suivantes pour exporter et importer vos parcours entre les environnements :

1. Créez et paramétrez un parcours dans votre environnement de départ. [Plus d’informations ici](https://docs.adobe.com/content/help/fr-FR/journeys/using/building-journeys/about-journey-building/journey.html)
1. Vérifiez si la version du parcours ne comporte aucune erreur. [Plus d’informations ici](https://docs.adobe.com/content/help/fr-FR/journeys/using/building-journeys/testing-the-journey.html)
1. Appelez l’API **/list/journeys** pour récupérer l’UID du parcours et l’UID de votre dernière version de parcours. Si nécessaire, vous pouvez appeler **/journeys/`{uid}`/latest** pour trouver l’UID de votre dernière version de parcours.
1. Appelez l’API **d’export** avec vos paramètres d’environnement de départ (orgID et sandboxName).
1. Ouvrez la payload de retour, puis vérifiez les éléments suivants :
   * Si le parcours exporté contient des **informations d’identification spécifiques**, vous devez les remplacer par celles correspondant au nouvel environnement.
   * Si le parcours exporté contient des **événements** qui pointent vers un **schéma XDM**, vous devez mettre à jour manuellement la référence à l’ID de schéma avec l’ID de schéma du nouvel environnement dans le nœud xdmEntity si les valeurs d’ID sont différentes. Cette mise à jour doit être effectuée pour chaque événement. [Plus d’informations ici](https://docs.adobe.com/content/help/fr-FR/journeys/using/events-journeys/experience-event-schema.html)
   * Si le parcours contient des actions push, email et SMS, vous devrez peut-être mettre à jour le nom du modèle ou de l’application mobile si le nom figurant dans l’environnement cible est différent de celui de votre environnement de départ.
1. Call the **Import** API with your target environment parameters (orgID and sandboxName). Notez que vous pouvez appeler l’API d’import autant de fois que vous le souhaitez. L’UUID et le nom de chaque objet contenu dans le voyage sont générés chaque fois que vous appelez l’API d’importation.
1. Une fois le voyage importé, vous pouvez le publier dans l’application Journey Orchestration. More info [here](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/publishing-the-journey.html)


## Authentification

### Configuration de l’accès aux API

La configuration de l’accès aux API Journey Orchestration est effectuée comme suit. Chacune de ces étapes est détaillée dans la [documentation Adobe I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Pour gérer les certificats dans Adobe I/O, assurez-vous de disposer des droits d’<b>administrateur système</b> sur l’organisation ou d’un [compte de développeur](https://helpx.adobe.com/fr/enterprise/using/manage-developers.html) dans Admin Console.

1. **Vérifiez que vous disposez d’un certificat numérique**, ou créez-en un si nécessaire. Les clés publique et privée fournies avec le certificat sont nécessaires dans les étapes suivantes.
1. **Créez une nouvelle intégration avec [!DNL Journey Orchestration] Service** dans Adobe I/O et configurez-la. L’accès au profil de produit est nécessaire pour Journey Orchestration et Adobe Experience Platform. Vos informations d’identification seront alors générées (clé d’API, secret client...).
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



## Description de l’API Export-Import

Cette API vous permet d’exporter une version de voyage identifiée par son identifiant d’utilisateur et tous les objets associés (voyage, événements, sources de données, groupes de champs, actions personnalisées) par son identifiant d’utilisateur.
La payload obtenue peut être utilisée pour importer la version du parcours dans un autre environnement (sandbox ou instance).

| Méthodologie | Chemin | Description |
|---|---|---|
| `[POST]` | /journeyVersions/import | Permet d’importer un contenu de version de parcours obtenu d’un export de version de parcours |
| `[GET]` | /journeyVersions/`{uid}`/export | Permet d’exporter une version de parcours |
| `[GET]` | /journeys/`{uid}`/latest | Permet d’obtenir la dernière version d’un parcours |
| `[POST]` | /list/journeys | Permet de répertorier les métadonnées des parcours et leurs versions de parcours |


### Caractéristiques de l’export et barrières de sécurité

* Le parcours doit être valide avant l’export.

* Les informations d’identification ne sont pas exportées et un espace réservé (INSERT_SECRET_HERE) est inséré dans la charge utile de réponse.
Après l’appel d’exportation, vous devez insérer manuellement les nouvelles informations d’identification (correspondant à l’environnement de cible) avant d’importer la charge utile dans l’environnement de cible.

* Les objets suivants sont exportés, mais ils ne seront jamais importés dans l’environnement de cible. Il s&#39;agit de ressources système gérées automatiquement par le Journey Orchestration. Vous n&#39;avez pas besoin de remplacer &quot;INSERT_SECRET_HERE&quot;.
   * **DataProviders**:  &quot;Fournisseur de données Adobe Campaign Standard&quot; (acsDataProvider) et &quot;Experience Platform&quot; (acppsDataProvider)
   * **Groupes** de champs (dataEntities) : &quot;ProfileFieldGroup&quot; (acppsDataPack)



### Caractéristiques de l’import

* Au cours de l’importation, les objets de voyage sont créés avec un nouvel identifiant utilisateur et un nouveau nom pour garantir l’unicité dans l’environnement de cible (instance ou sandbox).

* Si la payload d’import contient des espaces réservés secrets, une erreur est générée. Vous devez remplacer les informations d’identification avant l’appel POST pour importer le parcours.

## Avertissement et erreurs

Les erreurs potentielles sont les suivantes :

* Au **moment de l’export**, si la version du parcours n’est pas valide : erreur 500

* Au **moment de l’import**, si la payload n’est pas valide après modification ou si les informations d’identification ne sont pas correctement définies dans la payload : erreur 400

* Après l’étape d’importation, si l’ID de Schéma XDM pour vos événements n’est pas valide dans l’environnement de cible, une erreur s’affiche dans l’application Journey Orchestration. Dans ce cas, il ne sera pas possible de publier le voyage.