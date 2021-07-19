---
product: adobe campaign
title: Généralités
description: Généralités relatives aux expressions avancées
feature: Parcours
role: Data Engineer
level: Experienced
exl-id: ba474219-7c9e-4f93-8e9c-16c317131614
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 100%

---

# Généralités {#concept_rcy_qj5_dgb}

## Parenthèses et priorité des expressions{#section_edf_fks_bgb}

Il est possible d’utiliser des parenthèses pour améliorer la lisibilité d’une expression complexe. _(&lt;expression>)_ est l’équivalent de _&lt;expression>_. Il est également possible d’utiliser des parenthèses pour définir l’ordre d’évaluation et l’associativité.

Les expressions sont évaluées de gauche à droite. L’associativité des opérateurs arithmétiques doit être appliquée : les multiplications et les divisions sont prioritaires sur les additions et les soustractions. Pour imposer un ordre spécifique, il est nécessaire d’ajouter des parenthèses afin de délimiter les opérations. Par exemple :

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| Expression | Évaluation |
|--- |--- |
| `4 + 2 * 10` | <ul><li>« * » a la priorité sur « + » : 2 * 10 est évalué → 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>Les parenthèses modifient la priorité : (4 + 2) est évalué → 6</li><li> 6 * 10 → 60</li></ul> |

## Respect de la casse{#section_lrb_xh5_dgb}

Les règles de respect de la casse sont les suivantes :

* Tous les opérateurs (and, or, etc.) doivent être en minuscules. Par exemple, _`<expression1>`and`<expression2>`_ est une expression valide, contrairement à l’expression _`<expression1>`AND`<expression2>`_.
* Tous les noms de fonctions sont sensibles à la casse. Par exemple _inSegment()_ est valide, contrairement à la fonction _INSEGMENT()_.
* Les références aux champs et les valeurs constantes respectent la casse : ces éléments ne sont pas intégrés au langage (par opposition aux opérateurs et aux fonctions), mais créés par l’utilisateur.

## Type d’expression renvoyé{#section_gyc_435_53b}

Selon le contexte d’utilisation, l’éditeur d’expression peut renvoyer différentes valeurs.

| Utilisation de l’éditeur d’expression avancé | Type d’expression renvoyé attendu |
|--- |--- |
| Condition (condition de source de données, condition de date) | booléen |
| Retardateur personnalisé | dateTimeOnly |
| Mappage des paramètres d’action | Tous |
