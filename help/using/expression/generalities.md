---
title: Généralités
description: En savoir plus sur les généralités d’expression avancées
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
source-git-commit: 239efa9592b011c70e2fc331df8f33820301253d

---


# Généralités {#concept_rcy_qj5_dgb}

## Parenthèses et priorité d’expression{#section_edf_fks_bgb}

Les parenthèses peuvent être utilisées pour rendre une expression complexe plus lisible. _(&lt;expression>)_ est l’équivalent de _&lt;expression>_. Les parenthèses peuvent également être utilisées pour définir l’ordre d’évaluation et l’associativité.

Les expressions seront évaluées de gauche à droite. L’associativité des opérateurs arithmétiques doit être appliquée : les multiplications et les divisions sont prioritaires sur les ajouts et les soustractions. Pour imposer un ordre spécifique, des parenthèses doivent être ajoutées pour délimiter les opérations. Par exemple :

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| Expression | Évaluation |
|--- |--- |
| `4 + 2 * 10` | <ul><li>&#39;*&#39; a la priorité sur &#39;+&#39; : 2 * 10 est évalué → 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>Les parenthèses modifient la priorité : (4 + 2) est évaluée → 6</li><li> 6 * 10 → 60</li></ul> |

## Respect de la casse{#section_lrb_xh5_dgb}

Voici les différentes règles de respect de la casse :

* Tous les opérateurs (et, ou, etc.) doit être en minuscules. Par exemple, _`<expression1>`et`<expression2>`_est une expression valide, contrairement à l’expression_`<expression1>` ET `<expression2>`_ .
* Tous les noms de fonction sont sensibles à la casse. Par exemple, _getBestSendTime()_ est valide, contrairement à la fonction _GETBESTSENDTIME()_ .
* Les références aux champs et les valeurs constantes sont sensibles à la casse : ils ne sont pas des éléments intégrés du langage (par opposition aux opérateurs et aux fonctions), ils sont créés par l’utilisateur final.

## Type d’expression renvoyé{#section_gyc_435_53b}

Selon le contexte d’utilisation, l’éditeur d’expression peut renvoyer différentes valeurs.

| Utilisation avancée de l’éditeur d’expression | Type d’expression renvoyé attendu |
|--- |--- |
| Condition (condition de source de données, condition de date) | boolean |
| Minuteur personnalisé | dateTimeOnly |
| Fuseau horaire personnalisé | timeZone ou chaîne (ex. Europe/Paris) |
| Mappage des paramètres d’action | Any |
