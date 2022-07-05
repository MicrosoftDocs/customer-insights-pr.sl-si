---
title: Izvozi segmente v Braze (predogled)
description: Naučite se konfigurirati povezavo in izvoziti v Braze.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 314a61f82c4040a8dbd6dff1dd5d92e20464f82a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082690"
---
# <a name="export-segments-to-braze-preview"></a>Izvozi segmente v Braze (predogled)

Izvozite segmente enotnih profilov strank v Braze in jih uporabite za marketinške dejavnosti.

## <a name="prerequisites"></a>Zahteve

- A [Braze račun](https://www.braze.com/) in ustrezne skrbniške poverilnice.
- Obstoječe [segmenti v Braze](https://www.braze.com/docs/user_guide/engagement_tools/segments/creating_a_segment/).
- [Konfigurirani segmenti](segments.md) v Customer Insights.
- Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov in ID stranke Braze.

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

1. V **Povezava za izvoz** polje, izberite povezavo v razdelku Braze. Če tega razdelka ne vidite, vam ni na voljo nobenih povezav te vrste.  

1. Dodajte a **prikazno ime** za vaš izvoz.

1. Dodajte identifikator API segmenta Braze, v katerega želite izvoziti v **Identifikator API segmenta Braze** polje. Identifikator najdete v podrobnostih segmenta na platformi Braze.

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje, ki predstavlja e-poštni naslov stranke. V **identifikacijska številka stranke** polje, izberite polje, ki predstavlja strankin Braze ID. Potrebno je izvoziti segmente v Braze. Po želji lahko izberete več polj.

1. Izberite **Shrani**.

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab). Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Braze dovolite prenos podatkov izven meja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo te podatke prenesel po vaših navodilih, vendar ste odgovorni za zagotovitev, da Braze izpolnjuje vse vaše obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.
