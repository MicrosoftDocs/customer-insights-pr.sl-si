---
title: Izvozite podatke Customer Insights v Google Ads
description: Naučite se, kako konfigurirati povezavo in izvažati v Google Ads.
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c958f58c927b76364f305dad8f524dde29b2a638
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558992"
---
# <a name="export-segments-to-google-ads-preview"></a>Izvoz segmentov v Google Ads (predogledna različica)

Segmente poenotenih profilov strank izvozite na seznam občinstva Google Ads in jih uporabite za oglaševanje v iskalniku Google, v storitvah Gmail, YouTube in v iskalnem omrežju Google. 

> [!IMPORTANT]
> Trenutno lahko ustvarite novo povezavo in izvozite podatke v storitev Google Ads, če že imate odobren žeton za razvijalca v storitvi Google Ads. Zaradi sprememb pravilnika bomo kmalu posodobili izvoz storitve Google Ads in zagotovili možnost izvoza, ki ne bo zahtevala žetona za razvijalca, da bi zagotovili neprekinjeno izkušnjo in poenostavili izvoz v storitev Google Ads. Priporočamo, da ne nastavite več povezav s storitvijo Google Ads, da bi olajšali prehod na novo možnost izvoza.

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
