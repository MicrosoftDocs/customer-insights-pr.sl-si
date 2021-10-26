---
title: Povezovalnik Power Apps
description: Povezava s storitvama Power Apps in Power Automate.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 985e6c85795fba8ca3063cdffc7f9012e798856a
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623243"
---
# <a name="microsoft-power-apps-connector-preview"></a>Povezovalnik storitve Microsoft Power Apps (predogled)

Vnesite poenotene profile strank v svoje prilagojene aplikacije s storitvijo Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Povezava storitev Power Apps in Dynamics 365 Customer Insights

Storitev Customer Insights je ena od mnogih [razpoložljivih virov podatkov v storitvi Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Oglejte si dokumentacijo za Power Apps, če želite izvedeti več o [dodajanju podatkovne povezave v aplikacijo](/powerapps/maker/canvas-apps/add-data-connection). Priporočamo, da pregledate tudi [kako se v storitvi Power Apps uporablja pooblastitve za obdelavo velikih množic podatkov v aplikacijah s platnom](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Entitete, ki so na voljo

Ko dodate storitev Customer Insights kot podatkovno povezavo, lahko v storitvi Power Apps izberete naslednje entitete:

- **Stranka**: uporaba podatkov iz [poenotenega profila stranke](customer-profiles.md).
- **UnifiedActivity**: prikaz [časovnega okvira dejavnosti](activities.md) v aplikaciji.
- **ContactProfile**: prikaz stikov stranke. Entiteta je na voljo samo v okoljih vpogledov v občinstvo za poslovne račune.

## <a name="limitations"></a>Omejitve

### <a name="retrievable-entities"></a>Entitete, ki jih je mogoče pridobiti

S povezovalnikom Power Apps lahko pridobite le entitete **Stranka**, **UnifiedActivity**, **Segmenti** in **ContactProfile**. »ContactProfile« je na voljo samo v primerkih vpogledov v občinstvo za poslovne račune. Prikazane so druge entitete, ker jih osnovni povezovalnik podpira prek sprožilcev v storitvi Power Automate.

### <a name="delegation"></a>Pooblastitev

Pooblastitev deluje za entiteto **Stranka** in entiteto **UnifiedActivity**. 

- Pooblastitev za entiteto **Stranka**: če želite uporabiti pooblastitev za to entiteto, je treba polja indeksirati pri možnosti [Kazalo za iskanje in filtre](search-filter-index.md).  
- Pooblastitev za entiteto **UnifiedActivity**: pooblastitev za to entiteto deluje samo za polja **ActivityId** in **CustomerId**.  
- Pooblastitev za **ContactProfile**: pooblastitev za to entiteto deluje samo za polja **ContactId** in **CustomerId**. »ContactProfile« je na voljo samo v okoljih vpogledov v občinstvo za poslovne račune.

Za več informacij o pooblastitvi odprite razdelek [Funkcije in postopki Power Apps, ki jih je mogoče pooblastiti](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>Primer kontrolnika galerije

Profile strank lahko dodate v [kontrolnik za galerijo](/powerapps/maker/canvas-apps/add-gallery).

1. Aplikaciji, ki jo ustvarjate, dodajte kontrolnik **Galerija**.

    > [!div class="mx-imgBorder"]
    > ![Dodajte element galerije.](media/connector-powerapps9.png "Dodajte element galerije.")

2. Kot vir podatkov za elemente izberite **Stranka**.

    > [!div class="mx-imgBorder"]
    > ![Izberite vir podatkov.](media/choose-datasource-powerapps.png "Izberite vir podatkov.")

3. Ploščo podatkov na desni strani lahko spremenite in izberete, katero polje za entiteto stranke bo prikazano v galeriji.

4. Če želite prikazati določeno polje iz izbrane stranke v galeriji, izpolnite lastnost **Besedilo** za nalepko: .**{Name_of_the_gallery}.Selected.{property_name}**  
    - Na primer: _Gallery1.Selected.address1_city_

5. Če želite prikazati poenoteno časovnico za stranko, dodajte element galerije in lastnost **Elementi**: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Na primer: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE[footer-include](../includes/footer-banner.md)]
