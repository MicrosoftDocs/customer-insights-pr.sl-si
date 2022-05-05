---
title: Izvozite podatke Customer Insights v Braze
description: Naučite se konfigurirati povezavo in izvoziti v Braze.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bfc9b34506dc3385b5edf12b31e74d05f2d20655
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643158"
---
# <a name="export-segment-lists-to-braze-preview"></a>Izvozi sezname segmentov v Braze (predogled)

Izvozite segmente enotnih profilov strank v Braze in jih uporabite za marketinške dejavnosti.

## <a name="prerequisites"></a>Zahteve

-   Imate [Braze račun](https://www.braze.com/) in ustrezne skrbniške poverilnice.
-   Imaš [konfigurirani segmenti](segments.md) v Customer Insights.
-   Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov in ID stranke Braze. 

## <a name="known-limitations"></a>Znane omejitve

- Izvoz v Braze je omejen na segmente.
- Izvoz do 1 milijona profilov strank v Braze lahko traja do 40 minut. 
- Število profilov strank, ki jih lahko izvozite v Braze, je odvisno in omejeno od vaše pogodbe z Braze.

## <a name="set-up-connection-to-braze"></a>Nastavite povezavo z Braze

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **Braze** da konfigurirate povezavo.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ponudite svoje [Braze API ključ](https://www.braze.com/docs/api/basics/) za nadaljevanje prijave. 

1. Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.

1. Izberite **Povežite se** za inicializacijo povezave z Braze.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Za ustvarjanje novega izvoza izberite **Dodaj cilj**.

1. V **Povezava za izvoz** polje, izberite povezavo v razdelku Braze. Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.  

3. V **Ujemanje podatkov** oddelku, v **E-naslov** polje, izberite polje, ki predstavlja e-poštni naslov stranke, v polju "ID stranke" izberite polje, ki predstavlja ID stranke Braze. Potrebno je izvoziti segmente v Braze. Segmenti v Braze bodo ustvarjeni z istim imenom segmenta kot v Dynamics 365 Customer Insights. Izberete lahko dodatna, neobvezna polja za ujemanje podatkov. 

1. Izberite **Shrani**.

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab). Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Braze dovolite prenos podatkov izven meja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo te podatke prenesel po vašem navodilu, vendar ste odgovorni za zagotovitev, da Braze izpolnjuje vse vaše obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.
