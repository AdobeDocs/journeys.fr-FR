---
product: adobe campaign
title: Ajout d’une condition
description: Découvrez comment ajouter une condition
feature: Parcours
role: User
level: Intermediate
exl-id: 09cda689-6953-4ea6-a446-cb4e1d8ad8e4
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 100%

---

# Ajout d’une condition {#concept_rbg_gqt_52b}

Pour les événements générés par le système, vous pouvez définir une condition d’événement qui permet au système de filtrer le traitement des événements. Si la condition est vraie, l&#39;événement est traité. Dans le cas contraire, il est ignoré.

La condition relative aux événements ne peut être basée que sur les données transmises dans la payload d&#39;événement. La condition définie au niveau de l&#39;événement ne peut pas être modifiée par un marketeur dans la zone de travail. L&#39;objectif est de rendre cette condition plus stricte lorsque cet événement est utilisé. Par exemple, si vous ne souhaitez pas que les marketeurs utilisent des événements d&#39;abandon de panier si la valeur du panier est trop faible, vous pouvez créer une condition sur le champ d&#39;événement « valeur du panier » et imposer une valeur supérieure à 100 euros.

Vous pouvez utiliser l&#39;éditeur d&#39;expression simple ou avancé pour configurer des conditions sur les événements. Voir [cette page](../expression/expressionadvanced.md).

Vous pouvez, par exemple, définir une condition pour ne traiter que les événements d&#39;un type spécifique et ignorer les autres. Si votre événement est un abandon de panier et que la payload comprend le champ de valeur de panier, vous pouvez définir une condition d&#39;événement afin de ne traiter les événements que si la valeur du panier est supérieure à 100 euros.

![](../assets/journey78.png)
