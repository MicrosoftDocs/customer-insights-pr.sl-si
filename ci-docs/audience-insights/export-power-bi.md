---
title: Povezovalnik Power BI
description: Seznanite se z uporabo povezovalnika Dynamics 365 Customer Insights v storitvi Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0607a4644ac7d7beb19e4faecf012efcd197d48c
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477108"
---
# <a name="connector-for-power-bi-preview"></a>Povezovalnik za Power BI (predogled)

Ustvarite vizualizacije svojih podatkov s storitvijo Power BI Desktop. Ustvarite dodatne vpoglede in poročila s svojimi poenotenimi podatki o strankah.

## <a name="prerequisites"></a>Zahteve

- Imate poenotene profile strank.
- Najnovejša različica storitve [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) je nameščena v računalnik. [Preberite več o storitvi Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfiguracija povezovalnika za Power BI

1. V storitvi Power BI Desktop izberite možnost **Datoteka** > **Pridobi podatke**.

1. Izberite **Prikaži več** in poiščite storitev **Dynamics 365 Customer Insights**

1. Izberite **Vzpostavljanje povezave**.

1. Opravite **Vpis** z enakim računom organizacije, ki ga uporabljate za storitev Customer Insights, in izberite možnost **Poveži**.
   > [!NOTE]
   > Račun, ki ga navedete v tem koraku, se uporablja za pridobivanje podatkov iz storitve Customer Insights in ni nujno enak tistemu, v katerega ste prijavljeni v Power BI. Če želite ponastaviti račun, ki se uporablja za pridobivanje podatkov, odprite Power BI in izberite **Datoteka** > **Možnosti** > **Nastavitve** > **Nastavitve vira podatkov**. Na seznamu virov podatkov izberite **Prijava v Dynamics 365 Customer Insights** in izberite **Počisti dovoljenja**.  

1. V pogovornem oknu **Krmilnik**. Prikazan je seznam vseh okolij, do katerih imate dostop. Razširite okolje in odprite katero koli mapo (entitete, mere, segmenti, obogatitve). Odprite na primer mapo **Entitete** za ogled vseh entitet, ki jih lahko uvozite.

   ![Krmilnik povezovalnika storitve Power BI](media/power-bi-navigator.png "Krmilnik povezovalnika storitve Power BI")

1. Izberite potrditvena polja poleg entitet, ki jih želite vključiti, in nato **Naloži**. Izberete lahko več entitet iz več okolij.

1. Med nalaganjem entitet bo prikazano pogovorno okno za nalaganje. Ko se naložijo vse vaše izbrane entitete, lahko uporabite zmožnosti Power BI za vizualizacijo podatkov.

## <a name="large-data-sets"></a>Obsežni nabori podatkov

Povezovalnik Customer Insights za Power BI je zasnovan tako, da deluje za nabore podatkov, ki imajo do 1 milijona profilov strank. Uvoz večjih naborov podatkov lahko deluje, vendar traja dolgo. Poleg tega lahko zaradi omejitev storitve Power BI pride do časovnih omejitev. Za več informacij glejte [Power BI: priporočila za obsežne nabore podatkov](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Delo s podmnožico želenih podatkov

Razmislite o delu s podmnožico svojih podatkov. Lahko na primer ustvarite [segmente](segments.md) namesto izvoza vseh zapisov strank v storitev Power BI.

## <a name="troubleshooting"></a>Odpravljanje težav

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Okolje storitve Customer Insights se ne prikaže v storitvi Power BI

Okolja, ki imajo opredeljen več kot en [odnos](relationships.md) med dvema enakima entitetama v vpogledih v občinstvo, ne bodo na voljo v povezovalniku storitve Power BI.

Podvojene odnose lahko prepoznate in jih odstranite.

1. V vpogledih v občinstvo odprite razdelek **Podatki** > **Odnosi** za okolje, ki manjka v storitvi Power BI.
2. Prepoznajte podvojene odnose:
   - Preverite, ali je med istima entitetama določen več kot en odnos.
   - Preverite, ali je odnos ustvarjen med entitetama, ki sta vključeni v postopek poenotenja. Med vsemi entitetami, vključenimi v postopek združevanja, je določen implicitni odnos.
3. Odstranite vse prepoznane podvojene odnose.

Po odstranitvi podvojenih odnosov poskusite znova konfigurirati povezovalnik storitve Power BI. Okolje bi moralo biti zdaj na voljo.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

