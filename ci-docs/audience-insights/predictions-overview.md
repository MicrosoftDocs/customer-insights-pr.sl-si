---
title: Pregled podprtih scenarijev predvidevanja
description: Scenariji in možnosti predvidevanja, ki jih zajema aplikacija Dynamics 365 Customer Insights.
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 11b0efeecf8bea893272e67d29b1c6622771110c
ms.sourcegitcommit: a5e4503cf9ce0cea562bab9389748d8ca1451f9d
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/25/2022
ms.locfileid: "8487555"
---
# <a name="predictions-overview"></a>Pregled predvidevanj

Dynamics 365 Customer Insights vsebuje različne možnosti, ki uporabljajo AI in strojno učenje za napovedovanje podatkov. 

## <a name="out-of-box-models"></a>Vnaprej pripravljeni modeli

Najlažji način za začetek napovedovanja podatkov predstavljajo vnaprej določeni modeli, ki jih pogosto imenujemo vnaprej pripravljeni modeli. Za hitro ustvarjanje vpogledov potrebujejo le določene podatke in strukturo. Trenutno so na voljo naslednji modeli: 

# <a name="individual-consumers-b-to-c"></a>[Posamezni potrošniki (prodaja strankam)](#tab/b2c)

- [Vrednost življenjske dobe stranke](predict-customer-lifetime-value.md): napoveduje potencialni prihodek stranke v celotni interakciji s podjetjem.
- [Priporočilo izdelka](predict-product-recommendation.md): predlaga nabore napovednih priporočil za izdelke, ki temeljijo na nakupnem vedenju in strankah s podobnimi vzorci nakupovanja.
- [Izguba naročnin](predict-subscription-churn.md): predvidi, ali za stranko obstaja tveganje, če ne bo več uporabljala naročniških izdelkov ali storitev vašega podjetja.
- [Izguba transakcij](predict-transactional-churn.md): predvidi, ali stranka ne bo več kupovala vaših izdelkov ali storitev v določenem časovnem okviru.
- [Analiza občutkov](sentiment-analysis.md) : Analizirajte čustva povratnih informacij strank in prepoznajte poslovne vidike, ki so pogosto omenjeni.

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (podjetja podjetjem)](#tab/b2b)

- [Izguba transakcij](predict-transactional-churn.md): predvidi, ali stranka ne bo več kupovala vaših izdelkov ali storitev v določenem časovnem okviru.

---

> [!TIP]
> Priporočamo, da redno posodabljate že pripravljene modele s posodobljenimi podatki, da zagotovite, da bodo natančno obveščali o vašem primeru poslovne uporabe. Podatki se osvežijo ad hoc, ko sistem zaužije nove ali posodobljene vire podatkov. Vendar bodo modeli samo v tem primeru ponovno ocenili in še naprej uporabljali obstoječe podatke o usposabljanju.
> 
> Konfigurirate lahko **Posodobitev urnika** z nastavitvijo urnika ponovnega usposabljanja modela v konfiguracijski izkušnji. Model se bo ponovno usposobil in ocenil po tem urniku, ki ga lahko kadar koli spremenite.


## <a name="azure-machine-learning-integration"></a>Integracija strojnega učenja Azure

Če organizacija že uporablja scenarije strojnega učenja, ki temeljijo na poskusih strojnega učenja Azure, bo funkcija modelov po meri v Customer Insights pomagala povezovati pike. Ustvarite poteke dela, ki vam pomagajo izbrati podatke, iz katerih želite ustvariti vpogled, in rezultate preslikajte v svoje poenotene profile strank. Za več informacij glejte [Modeli strojnega učenja po meri](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder predvidevanje

Včasih so nabori podatkov nepopolni in nekatere vrednosti manjkajo. Customer Insights vam lahko pomaga napovedati manjkajoče vrednosti za entiteto in segmente stranke. Za več informacij glejte razdelek [Dopolnjevanje delnih podatkov s predvidevanji](predictions.md).
