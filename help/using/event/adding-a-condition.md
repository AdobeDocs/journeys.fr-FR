---
title: Ajout d’une condition
description: Découvrez comment ajouter une condition
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
source-git-commit: 5df2fecc56d2d2d081d952f17aadf103f2f0140a

---



# Ajout d’une condition {#concept_rbg_gqt_52b}

La condition d’événement permet au système de filtrer le traitement des événements. Si la condition est vraie, l’événement est traité. Si la condition n’est pas vraie, l’événement est ignoré.

La condition sur les événements ne peut être basée que sur les données transmises dans la charge utile de l’événement. La condition définie au niveau de l’événement ne peut pas être modifiée dans la trame par un spécialiste du marketing. L’objectif est de durcir cette condition lorsque cet événement est utilisé. Par exemple, si vous ne souhaitez jamais que les marketeurs utilisent des événements d’abandon de panier si la valeur du panier est trop faible, vous pouvez créer une condition sur le champ d’événement &quot;valeur du panier&quot; et imposer une valeur supérieure à 100 dollars.

Vous pouvez utiliser l’éditeur d’expression simple ou l’éditeur d’expression avancé pour configurer des conditions sur des événements. Voir la section [](../expression/expressionadvanced.md).

Par exemple, vous pouvez définir une condition pour traiter uniquement les événements d’un type d’événement spécifique et ignorer les autres types. Ou si votre événement est un abandon de panier et que la charge utile inclut le champ de valeur de panier, vous pouvez définir une condition d’événement pour traiter les événements uniquement si la valeur de panier est supérieure à 100 dollars.

![](../assets/journey78.png)
