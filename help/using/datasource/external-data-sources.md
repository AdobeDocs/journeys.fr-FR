---
title: 'Sources de données externes '
description: 'Découvrez comment configurer des sources de données externes '
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



# Sources de données externes {#concept_t2s_kqt_52b}

Les sources de données externes vous permettent de définir une connexion à des systèmes tiers, par exemple si vous utilisez un système de réservation d&#39;hôtel pour vérifier si la personne a enregistré une chambre. Contrairement à la source de données de la plateforme d’expérience intégrée, vous pouvez créer autant de sources de données externes que nécessaire.

Les API REST utilisant POST ou GET et renvoyant JSON sont prises en charge. Clé d’API, modes d’authentification de base et d’authentification personnalisée sont pris en charge.

Prenons l&#39;exemple d&#39;un service API météorologique que je veux utiliser pour personnaliser les comportements de mon voyage en fonction des données météorologiques en temps réel.

Voici deux exemples d’appel d’API :

* _https://api.adobeweather.org/weather?city=London,uk&amp;appid=1234_
* _https://api.adobeweather.org/weather?lat=35&amp;lon=139&amp;appid=1234_

L’appel est composé d’une URL principale (_https://api.adobeweather.org/weather_), de deux ensembles de paramètres (&quot;ville&quot; pour la ville et &quot;lat/long&quot; pour la latitude et la longitude) et de la clé API (appid).

Voici les étapes principales pour créer et configurer une nouvelle source de données externe :

1. Dans la liste des sources de données, cliquez sur **[!UICONTROL Ajouter]**pour créer une source de données externe.

   ![](../assets/journey25.png)

   Le volet de configuration de la source de données s’ouvre alors sur le côté droit de l’écran.

   ![](../assets/journey26.png)

1. Entrez un nom pour votre source de données.

   >[!NOTE]
   >
   >N’utilisez pas d’espaces ni de caractères spéciaux. N’utilisez pas plus de 30 caractères.

1. Ajoutez une description à votre source de données. Cette étape est facultative.
1. Ajoutez l’URL du service externe. Dans notre exemple : _https://api.adobeweather.org/weather_.

   >[!CAUTION]
   >
   >Nous vous recommandons vivement d’utiliser HTTPS pour des raisons de sécurité. Notez également que nous n’autorisons pas l’utilisation d’adresses Adobe qui ne sont pas accessibles au public et d’adresses IP.

   ![](../assets/journey27.png)

1. Configurez l’authentification en fonction de la configuration du service externe : **[!UICONTROL Aucune clé d’authentification]**,**[!UICONTROL  de base]**, **[!UICONTROL personnalisée]**ou**[!UICONTROL  API. ]** Pour plus d’informations sur le mode d’authentification personnalisé, voir [](../datasource/external-data-sources.md#section_wjp_nl5_nhb). Dans notre exemple, nous choisissons :


   * **[!UICONTROL Type]**: &quot;Clé API&quot;
   * **[!UICONTROL Valeur]**: &quot;1234&quot; (valeur de la clé d’API)
   * **[!UICONTROL Nom]**: &quot;appid&quot; (il s’agit du nom du paramètre de clé API)
   * **[!UICONTROL Emplacement]**: &quot;Paramètre de requête&quot; (la clé API se trouve dans l’URL)
   ![](../assets/journey28.png)

1. Ajoutez un nouveau groupe de champs pour chaque jeu de paramètres d’API en cliquant sur **[!UICONTROL Ajouter un nouveau groupe]**de champs. N’utilisez pas d’espaces ni de caractères spéciaux dans le nom du groupe de champs. Dans notre exemple, nous devons créer deux groupes de champs, un pour chaque ensemble de paramètres (ville et long/long).

Pour le jeu de paramètres &quot;long/long&quot;, nous créons un groupe de champs avec les informations suivantes :

* **[!UICONTROL Utilisé dans]**: affiche le nombre de voyages qui utilisent un groupe de champs. Vous pouvez cliquer sur l&#39;icône**[!UICONTROL  Afficher les voyages]** pour afficher la liste des voyages utilisant ce groupe de champs.
* **[!UICONTROL Méthode]**: sélectionnez la méthode POST ou GET. Dans notre cas, nous choisissons la méthode GET.
* **[!UICONTROL Durée]**du cache : dans notre cas, nous voulons que la météo soit mise en cache pendant 10 minutes.
* **[!UICONTROL Charge utile]**de réponse : cliquez dans le champ**[!UICONTROL  Charge]** utile et collez un exemple de charge utile renvoyée par l’appel. Par exemple, nous avons utilisé une charge utile trouvée sur un site Web de l’API météorologique. Vérifiez que les types de champ sont corrects. Chaque fois que l’API est appelée, le système récupère tous les champs inclus dans l’exemple de charge utile. Notez que vous pouvez cliquer sur **[!UICONTROL Coller une nouvelle charge]**si vous souhaitez modifier la charge actuellement transmise.
* **[!UICONTROL Valeurs]**dynamiques : entrez les différents paramètres séparés par une virgule, &quot;long,lat&quot; dans notre exemple. Les valeurs des paramètres dépendant du contexte d’exécution, elles seront définies dans les voyages. Voir la section[](../expression/expressionadvanced.md).
* **[!UICONTROL Charge utile]**envoyée : ce champ n&#39; apparaît pas dans notre exemple. Elle n’est disponible que si vous sélectionnez la méthode POST. Collez la charge qui sera envoyée au système tiers.

Dans le cas d’un appel GET nécessitant un ou plusieurs paramètres, vous saisissez le ou les paramètres dans le champ **[!UICONTROL Paramètres]**et ils sont automatiquement ajoutés à la fin de l’appel. En cas d’appel POST, vous devez effectuer les opérations suivantes :

* répertorie les paramètres à transmettre au moment de l’appel dans le champ **[!UICONTROL Paramètre]**(dans l’exemple ci-dessous : &quot;identifier&quot;).
* spécifiez-les également avec la même syntaxe dans le corps de la charge utile envoyée. Pour ce faire, vous devez ajouter : &quot;param&quot; : &quot;nom de votre paramètre&quot; (dans l’exemple ci-dessous : &quot;identifier&quot;). Suivez la syntaxe ci-dessous :

   ```
   {“id”:{“param”:“identifier”}}
   ```

![](../assets/journey29.png)

Cliquez sur **[!UICONTROL Enregistrer]**.

La source de données est maintenant configurée et prête à être utilisée dans vos voyages, par exemple dans vos conditions ou pour personnaliser un courrier électronique. Si la température est supérieure à 30 °C, vous pouvez décider d&#39;envoyer une communication spécifique.

## Mode d’authentification personnalisé{#section_wjp_nl5_nhb}

Ce mode d’authentification est utilisé pour l’authentification complexe, fréquemment utilisée pour appeler les protocoles d’encapsulage d’API tels que OAuth2, afin de récupérer un jeton d’accès à injecter dans la requête HTTP réelle pour l’action.

Lorsque vous configurez l’authentification personnalisée, vous pouvez cliquer sur le bouton ci-dessous pour vérifier si la charge utile d’authentification personnalisée est correctement configurée.

![](../assets/journey29-bis.png)

Si le test réussit, le bouton devient vert.

![](../assets/journey29-ter.png)

Avec cette authentification, l’exécution de l’action est un processus en deux étapes :

1. Appelez le point de fin pour générer le jeton d’accès.
1. Appelez l’API REST en injectant le jeton d’accès de la manière appropriée.

Cette authentification comporte deux parties.

Définition du point de fin à appeler pour générer le jeton d’accès :

* point de fin : URL à utiliser pour générer le point de fin
* méthode de la requête HTTP sur le point de fin (GET ou POST)
* en-têtes : paires clé/valeur à injecter en tant qu’en-têtes dans cet appel, le cas échéant
* body : décrit le corps de l’appel si la méthode est POST. Nous prenons en charge une structure corporelle limitée, définie dans bodyParams (paires clé/valeur). bodyType décrit le format et le codage du corps dans l’appel :
   * &#39;form&#39; : ce qui signifie que le type de contenu sera application/x-www-form-urlencoded (jeu de caractères UTF-8) et que les paires clé/valeur seront sérialisées comme suit : key1=value1&amp;key2=value2&amp;...
   * &#39;json&#39; : ce qui signifie que le type de contenu sera application/json (charset UTF-8) et que les paires clé-valeur seront sérialisées sous forme d’objet json tel quel : _{ &quot;key1&quot; : &quot;value1&quot;, &quot;key2&quot; : &quot;value2&quot;, ...}_

Définition de la manière dont le jeton d’accès doit être injecté dans la requête HTTP de l’action :

* authorizedType : définit comment le jeton d’accès généré doit être injecté dans l’appel HTTP de l’action. Les valeurs possibles sont les suivantes :

   * porteur : indique que le jeton d’accès doit être injecté dans l’en-tête d’autorisation, par exemple : _Autorisation : Porteur &lt;jeton d’accès>_
   * header : indique que le jeton d’accès doit être injecté en tant qu’en-tête, nom d’en-tête défini par la propriété tokenTarget. Par exemple, si la cible de jeton est myHeader, le jeton d’accès est injecté sous la forme d’un en-tête : _myHeader : &lt;jeton d’accès>_
   * queryParam : indique que le jeton d’accès doit être injecté en tant que queryParam, le nom du paramètre de requête défini par la propriété tokenTarget. Par exemple, si tokenTarget est myQueryParam, l’URL de l’appel d’action sera : _&lt;url>?myQueryParam=&lt;jeton d’accès>_

* tokenInResponse : indique comment extraire le jeton d’accès de l’appel d’authentification. Cette propriété peut être :
   * &#39;response&#39; : indique que la réponse HTTP est le jeton d’accès
   * un sélecteur dans un fichier json (en supposant que la réponse est un fichier json, nous ne prenons pas en charge d’autres formats, tels que XML). Le format de ce sélecteur est _json://&lt;chemin d’accès à la propriété du jeton d’accès>_. Par exemple, si la réponse de l’appel est : _{ &quot;access_token&quot; : &quot;theToken&quot;, &quot;timestamp&quot; : 12323445656}_, le jetonInResponse sera : _json : //access_token_

Le format de cette authentification est le suivant :

```
{
    "type": "customAuthorization",
    "authorizationType": "<value in 'bearer', 'header' or 'queryParam'>",
    (optional, mandatory if authorizationType is 'header' or 'queryParam') "tokenTarget": "<name of the header or queryParam if the authorizationType is 'header' or 'queryParam'>",
    "endpoint": "<URL of the authentication endpoint>",
    "method": "<HTTP method to call the authentication endpoint, in 'GET' or 'POST'>",
    (optional) "headers: {
        "<header name>": "<header value>",
        ...
    },
    (optional, mandatory if method is 'POST') "body": {
        "bodyType": "<'form'or 'json'>,
        "bodyParams": {
            "param1": value1,
            ...

        }
    },
    "tokenInResponse": "<'response' or json selector in format 'json://<field path to access token>'"
}
```
