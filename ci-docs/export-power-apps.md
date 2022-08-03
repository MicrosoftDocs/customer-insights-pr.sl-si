---
title: Povezovalnik storitve Power Apps (predogled)
description: Povezava s storitvama Power Apps in Power Automate.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 8807e82e65ea20d1a7f7dc07552229f377927eed
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196920"
---
# <a name="power-apps-connector-preview"></a>Povezovalnik storitve Power Apps (predogled)

Vnesite poenotene profile strank v svoje prilagojene aplikacije s storitvijo Microsoft Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Povezava storitev Power Apps in Dynamics 365 Customer Insights

Storitev Customer Insights je ena od mnogih [razpoložljivih virov podatkov v storitvi Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Oglejte si dokumentacijo za Power Apps, če želite izvedeti več o [dodajanju podatkovne povezave v aplikacijo](/powerapps/maker/canvas-apps/add-data-connection). Priporočamo, da pregledate tudi [kako se v storitvi Power Apps uporablja pooblastitve za obdelavo velikih množic podatkov v aplikacijah s platnom](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Entitete, ki so na voljo

Ko dodate Customer Insights kot podatkovno povezavo, izberite naslednje entitete Power Apps:

- **Stranka**: uporaba podatkov iz [poenotenega profila stranke](customer-profiles.md).
- **UnifiedActivity**: prikaz [časovnega okvira dejavnosti](activities.md) v aplikaciji.
- **ContactProfile**: prikaz stikov stranke. Ta entiteta je na voljo samo v okoljih Customer Insights za poslovne račune.

## <a name="limitations"></a>Omejitve

### <a name="retrievable-entities"></a>Entitete, ki jih je mogoče pridobiti

S povezovalnikom Power Apps lahko pridobite le entitete **Stranka**, **UnifiedActivity**, **Segmenti** in **ContactProfile**. ContactProfile je na voljo samo v okoljih Customer Insights za poslovne račune. Prikazane so druge entitete, ker jih osnovni povezovalnik podpira prek sprožilcev v storitvi Power Automate.

V 60 sekundah lahko opravite največ 100 klicev. API končna točka lahko pokličete večkrat z uporabo parametra $skip. [Več o parametru $skip](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Pooblastitev

Pooblastitev deluje za entiteto **Stranka** in entiteto **UnifiedActivity**.

- Delegacija za **Stranka** entiteta: če želite uporabiti delegiranje za to entiteto, morajo biti polja indeksirana v [indeks iskanja in filtriranja](search-filter-index.md).  
- Pooblastitev za entiteto **UnifiedActivity**: pooblastitev za to entiteto deluje samo za polja **ActivityId** in **CustomerId**.  
- Pooblastitev za **ContactProfile**: pooblastitev za to entiteto deluje samo za polja **ContactId** in **CustomerId**. ContactProfile je na voljo samo v okoljih Customer Insights za poslovne račune.

Za več informacij o pooblastitvi odprite razdelek [Funkcije in postopki Power Apps, ki jih je mogoče pooblastiti](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="example-gallery-control"></a>Primer kontrolnika galerije

Po želji dodajte profile strank v a [nadzor nad galerijo](/powerapps/maker/canvas-apps/add-gallery).

1. Aplikaciji, ki jo ustvarjate, dodajte kontrolnik **Galerija**.
  
   :::image type="content" source="media/connector-powerapps9.png" alt-text="Dodajte element galerije.":::

1. Kot vir podatkov za elemente izberite **Stranka**.

   :::image type="content" source="media/choose-datasource-powerapps.png" alt-text="Izberite vir podatkov.":::

1. Spremenite podatkovno ploščo na desni, da izberete, katero polje za entiteto Stranka bo prikazano v galeriji.

1. Če želite prikazati določeno polje iz izbrane stranke v galeriji, izpolnite lastnost **Besedilo** za nalepko: .**{Name_of_the_gallery}.Selected.{property_name}**  
    - Na primer: _Gallery1.Selected.address1_city_

1. Če želite prikazati poenoteno časovnico za stranko, dodajte element galerije in lastnost **Elementi**: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Na primer: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_

[!INCLUDE [footer-include](includes/footer-banner.md)]
