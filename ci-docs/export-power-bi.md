---
title: Povezovalnik Power BI
description: Seznanite se z uporabo povezovalnika Dynamics 365 Customer Insights v storitvi Power BI.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e901114703a43b4b4e751e0a93eb4876d7636c00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643640"
---
# <a name="connector-for-power-bi-preview"></a>Povezovalnik za Power BI (predogled)

Ustvarite vizualizacije svojih podatkov s storitvijo Power BI Desktop. Ustvarite dodatne vpoglede in poročila s svojimi poenotenimi podatki o strankah.

## <a name="prerequisites"></a>Zahteve

- Imate poenotene profile strank.
- Najnovejša različica aplikacije [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) je nameščena v vašem računalniku. [Preberite več o storitvi Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfiguracija povezovalnika za Power BI

1. V storitvi Power BI Desktop izberite možnost **Datoteka** > **Pridobi podatke**.

1. Izberite **Prikaži več** in poiščite storitev **Dynamics 365 Customer Insights**

1. Izberite **Vzpostavljanje povezave**.

1. Opravite **Vpis** z enakim računom organizacije, ki ga uporabljate za storitev Customer Insights, in izberite možnost **Poveži**.
   > [!NOTE]
   > Račun, ki ga navedete v tem koraku, se uporablja za pridobivanje podatkov iz storitve Customer Insights in ni nujno enak tistemu, v katerega ste prijavljeni v Power BI. Če želite ponastaviti račun, ki se uporablja za pridobivanje podatkov, odprite Power BI in izberite **Datoteka** > **Možnosti** > **Nastavitve** > **Nastavitve vira podatkov**. Na seznamu virov podatkov izberite **Prijava v Dynamics 365 Customer Insights** in izberite **Počisti dovoljenja**.  

1. V pogovornem oknu **Krmilnik**. Prikazan je seznam vseh okolij, do katerih imate dostop. Razširite okolje in odprite katero koli mapo (entitete, mere, segmenti, obogatitve). Odprite na primer mapo **Entitete** za ogled vseh entitet, ki jih lahko uvozite.

   ![Krmilnik povezovalnika storitve Power BI.](media/power-bi-navigator.png "Krmilnik povezovalnika storitve Power BI")

1. Izberite potrditvena polja poleg entitet, ki jih želite vključiti, in nato **Naloži**. Izberete lahko več entitet iz več okolij.

1. Med nalaganjem entitet bo prikazano pogovorno okno za nalaganje. Ko se naložijo vse vaše izbrane entitete, lahko uporabite zmožnosti Power BI za vizualizacijo podatkov.

## <a name="large-data-sets"></a>Obsežni nabori podatkov

Povezovalnik Customer Insights za Power BI je zasnovan tako, da deluje za nabore podatkov, ki imajo do 1 milijona profilov strank. Uvoz večjih naborov podatkov lahko deluje, vendar traja dolgo. Poleg tega lahko zaradi omejitev storitve Power BI pride do časovnih omejitev. Za več informacij glejte [Power BI: priporočila za obsežne nabore podatkov](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Delo s podmnožico želenih podatkov

Razmislite o delu s podmnožico svojih podatkov. Lahko na primer ustvarite [segmente](segments.md) namesto izvoza vseh zapisov strank v storitev Power BI.

## <a name="troubleshooting"></a>Odpravljanje težav

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Okolje storitve Customer Insights se ne prikaže v storitvi Power BI

Okolja, ki imajo več kot eno [odnos](relationships.md) definirana med dvema enakima entitetama v Customer Insights, ne bo na voljo v Power BI konektor.

Podvojene odnose lahko prepoznate in jih odstranite.

1. Pojdi do **Podatki** > **Odnosi** o okolju, v katerem pogrešate Power BI.
2. Prepoznajte podvojene odnose:
   - Preverite, ali je med istima entitetama določen več kot en odnos.
   - Preverite, ali je odnos ustvarjen med entitetama, ki sta vključeni v postopek poenotenja. Med vsemi entitetami, vključenimi v postopek združevanja, je določen implicitni odnos.
3. Odstranite vse prepoznane podvojene odnose.

Po odstranitvi podvojenih odnosov poskusite znova konfigurirati povezovalnik storitve Power BI. Okolje bi moralo biti zdaj na voljo.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Napake v datumskih poljih pri nalaganju entitet v Power BI Desktop

Ko nalagate entitete, ki vsebujejo polja z obliko datuma, kot je DD/MM/LLLL, lahko naletite na napake zaradi neusklajenih oblik območnih nastavitev. Ta neusklajenost se zgodi, ko vaš Power BI Desktop je nastavljena na drugo jezikovno nastavitev kot angleščina (Združene države), ker so datumska polja v Customer Insights shranjena v formatu ZDA.

Datoteka Power BI Desktop ima eno območno nastavitev, ki se uporablja pri pridobivanju podatkov. Če želite pravilno razlagati ta datumska polja, nastavite območno nastavitev datoteke .BPI v angleščino (Združene države). [Naučite se spremeniti območno nastavitev namizne datoteke Power BI](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop).

[!INCLUDE [footer-include](includes/footer-banner.md)]