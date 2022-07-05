---
title: Izvoz segmentov v Criteo (predogled)
description: Naučite se konfigurirati povezavo in izvoziti v Criteo.
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ace9056d200a3179e442132004324a01f0d247b6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082795"
---
# <a name="export-segments-to-criteo-preview"></a>Izvoz segmentov v Criteo (predogled)

Izvozite segmente enotnih profilov strank za ustvarjanje kampanj, zagotavljanje e-poštnega trženja in uporabo posebnih skupin strank s Criteom.

## <a name="prerequisites-for-connection"></a>Predpogoji za povezavo

-   Imate [Račun za ponovno ciljanje Criteo Dynamics](https://www.criteo.com/login/) in ustrezne skrbniške poverilnice.
-   Imate [konfigurirane segmente](segments.md).
-   Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="known-limitations"></a>Znane omejitve

- Do 1 milijon profilov strank na izvoz v Criteo.
- Izvoz v Criteo je omejen na segmente.
- Izvoz segmentov s skupno 1 milijonom profilov strank lahko traja do 30 minut. 
- Število profilov strank, ki jih lahko izvozite v Criteo, je odvisno in omejeno od vaše pogodbe s Criteo.

## <a name="set-up-connection-to-criteo"></a>Nastavite povezavo s Criteo

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **Criteo** da konfigurirate povezavo.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Izberite **strinjam se** za potrditev **Zasebnost podatkov in skladnost** in izberite **Povežite se** za inicializacijo povezave s Criteo.

1. Izberite **Preverjanje pristnosti s Criteo** in navedite svoje skrbniško uporabniško ime in poverilnice za Criteo. 

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Za ustvarjanje novega izvoza izberite **Dodaj cilj**.

1. V **Povezava za izvoz** polje, izberite povezavo v razdelku Criteo. Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava. 

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje, ki predstavlja e-poštni naslov stranke. 

1. Po želji lahko izvozite **ID oglaševalca** in **ime**

1. Izberite segmente, ki jih želite izvoziti. 

1. Izberite **Shrani**.

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab). Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Criteo dovolite prenos podatkov izven meja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo te podatke prenesel po vašem navodilu, vendar ste odgovorni za zagotovitev, da Criteo izpolnjuje morebitne obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.


[!INCLUDE[footer-include](includes/footer-banner.md)]
