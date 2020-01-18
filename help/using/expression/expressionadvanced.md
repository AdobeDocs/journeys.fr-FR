---
title: A propos de l’éditeur d’expression avancé
description: Découvrez comment créer des expressions avancées
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


# A propos de l’éditeur d’expression avancé {#concept_uyj_trt_52b}

L’éditeur d’expression avancé vous permet de créer des expressions avancées dans divers écrans de l’interface, par exemple lors de la définition d’une condition de source de données.
Il est également disponible chaque fois que vous avez besoin de définir des paramètres d’action qui nécessitent des manipulations de données spécifiques. Vous pouvez exploiter les données provenant des événements ou des informations supplémentaires extraites de la source de données. Dans un voyage, la liste affichée des champs d’événement est contextuelle et varie selon le ou les événements ajoutés au voyage.

L’éditeur d’expression avancé propose un ensemble de fonctions et d’opérateurs intégrés qui vous permettent de manipuler des valeurs et de définir une expression qui correspond à vos besoins. L’éditeur d’expression avancé vous permet également de définir les valeurs du paramètre de source de données externe, de manipuler les champs de mappage et les collections, comme les événements d’expérience.

![](../assets/journey65.png)

_Interface de l’éditeur d’expression avancé_

L’éditeur d’expression avancé peut être utilisé pour :

* créer des conditions [](../building-journeys/condition-activity.md#about_condition) avancées sur les sources de données et les informations sur les événements
* définir des [fuseaux](../building-journeys/timezone-management.md) horaires personnalisés dans les conditions de date, des activités d’attente de date fixe, des activités d’attente personnalisées
* définir des activités [d’attente personnalisées](../building-journeys/wait-activity.md#custom)
* définir le mappage des paramètres d’action

Lorsque cela est possible, vous pouvez basculer entre les deux modes à l’aide du bouton Mode ****avancé / Mode**** simple. Le mode simple est décrit [ici](../building-journeys/condition-activity.md#about_condition).

>[!NOTE]
>
>Les conditions peuvent être définies dans l’éditeur d’expression simple ou avancé. Ils renvoient toujours un type booléen.
>
>Les paramètres d’action peuvent être définis en sélectionnant des champs ou via l’éditeur d’expression avancé. Ils renvoient un type de données spécifique en fonction de leur expression.

## Accès à l’éditeur d’expression avancé {#section_fdz_4nj_cjb}

Vous pouvez accéder à l’éditeur d’expression avancé de différentes manières :

* Lorsque vous créez une condition de source de données, vous pouvez accéder à l’éditeur avancé en cliquant sur le mode ****avancé.

   ![](../assets/journeyuc2_33.png)

* Lorsque vous créez un fuseau horaire personnalisé ou un minuteur personnalisé, l’éditeur avancé s’affiche directement.
* Lorsque vous mappez le paramètre d’action, cliquez sur le mode ****avancé.

## Découverte de l&#39;interface{#section_otq_tnj_cjb}

Cet écran vous permet d’écrire manuellement votre expression.

![](../assets/journey70.png)

Dans la partie gauche de l’écran s’affichent les champs et fonctions disponibles :

* **[!UICONTROL Evénements]**: sélectionnez l’un des champs reçus de l’événement entrant. La liste affichée des champs d’événement est contextuelle et varie selon le ou les événements ajoutés au parcours.
* **[!UICONTROL Sources]**de données : faites votre choix dans la liste des champs disponibles à partir des groupes de champs de vos sources de données.
* **[!UICONTROL Fonctions]**: faites votre choix dans la liste des fonctions intégrées permettant d’effectuer un filtrage complexe. Les fonctions sont organisées par catégories.

![](../assets/journey65.png)

Un mécanisme d’auto-achèvement affiche des suggestions contextuelles.

![](../assets/journey68.png)

Un mécanisme de validation de syntaxe vérifie l’intégrité du code. Les erreurs s’affichent au-dessus de l’éditeur.

![](../assets/journey69.png)

**Besoin de paramètres lors de la création de conditions à l’aide de l’éditeur d’expression avancé**

Si vous sélectionnez un champ d’une source de données externe nécessitant l’appel d’un paramètre (voir [](../datasource/external-data-sources.md). Par exemple, dans une source de données météorologiques, un paramètre fréquemment utilisé est &quot;ville&quot;. Par conséquent, vous devez sélectionner l’emplacement où vous souhaitez obtenir ce paramètre de ville. Des fonctions peuvent également être appliquées aux paramètres pour effectuer des modifications de format ou des concaténations.

![](../assets/journeyuc2_19.png)

Dans les cas d’utilisation plus complexes, si vous souhaitez inclure les paramètres de la source de données dans l’expression principale, vous pouvez définir leurs valeurs à l’aide du mot-clé &quot;params&quot;. Voir [cette page](../expression/field-references.md).
