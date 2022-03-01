---
title: Povezovalnik Power Apps
description: Povezava s storitvama Power Apps in Power Automate.
ms.date: 08/21/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b6ec103e29e218b2f27bfc1193300ea793a6b30b
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406949"
---
# <a name="microsoft-power-apps-connector-preview"></a>Povezovalnik storitve Microsoft Power Apps (predogled)

Vnesite poenotene profile strank v svoje prilagojene aplikacije s storitvijo Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Povezava storitev Power Apps in Dynamics 365 Customer Insights

Storitev Customer Insights je ena od mnogih [razpoložljivih virov podatkov v storitvi Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).

Oglejte si dokumentacijo za Power Apps, če želite izvedeti več o [dodajanju podatkovne povezave v aplikacijo](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection). Priporočamo, da pregledate tudi [kako se v storitvi Power Apps uporablja pooblastitve za obdelavo velikih množic podatkov v aplikacijah s platnom](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Entitete, ki so na voljo

Ko dodate storitev Customer Insights kot podatkovno povezavo, lahko v storitvi Power Apps izberete naslednje entitete:

- Stranka: uporaba podatkov iz [poenotenega profila stranke](customer-profiles.md).
- Poenotena dejavnost stranke: prikaz [časovnice dejavnosti](activities.md) v aplikaciji.

## <a name="limitations"></a>Omejitve

### <a name="retrievable-entities"></a>Entitete, ki jih je mogoče pridobiti

Prek povezovalnika za Power Apps lahko pridobite samo entitete **Stranka**, **UnifiedActivity** in **Segmenti**. Prikazane so druge entitete, ker jih osnovni povezovalnik podpira prek sprožilcev v storitvi Power Automate.  

### <a name="delegation"></a>Pooblastitev

Pooblastitev deluje za entiteto »Stranka« in entiteto »UnifiedActivity«. 

- Pooblastitev za entiteto **Stranka**: če želite uporabiti pooblastitev za to entiteto, je treba polja indeksirati pri možnosti [Kazalo za iskanje in filtre](search-filter-index.md).  

- Pooblastitev za entiteto **UnifiedActivity**: pooblastitev za to entiteto deluje samo za polja **ActivityId** in **CustomerId**.  

- Za več informacij o pooblastitvi glejte [Funkcije in postopki v storitvi Power Apps. ki jih je mogoče pooblastiti](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Primer kontrolnika galerije

Profile strank na primer dodate v [kontrolnik galerije](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).

1. Aplikaciji, ki jo ustvarjate, dodajte kontrolnik **Galerija**.

> [!div class="mx-imgBorder"]
> ![Dodajanje elementa galerije](media/connector-powerapps9.png "Dodajanje elementa galerije")

1. Kot vir podatkov za elemente izberite **Stranka**.

    > [!div class="mx-imgBorder"]
    > ![Izbira vira podatkov](media/choose-datasource-powerapps.png "Izbira vira podatkov")

1. Ploščo podatkov na desni strani lahko spremenite in izberete, katero polje za entiteto stranke bo prikazano v galeriji.

1. Če želite prikazati določeno polje iz izbrane stranke v galeriji, izpolnite lastnost »Besedilo« za nalepko: **{Name_of_the_gallery}.Selected.{property_name}**

    Primer: Gallery1.Selected.address1_city

1. Če želite prikazati poenoteno časovnico za stranko, dodajte element galerije in lastnost »Elementi«: **('UnifiedActivity', CustomerId = {Customer_Id})**

    Primer: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)
