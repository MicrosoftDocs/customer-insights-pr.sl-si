---
title: Izvozite podatke Customer Insights v Marketo
description: Naučite se, kako konfigurirati povezavo in izvažati v Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759841"
---
# <a name="export-segments-to-marketo-preview"></a>Izvoz segmentov v Marketo (predogledna različica)

Izvozite segmente poenotenih profilov strank, da akcije, zagotovite e-poštno trženje in uporabite določene skupine strank s storitvijo Marketo.

## <a name="prerequisites-for-connection"></a>Predpogoji za povezavo

-   Imate [račun za Marketo](https://login.marketo.com/) in ustrezne skrbniške poverilnice.
-   V storitvi Marketo so na voljo obstoječi seznami in ustrezni ID-ji. Več informacij je na voljo na [seznamih Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Imate [konfigurirane segmente](segments.md).
-   Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="known-limitations"></a>Znane omejitve

- Do 1 milijon profilov na izvoz v Marketo.
- Izvoz v Marketo je omejen na segmente.
- Izvoz segmentov s skupno 1 milijonom profilov lahko traja do 3 ure. 
- Število profilov, ki jih lahko izvozite v Marketo, je odvisno in omejeno glede na vašo pogodbo s podjetjem Marketo.

## <a name="set-up-connection-to-marketo"></a>Nastavitev povezave s storitvijo Marketo

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajanje povezave** in izberite **Marketo** za konfiguracijo povezave.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vnesite svoj **[ID odjemalca Marketo, skrivnost odjemalca in ime gostitelja končne točke REST](https://developers.marketo.com/rest-api/authentication/)**.

1. Izberite **Strinjam se** za potrditev možnosti **Zasebnost podatkov in skladnost** in izberite možnost **Poveži**, da inicializirate povezavo s storitvijo Marketo.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Za ustvarjanje novega izvoza izberite **Dodaj cilj**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku Marketo. Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.

1. Vnesite svoj **[ID seznama Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke. 

1. Izbirno lahko izvozite **Ime**, **Priimek**, **Mesto**, **Zvezna država** in **Država/regija**, da ustvarite bolj prilagojena e-poštna sporočila. Izberite **Dodaj atribut** za preslikavo teh polj.

1. Izberite segmente, ki jih želite izvoziti. V Marketo lahko izvozite do 1 milijon profilov strank.

1. Izberite **Shrani**.

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab). Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand). V storitvi Marketo lahko zdaj najdete svoje segmente pod možnostjo [Občinstva Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Marketo, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Marketo izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.


[!INCLUDE[footer-include](../includes/footer-banner.md)]