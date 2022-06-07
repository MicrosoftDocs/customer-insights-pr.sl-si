---
title: Kako - Upravljati okolja
description: Naučite se upravljati obstoječa okolja Customer Insights kot skrbnik."
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 62a5856edac5e66e5e42c93313d78fa6826469b3
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833512"
---
# <a name="how-to-manage-environments"></a>Kako: upravljati okolja

skrbniki [ustvariti](create-environment.md) in upravljati okolja. Lahko spremenijo nekatere nastavitve v obstoječih okoljih. Podjetje, vrsta, regija, možnost shranjevanja in Dataverse nastavitve so popravljene po ustvarjanju okolja. Če želite spremeniti te nastavitve, ponastavite okolje ali ustvarite novo okolje.

## <a name="edit-an-existing-environment"></a>Urejanje obstoječega okolja

Uredite lahko določene podatke obstoječih okolij.

1. V glavi aplikacije izberite izbirnik **Okolje**.

1. Izberite ikono za **urejanje**.

   :::image type="content" source="media/edit-environment.png" alt-text="Ikona za urejanje nastavitev okolja.":::

1. V polju **Urejanje okolja**, lahko posodobite nastavitve okolja.

Za začetek s svežim okoljem, gl [Ustvarite novo okolje](create-environment.md).

## <a name="change-the-owner-of-an-environment"></a>Spremenite lastnika okolja

Več uporabnikov ima lahko skrbniška dovoljenja, vendar je samo en uporabnik lastnik okolja. Privzeto je skrbnik tisti, ki prvotno ustvari okolje. Kot skrbnik okolja lahko dodelite lastništvo drugemu uporabniku s skrbniškimi dovoljenji.

1. V glavi aplikacije izberite izbirnik **Okolje**.

1. Izberite ikono za **urejanje**.

1. V **Uredi okolje** polje, pojdite na **Osnovni podatki** korak.

1. V **Zamenjajte lastnika okolja** polje, izberite novega lastnika okolja.  

1. Izberite **Preglejte in dokončajte**, potem **Nadgradnja** za uveljavitev sprememb.

## <a name="claim-ownership-of-an-environment"></a>Zahtevajte lastništvo okolja

Če je uporabniški račun lastnika izbrisan ali onemogočen, okolje ne bo imelo lastnika. Vsak skrbniški uporabnik lahko zahteva lastništvo in postane novi lastnik. Še naprej si lahko lastijo okolje oz [spremeni lastništvo drugemu skrbniku](#change-the-owner-of-an-environment).

Če želite zahtevati lastništvo, izberite **Prevzemi lastništvo** gumb, ki se prikaže na vrhu vsake strani v Customer Insights, ko je prvotni lastnik zapustil organizacijo.

## <a name="reset-an-existing-environment-preview"></a>Ponastavitev obstoječega okolja (predogled)

Kot lastnik okolja lahko okolje ponastavite na prazno stanje, če želite izbrisati vse konfiguracije in odstraniti vnesene podatke.

1. V glavi aplikacije izberite izbirnik **Okolje**.

1. Izberite okolje, ki ga želite ponastaviti, in izberite navpično tritočko (&vellip;).

1. Izberite možnost **Ponastavi**.

   :::image type="content" source="media/reset-environment.png" alt-text="Nadzor za ponastavitev okolja.":::

1. Izberite, ali želite ponastaviti celotno okolje, vse razen podatkovnih virov ali karkoli, kar je konfigurirano na vrhu enotnega profila stranke.

1. Za potrditev vnesite ime okolja in izberite **Ponastaviti**.

## <a name="delete-an-existing-environment"></a>Brisanje obstoječega okolja

Kot lastnik okolja lahko izbrišete okolje, ki ga upravljate.

1. V glavi aplikacije izberite izbirnik **Okolje**.

1. Izberite okolje, ki ga želite ponastaviti, in izberite navpično tritočko (&vellip;). 

1. Izberite možnost **Izbriši**.

   :::image type="content" source="media/delete-environment.png" alt-text="Nadzor za brisanje okolja.":::

1. Če želite potrditi izbris, vnesite ime okolja in izberite **Izbriši**.

> [!IMPORTANT]
> Če izbrišete okolje, ne odstranite povezave z a Dataverse okolje. Če nameravate povezati isto Dataverse okolje v novo okolje Customer Insights v prihodnosti, morate odstraniti to povezavo Naučite se [odstranite obstoječo povezavo z a Dataverse okolje](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

[!INCLUDE [footer-include](includes/footer-banner.md)]
