---
product: adobe campaign
title: Commencer avec les API de Journeys
description: En savoir plus sur les API de Journeys
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: a5dd3d23-c820-4ab7-bc6c-b1dcfe15022c
source-git-commit: 8f409fe6e37a3b80527d9a5514b066e539dcd9f3
workflow-type: ht
source-wordcount: '828'
ht-degree: 100%

---

# Commencer avec les API de Journeys

## À propos des API de plafonnement et de limitation

Lors de la configuration d’une source de données ou d’une action, vous établissez une connexion à un système afin de récupérer des informations supplémentaires à utiliser dans vos parcours ou pour envoyer des messages ou des appels API.

Les API de Journeys prennent en charge jusqu’à 5 000 événements par seconde, mais certains systèmes externes ou API peuvent ne pas avoir un débit équivalent. Pour éviter de surcharger ces systèmes, vous pouvez utiliser les API de **Plafonnement** et de **Limitation** pour limiter le nombre d’événements envoyés par seconde.

Chaque fois qu’un appel API est réalisé par Journeys, le moteur d’API est sollicité. Si la limite définie dans l’API est atteinte, deux scénarios peuvent se présenter selon l’API utilisée : avec l’API de plafonnement, l’appel est rejeté. Si vous utilisez l’API de limitation, l’appel est mis en file d’attente pendant 6 heures au maximum et traité dès que possible, dans l’ordre où il a été reçu.

Supposons, par exemple, que vous ayez défini une règle de plafonnement ou de limitation de 100 appels par seconde pour votre système externe. Votre système est appelé par une action personnalisée dans 10 parcours différents. Si un parcours reçoit 200 appels par seconde, il utilise les 100 emplacements disponibles et rejette ou met en file d’attente les 100 emplacements restants. Comme le taux maximum a été dépassé, il ne restera plus aucun emplacement pour les 9 autres parcours. Cette granularité permet de protéger le système externe contre la surcharge et la panne.

>[!IMPORTANT]
>
>Les **Règles de limitation** sont configurées au niveau de la sandbox, pour un point d’entrée spécifique (l’URL appelée), mais elles s’appliquent à tous les parcours de cette sandbox.
>
>Les **Règles de limitation** sont configurées dans les sandbox de production uniquement, pour un point d’entrée spécifique, mais elles s’appliquent à tous les parcours sur l’ensemble des sandbox. Une seule configuration de limitation est autorisée par organisation.

Pour plus d’informations sur l’utilisation des API, consultez les sections suivantes :

* [API de limitation](capping.md)
* [API de limitation](throttling.md)

Les deux API sont également décrites dans le fichier Swagger disponible [ici](https://adobedocs.github.io/JourneyAPI/docs/).

## Sources de données et capacité des actions personnalisées {#capacity}

Pour les **sources de données externes**, le nombre maximal d’appels par seconde est limité à 15. Si cette limite est dépassée, les appels suivants sont rejetés ou mis en file d’attente, selon l’API utilisée. Contactez Adobe si vous souhaitez augmenter cette limite pour les sources de données externes privées. Le point d’entrée sera alors placé dans la liste autorisée. Cette opération n’est pas possible pour les sources de données externes publiques. * [Découvrez comment configurer des sources de données](../datasource/about-data-sources.md).

>[!NOTE]
>
>Si une source de données utilise une authentification personnalisée avec un point d’entrée différent de celui utilisé pour la source de données, vous devez contacter Adobe pour inclure également ce point d’entrée dans la liste autorisée.

Pour les **actions personnalisées**, vous devez évaluer la capacité de votre API externe. Par exemple, si Journey Optimizer envoie 1 000 appels par seconde et que votre système ne peut prendre en charge que 100 appels par seconde, vous devez définir une configuration de plafonnement ou de limitation afin que votre système ne sature pas. [Découvrez comment configurer des actions](../action/action.md).

## Configuration de l&#39;accès aux API {#api}

Pour utiliser ces API avec votre instance [!DNL Journey Orchestration], vous devez utiliser la console Adobe I/O. La configuration de l’accès aux API [!DNL Journey Orchestration] est effectuée comme suit. Chacune de ces étapes est détaillée dans la [documentation Adobe I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Pour gérer les certificats dans Adobe I/O, assurez-vous de disposer des droits d’<b>administrateur système</b> sur l’organisation ou d’un [compte de développeur](https://helpx.adobe.com/fr/enterprise/using/manage-developers.html) dans Admin Console.

1. **Vérifiez que vous disposez d’un certificat numérique**, ou créez-en un si nécessaire. Les clés publique et privée fournies avec le certificat sont nécessaires dans les étapes suivantes.
1. **Créez une nouvelle intégration avec [!DNL Journey Orchestration] Service** dans Adobe I/O et configurez-la. L’accès au profil du produit est nécessaire pour [!DNL Journey Orchestration] et Adobe Experience Platform. Vos informations d’identification seront alors générées (clé d’API, secret client...).

>[!CAUTION]
>
>La méthode JWT de génération des jetons d’accès a été abandonnée. Toutes les nouvelles intégrations doivent être créées à l’aide de la [méthode d’authentification OAuth de serveur à serveur](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-authentication.html?lang=fr#select-oauth-server-to-server). Adobe vous recommande également de migrer vos intégrations existantes vers la méthode OAuth.
>
>Consultez attentivement les documents suivants :
>[Guide de migration de vos applications de JWT vers OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/),
>[Guide de mise en œuvre pour les nouvelles et les anciennes applications avec OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/),
>[Avantages de l’utilisation de la méthode d’identification OAuth de serveur à serveur](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/#why-oauth-server-to-server-credentials).

Pour établir une session d’API Adobe I/O de service à service sécurisée, chaque requête adressée à un service Adobe doit inclure les informations ci-dessous dans l’en-tête d’autorisation.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZATION>** : il s’agit de votre ORGANIZATION ID personnel, fourni par Adobe pour chacune de vos instances. Pour obtenir votre valeur ORGANIZATION ID, contactez votre administrateur ou votre contact technique Adobe. Vous pouvez également la récupérer dans Adobe I/O lors de la création d’une nouvelle intégration, dans la liste des licences (voir la <a href="https://www.adobe.io/authentication.html">documentation Adobe I/O</a>).

* **&lt;ACCESS_TOKEN>** : votre jeton d’accès personnel.

* **&lt;API_KEY>** : votre clé d’API personnelle. Elle est fournie dans Adobe I/O après la création d’une nouvelle intégration avec [!DNL Journey Orchestration] Service.
