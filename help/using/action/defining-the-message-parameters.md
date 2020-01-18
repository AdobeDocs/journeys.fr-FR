---
title: Définition des paramètres du message
description: Découvrez comment définir les paramètres du message
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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# Définition des paramètres du message {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

Dans la section Paramètres **[!UICONTROL du]**message, collez un exemple de charge utile JSON à envoyer au service externe.


![](../assets/customactionpayloadmessage.png)

Vous pourrez définir si le type du paramètre est correct (ex. : string, integer, etc.).

Vous aurez également le choix entre spécifier un paramètre est une constante ou une variable :

* Constante signifie que la valeur du paramètre est définie dans le volet de configuration de l’action par une personne technique. La valeur sera toujours la même pour tous les voyages. Il ne varie pas et le spécialiste du marketing ne le voit pas lors de l’utilisation de l’action personnalisée dans le parcours. Il peut s’agir, par exemple, d’un identifiant auquel le système tiers s’attend. Dans ce cas, le champ à droite de la constante/variable de basculement est la valeur transmise.
* Variable signifie que la valeur du paramètre varie. Le spécialiste du marketing qui utilise cette action personnalisée dans un voyage peut transmettre la valeur qu’il souhaite ou spécifier où récupérer la valeur de ce paramètre (par exemple, à partir de l’événement, de la plateforme de données...). Dans ce cas, le champ à droite de la constante/variable de basculement est l’étiquette que le spécialiste du marketing verra dans le parcours pour nommer ce paramètre.
