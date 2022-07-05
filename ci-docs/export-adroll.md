---
title: Izvoz segmentov v AdRoll (predogledna različica)
description: Naučite se, kako konfigurirati povezavo in izvažati v storitev AdRoll.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 13c7dd3b8556ad807fba6c537525b463480e860b
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082837"
---
# <a name="export-segments-to-adroll-preview"></a>Izvoz segmentov v AdRoll (predogledna različica)

Izvozite segmente poenotenih profilov strank v storitev AdRoll in jih uporabite za oglaševanje. 

## <a name="prerequisites-for-a-connection"></a>Predpogoji za povezavo

- Imate [račun za AdRoll](https://www.adroll.com/) in ustrezne skrbniške poverilnice.
- Imaš [konfigurirani segmenti](segments.md) v Customer Insights.
- Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="known-limitations"></a>Znane omejitve

- V storitev AdRoll lahko hkrati izvozite do 250.000 profilov strank.
- Segmentov z manj kot 100 profili strank ne morete izvoziti v storitev AdRoll. 
- Izvoz v storitev AdRoll je omejen na segmente.
- Izvoz do 250.000 profilov strank v storitev AdRoll lahko traja do 10 minut. 
- Število profilov strank, ki jih lahko izvozite v storitev AdRoll, je odvisno od vaše pogodbe s storitvijo AdRoll.

## <a name="set-up-connection-to-adroll"></a>Nastavitev povezave s storitvijo AdRoll

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite možnost **Dodajanje povezave** in izberite **AdRoll** za konfiguracijo povezave.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.

1. Izberite možnost **Poveži**, da inicializirate povezavo s storitvijo AdRoll.

1. Izberite **Preverjanje pristnosti s storitvijo AdRoll** in vnesite svoje skrbniške poverilnice za AdRoll. 

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Za ustvarjanje novega izvoza izberite **Dodaj cilj**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku AdRoll. Če se vam poimenovanje tega odseka ne prikaže, to pomeni, da vam ni na voljo nobena tovrstna povezava.

1. Vnesite **ID oglaševalca AdRoll**. Za več informacij si oglejte možnost [Profili oglaševalcev AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje, ki predstavlja e-poštni naslov stranke. Segmente je treba izvoziti v storitev AdRoll.

1. Izberite segmente, ki jih želite izvoziti. Izberite segment z vsaj 100 člani. Manjših segmentov ni mogoče izvoziti. Poleg tega največja velikost segmenta za izvoz znaša 250.000 članov na izvoz. 

1. Izberite **Shrani**.

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab). 

Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v storitev AdRoll, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da storitev AdRoll izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.
