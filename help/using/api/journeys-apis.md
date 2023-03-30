---
product: adobe campaign
title: Prise en main des API parcours
description: En savoir plus sur les API parcours
products: journeys
feature: Journeys
role: User
level: Intermediate
source-git-commit: 137637a753ba44cc4f8e397b77c3fc076ec3de3f
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 47%

---

# Prise en main des API parcours

## À propos des API de limitation et de limitation

Lors de la configuration d’une source de données ou d’une action, vous établissez une connexion à un système afin de récupérer des informations supplémentaires à utiliser dans vos parcours ou d’envoyer des messages ou des appels d’API.

Les API Parcours prennent en charge jusqu’à 5 000 événements par seconde, mais certains systèmes ou API externes peuvent ne pas avoir un débit équivalent. Pour éviter de surcharger ces systèmes, vous pouvez utiliser la variable **Limitation** et **Ralentissement** API pour limiter le nombre d’événements envoyés par seconde.

Chaque fois qu’un appel API est effectué par parcours, il passe par le moteur d’API. Si la limite définie dans l’API est atteinte, l’appel est rejeté si vous utilisez l’API de limitation, ou mis en file d’attente et traité le plus tôt possible dans l’ordre dans lequel ils ont été reçus si vous utilisez l’API de limitation.

Supposons, par exemple, que vous ayez défini une règle de limitation ou de limitation de 100 appels par seconde pour votre système externe. Votre système est appelé par une action personnalisée dans 10 parcours différents. Si un parcours reçoit 200 appels par seconde, il utilise les 100 emplacements disponibles et ignore ou met en file d’attente les 100 emplacements restants. Comme le taux maximum a été dépassé, il ne restera plus aucun emplacement pour les 9 autres parcours. Cette granularité permet de protéger le système externe contre la surcharge et la panne.

>[!IMPORTANT]
>
>**Règles de limitation** sont configurés au niveau de l’environnement de test, pour un point de terminaison spécifique (l’URL appelée), mais globaux pour tous les parcours de cet environnement de test.
>
>**Règles de limitation** sont configurés uniquement sur les environnements de test de production, pour un point de terminaison spécifique, mais globaux pour tous les parcours de tous les environnements de test. Vous ne pouvez avoir qu’une seule configuration de limitation par organisation.

Pour plus d’informations sur l’utilisation de ces API, reportez-vous aux sections suivantes :

* [API de limitation](capping.md)
* [API de limitation](throttling.md)

Les deux API sont également décrites dans un fichier Swagger disponible. [here](https://adobedocs.github.io/JourneyAPI/docs/).

## Sources de données et capacité des actions personnalisées {#capacity}

Pour **sources de données externes**, le nombre maximal d’appels par seconde est limité à 15. Si cette limite est dépassée, tout appel supplémentaire est ignoré ou mis en file d’attente selon l’API utilisée. Il est possible d’augmenter cette limite pour les sources de données externes privées en contactant Adobe pour inclure le point de terminaison dans la liste autorisée de données, mais il ne s’agit pas d’une option pour les sources de données externes publiques. * [Découvrez comment configurer des sources de données](../datasource/about-data-sources.md).

>[!NOTE]
>
>Si une source de données utilise une authentification personnalisée avec un point d’entrée différent de celui utilisé pour la source de données, vous devez contacter Adobe pour inclure également ce point d’entrée dans la liste autorisée.

Pour **actions personnalisées**, vous devez évaluer la capacité de votre API externe. Par exemple, si Journey Optimizer envoie 1 000 appels par seconde et que votre système ne peut prendre en charge que 100 appels par seconde, vous devez définir une configuration de limitation ou de ralentissement afin que votre système ne se satue pas. [Découvrez comment configurer des actions](../action/action.md)

## Configuration de l&#39;accès aux API {#api}

Pour utiliser ces API avec votre [!DNL Journey Orchestration] vous devez utiliser la console Adobe I/O. La configuration de l’accès aux API [!DNL Journey Orchestration] est effectuée comme suit. Chacune de ces étapes est détaillée dans la [documentation Adobe I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Pour gérer les certificats dans Adobe I/O, assurez-vous de disposer des droits d’<b>administrateur système</b> sur l’organisation ou d’un [compte de développeur](https://helpx.adobe.com/fr/enterprise/using/manage-developers.html) dans Admin Console.

1. **Vérifiez que vous disposez d’un certificat numérique**, ou créez-en un si nécessaire. Les clés publique et privée fournies avec le certificat sont nécessaires dans les étapes suivantes.
1. **Créez une nouvelle intégration avec [!DNL Journey Orchestration] Service** dans Adobe I/O et configurez-la. L’accès au profil du produit est nécessaire pour [!DNL Journey Orchestration] et Adobe Experience Platform. Vos informations d’identification seront alors générées (clé d’API, secret client...).
1. **Créez un jeton Web JSON (JWT)** à partir des informations d’identification précédemment générées, et signez-le avec votre clé privée. Le jeton JWT code toutes les informations d’identité et de sécurité dont Adobe a besoin pour vérifier votre identité et vous accorder l’accès à l’API. Cette étape est présentée dans cette [section](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Échangez votre jeton JWT pour un jeton d’accès** à l’aide d’une requête POST ou via l’interface de Developer Console. Ce jeton d’accès devra être utilisé dans chaque en-tête de vos requêtes d’API.

Pour établir une session d’API Adobe I/O de service à service sécurisée, chaque requête adressée à un service Adobe doit inclure les informations ci-dessous dans l’en-tête d’autorisation.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**: Il s’agit de votre ORGANIZATION ID personnel, fourni par Adobe pour chacune de vos instances. Pour obtenir votre valeur ORGANIZATION ID, contactez votre administrateur ou votre contact technique Adobe. Vous pouvez également la récupérer dans Adobe I/O lors de la création d’une nouvelle intégration, dans la liste des licences (voir la <a href="https://www.adobe.io/authentication.html">documentation Adobe I/O</a>).

* **&lt;ACCESS_TOKEN>** : votre jeton d’accès personnel, récupéré lors de l’échange de votre JWT par le biais d’une requête POST.

* **&lt;API_KEY>** : votre clé d’API personnelle. Elle est fournie dans Adobe I/O après la création d’une nouvelle intégration avec [!DNL Journey Orchestration] Service.
