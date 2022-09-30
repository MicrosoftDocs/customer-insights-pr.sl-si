---
title: Upravljanje okolij
description: Naučite se upravljati obstoječa okolja Customer Insights kot skrbnik.
ms.date: 08/15/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 6d48f7088d722b27ca69cd591178651bdb6e2c23
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588832"
---
# <a name="manage-environments"></a>Upravljanje okolij

Administratorji [ustvariti](create-environment.md) in upravljajte okolja. Lahko spremenijo nekatere nastavitve v obstoječih okoljih. Podjetje, vrsta, regija, možnost shranjevanja in Dataverse nastavitve se popravijo po ustvarjanju okolja. Če želite spremeniti te nastavitve, [ponastavite okolje](#reset-an-existing-environment-preview) oz [ustvariti novo okolje](create-environment.md).

## <a name="edit-an-existing-environment"></a>Urejanje obstoječega okolja

Uredite podrobnosti obstoječega okolja, kot je ime ali nastavitev privzetega okolja.

1. V glavi aplikacije izberite izbirnik **Okolje**.

1. Izberite ikono za **urejanje**.

   :::image type="content" source="media/edit-environment.png" alt-text="Ikona za urejanje nastavitev okolja.":::

1. V **Uredi okolje** podoknu posodobite nastavitve okolja.

1. Izberite **Pregled in dokončanje**, potem **Nadgradnja** za uporabo sprememb.

## <a name="change-the-owner-of-an-environment"></a>Spremenite lastnika okolja

Več uporabnikov ima lahko skrbniška dovoljenja, vendar je samo en uporabnik lastnik okolja. Privzeto je skrbnik tisti, ki na začetku ustvari okolje. Kot skrbnik okolja lahko dodelite lastništvo drugemu uporabniku s skrbniškimi dovoljenji.

1. V glavi aplikacije izberite izbirnik **Okolje**.

1. Izberite ikono za **urejanje**.

1. V **Uredi okolje** podokno, pojdite na **Osnovni podatki** korak.

1. V **Spremeni lastnika okolja** polje, izbere novega lastnika okolja.  

1. Izberite **Pregled in dokončanje**, potem **Nadgradnja** za uporabo sprememb.

## <a name="claim-ownership-of-an-environment"></a>Zahtevajte lastništvo okolja

Če je uporabniški račun lastnika izbrisan ali začasno ustavljen, okolje ne bo imelo lastnika. Vsak skrbniški uporabnik lahko prevzame lastništvo in postane novi lastnik. Lastnik admin si lahko še naprej lasti okolje oz [spremenite lastništvo na drugega skrbnika](#change-the-owner-of-an-environment).

Če želite zahtevati lastništvo, izberite **Prevzemi lastništvo** gumb, ki se prikaže na vrhu vsake strani v Customer Insights, ko je prvotni lastnik zapustil organizacijo.

## <a name="reset-an-existing-environment-preview"></a>Ponastavi obstoječe okolje (predogled)

Kot lastnik okolja ponastavite okolje na prazno stanje, če želite izbrisati vse konfiguracije in odstraniti vnesene podatke.

1. V glavi aplikacije izberite izbirnik **Okolje**.

1. Izberite okolje, ki ga želite ponastaviti, in izberite navpično elipso (&vellip;).

1. Izberite **Ponastavi (predogled)**.

   :::image type="content" source="media/reset-environment.png" alt-text="Nadzor za ponastavitev okolja.":::

1. Izberite, ali želite ponastaviti celotno okolje, vse razen podatkovnih virov ali karkoli, kar je konfigurirano na vrhu poenotenega profila stranke.

1. Za potrditev vnesite ime okolja in izberite **Ponastaviti**.

## <a name="delete-an-existing-environment"></a>Brisanje obstoječega okolja

Kot lastnik okolja ga lahko izbrišete.

> [!IMPORTANT]
> Brisanje okolja ne odstrani povezave z a Dataverse okolju. Če nameravate povezati isto Dataverse okolje v novo okolje Customer Insights v prihodnosti, morate [odstranite to povezavo z Dataverse okolju](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

1. V glavi aplikacije izberite izbirnik **Okolje**.

1. Izberite okolje, ki ga želite izbrisati, in izberite navpično elipso (&vellip;). 

1. Izberite **Izbriši**.

   :::image type="content" source="media/delete-environment.png" alt-text="Nadzor za brisanje okolja.":::

1. Če želite potrditi izbris, vnesite ime okolja in izberite **Izbriši**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
