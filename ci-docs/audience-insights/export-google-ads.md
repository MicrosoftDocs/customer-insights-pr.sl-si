---
title: Izvozite podatke Customer Insights v Google Ads
description: Naučite se, kako konfigurirati povezavo in izvažati v Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c16967bf8ea1fd02b3f991d7b7d3715a71fa8681
ms.sourcegitcommit: 9a99e48e96dfb3d895db428f37c30ae55eea66b7
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/14/2021
ms.locfileid: "6604297"
---
# <a name="export-segments-to-google-ads-preview"></a>Izvoz segmentov v Google Ads (predogledna različica)

Segmente poenotenih profilov strank izvozite na seznam občinstva Google Ads in jih uporabite za oglaševanje v iskalniku Google, v storitvah Gmail, YouTube in v iskalnem omrežju Google. 

## <a name="prerequisites-for-connection"></a>Predpogoji za povezavo

-   Imate [račun za Google Ads](https://ads.google.com/) in ustrezne skrbniške poverilnice.
-   Imate [odobreni žeton razvijalca v storitvi Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token). 
-   Izpolnjujete zahteve, ki jih določa [Pravilnik o ujemanju strank](https://support.google.com/adspolicy/answer/6299717).
-   Izpolnjujete zahteve [velikosti seznama za ponovno trženje](https://support.google.com/google-ads/answer/7558048).
-   V storitvi Google Ads so na voljo obstoječa občinstva in ustrezni ID-ji. Če želite več informacij, glejte razdelek [Občinstva Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Imate [konfigurirane segmente](segments.md).
-   Poenoteni profili strank v izvoženih segmentih vsebujejo polja, ki predstavljajo e-poštni naslov ter ime in priimek.

## <a name="known-limitations"></a>Znane omejitve

- Do 1 milijon profilov na izvoz v Google Ads.
- Izvoz v Google Ads je omejen na segmente.
- Izvoz segmentov s skupno 1 milijonom profilov lahko traja do 5 minut zaradi omejitev na strani ponudnika. 
- Ujemanje v storitvi Google Ads lahko traja do 48 ur.

## <a name="set-up-connection-to-google-ads"></a>Nastavitev povezave s storitvijo Google Ads

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajanje povezave** in izberite **Google Ads** za konfiguracijo povezave.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vnesite **[ID stranke za Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Vnesite **[odobreni žeton razvijalca v storitvi Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.

1. Izberite **Preverjanje pristnosti s storitvijo Google Ads** in vnesite svoje poverilnice za Google Ads.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo. 

## <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Za ustvarjanje novega izvoza izberite **Dodaj cilj**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku Google Ads. Če se vam poimenovanje tega odseka ne prikaže, to pomeni, da vam ni na voljo nobena tovrstna povezava.

1. Vnesite **[ID občinstva za Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** in izberite **Poveži**, da inicializirate povezavo s storitvijo Google Ads.

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke.

1. Izberite segmente, ki jih želite izvoziti. V Google Ads lahko izvozite do 1 milijon profilov strank.

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab). 

Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Google Ads, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Google Ads izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
