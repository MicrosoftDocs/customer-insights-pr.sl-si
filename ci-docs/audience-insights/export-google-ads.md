---
title: Izvozite podatke Customer Insights v Google Ads
description: Preberite o konfiguraciji povezave s storitvijo Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ba7c82e643ea0dc1897e0954e78646932cafffa3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268982"
---
# <a name="connector-for-google-ads-preview"></a>Povezovalnik za Google Ads (predogled)

Izvozite segmente poenotenih profilov strank na seznam občinstva storitve Google Ads in jih uporabite za oglaševanje v Googlovem iskalniku ter storitvah Gmail, YouTube in Google Display Network. 

## <a name="prerequisites"></a>Zahteve

-   Imate [račun za Google Ads](https://ads.google.com/) in ustrezne skrbniške poverilnice.
-   V storitvi Google Ads so na voljo obstoječa občinstva in ustrezni ID-ji. Če želite več informacij, glejte razdelek [Občinstva Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Imate [konfigurirane segmente](segments.md)
-   Poenoteni profili strank v izvoženih segmentih vsebujejo polja, ki predstavljajo e-poštni naslov, ime in priimek.

## <a name="connect-to-google-ads"></a>Vzpostavitev povezave s storitvijo Google Ads

1. Izberite **Skrbnik** > **Cilji za izvoz**.

1. V razdelku **Google Ads** izberite **Nastavi**.

1. Dajte svojemu cilju izvoza prepoznavno ime v polju **Prikazno ime**.

1. Vnesite **[ID stranke za Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Vnesite **[odobreni žeton razvijalca v storitvi Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.

1. Vnesite **[ID občinstva za Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** in izberite **Poveži**, da inicializirate povezavo s storitvijo Google Ads.

1. Izberite **Preverjanje pristnosti s storitvijo Google Ads** in vnesite svoje poverilnice za Google Ads.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Posnetek zaslona izvoza za povezavo Google Ads":::

1. Izberite **Naslednji** za nastavitev izvoza.

## <a name="configure-the-connector"></a>Konfiguracija povezovalnika

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke. Ponovite iste korake za polji **Ime** in **Priimek**.

1. Izberite segmente, ki jih želite izvoziti. V Google Ads lahko izvozite do 1 milijon profilov strank.

1. Izberite **Shrani**.

## <a name="export-the-data"></a>Izvoz podatkov

Lahko [izvozite podatke na zahtevo](export-destinations.md). Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab). V storitvi Google Ads lahko zdaj najdete svoje segmente pod možnostjo [Občinstva Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Znane omejitve

- Do 1 milijon profilov na izvoz v Google Ads.
- Izvoz v Google Ads je omejen na segmente.
- Izvoz segmentov s skupno 1 milijonom profilov lahko traja do 5 minut zaradi omejitev na strani ponudnika. 
- Ujemanje v storitvi Google Ads lahko traja do 48 ur.

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Google Ads, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Google Ads izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.


[!INCLUDE[footer-include](../includes/footer-banner.md)]