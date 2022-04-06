---
title: Izvozite podatke Customer Insights v Google Ads
description: Naučite se, kako konfigurirati povezavo in izvažati v Google Ads.
ms.date: 03/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7a85237f7aff564d6b540b2c11553a52f875fac4
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/31/2022
ms.locfileid: "8523825"
---
# <a name="export-segments-to-google-ads-preview"></a>Izvoz segmentov v Google Ads (predogledna različica)

Segmente poenotenih profilov strank izvozite na seznam občinstva Google Ads in jih uporabite za oglaševanje v iskalniku Google, v storitvah Gmail, YouTube in v iskalnem omrežju Google. 


## <a name="prerequisites-for-connection"></a>Predpogoji za povezavo

-   Imate [račun za Google Ads](https://ads.google.com/) in ustrezne skrbniške poverilnice.
-   Izpolnjujete zahteve, ki jih določa [Pravilnik o ujemanju strank](https://support.google.com/adspolicy/answer/6299717).
-   Izpolnjujete zahteve [velikosti seznama za ponovno trženje](https://support.google.com/google-ads/answer/7558048).
-   Imate [konfigurirane segmente](segments.md).
-   Poenoteni profili strank v izvoženih segmentih vsebujejo polja, ki predstavljajo e-poštni naslov, telefon, ID mobilnega oglaševalca, ID uporabnika tretje osebe ali naslov.

## <a name="known-limitations"></a>Znane omejitve

- Izvoz v Google Ads je omejen na segmente.
- Izvoz segmentov s skupno 1 milijonom profilov strank lahko traja do 30 minut zaradi omejitev na strani ponudnika. 
- Ujemanje v storitvi Google Ads lahko traja do 48 ur.

## <a name="set-up-connection-to-google-ads"></a>Nastavitev povezave s storitvijo Google Ads

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajanje povezave** in izberite **Google Ads** za konfiguracijo povezave.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vnesite **[ID stranke za Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.

1. Izberite **Preverjanje pristnosti s storitvijo Google Ads** in vnesite svoje poverilnice za Google Ads.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo. 

## <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Za ustvarjanje novega izvoza izberite **Dodaj cilj**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku Google Ads. Če se vam poimenovanje tega odseka ne prikaže, to pomeni, da vam ni na voljo nobena tovrstna povezava.

1. Če želite ustvariti nov občinstvo, pustite polje ID Google občinstvo prazno. V vašem računu Google Ads bomo samodejno ustvarili nov občinstvo in uporabili ime izvoženega segmenta. Če želite posodobiti obstoječi Google Ads občinstvo, vnesite svoj [ID programa Google Ads občinstvo](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)

1. V **Ujemanje podatkov** izberite eno ali več podatkovnih polj za izvoz in izberite polje, ki predstavlja ustrezna podatkovna polja v Customer Insights.

1. Izberite segmente, ki jih želite izvoziti. 

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab). 

Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Google Ads, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Google Ads izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
