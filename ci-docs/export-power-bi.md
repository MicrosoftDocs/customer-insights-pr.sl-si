---
title: Povezovalnik storitve Power BI (predogled)
description: Seznanite se z uporabo povezovalnika Dynamics 365 Customer Insights v storitvi Power BI.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 656a695b8b3f1ec2b5fbaad69feba7f1f0b73dee
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196690"
---
# <a name="power-bi-connector-preview"></a>Povezovalnik storitve Power BI (predogled)

Ustvarite vizualizacije za svoje podatke z Microsoft Power BI Namizje. Ustvarite dodatne vpoglede in poročila s svojimi poenotenimi podatki o strankah.

## <a name="prerequisites"></a>Zahteve

- Poenoteni profili strank.
- Najnovejša različica aplikacije [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) je nameščena v vašem računalniku. [Preberite več o storitvi Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfiguracija povezovalnika za Power BI

1. V storitvi Power BI Desktop izberite možnost **Datoteka** > **Pridobi podatke**.

1. Izberite **Prikaži več** in poiščite storitev **Dynamics 365 Customer Insights**

1. Izberite **Vzpostavljanje povezave**.

1. Opravite **Vpis** z enakim računom organizacije, ki ga uporabljate za storitev Customer Insights, in izberite možnost **Poveži**.
   > [!NOTE]
   > Račun, ki ga navedete v tem koraku, se uporablja za pridobivanje podatkov iz storitve Customer Insights in ni nujno enak tistemu, v katerega ste prijavljeni v Power BI. Če želite ponastaviti račun, ki se uporablja za pridobivanje podatkov, odprite Power BI in izberite **Datoteka** > **Možnosti** > **Nastavitve** > **Nastavitve vira podatkov**. Na seznamu virov podatkov izberite **Prijava v Dynamics 365 Customer Insights** in izberite **Počisti dovoljenja**.  

1. V **Navigator** pogovornem oknu si oglejte seznam vseh okolij, do katerih imate dostop. Razširite okolje in odprite katero koli mapo (entitete, mere, segmenti, obogatitve). Odprite na primer mapo **Entitete** za ogled vseh entitet, ki jih lahko uvozite.

   :::image type="content" source="media/power-bi-navigator.png" alt-text="Krmilnik povezovalnika storitve Power BI.":::

1. Izberite potrditvena polja poleg entitet, ki jih želite vključiti, in nato **Naloži**. Izberete lahko več entitet iz več okolij.

   Med nalaganjem entitet se prikaže pogovorno okno za nalaganje. Ko so naložene vse vaše izbrane entitete, uporabite zmožnosti Power BI za vizualizacijo podatkov.

## <a name="large-data-sets"></a>Obsežni nabori podatkov

Povezovalnik Customer Insights za Power BI je zasnovan tako, da deluje za nabore podatkov, ki imajo do 1 milijona profilov strank. Uvažanje večjih naborov podatkov morda deluje, vendar traja dolgo in lahko zaradi tega poteče časovna omejitev Power BI omejitve. Za več informacij glejte [Power BI: priporočila za obsežne nabore podatkov](/power-bi/admin/service-premium-what-is#large-datasets).

### <a name="work-with-a-subset-of-data"></a>Delo s podmnožico želenih podatkov

Razmislite o delu s podmnožico svojih podatkov. Na primer, ustvarite [segmenti](segments.md) namesto izvoza vseh zapisov strank v Power BI.

## <a name="troubleshooting"></a>Odpravljanje težav

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Okolje storitve Customer Insights se ne prikaže v storitvi Power BI

Okolja, ki imajo več kot eno [odnos](relationships.md) definiran med dvema enakima entitetama v Customer Insights, ne bo na voljo v Power BI priključek.

Identificirajte in odstranite podvojeni Odnosi.

1. Pojdi do **podatki** > **Odnosi** na okolje, v katerem pogrešaš Power BI.
1. Prepoznajte podvojene odnose:
   - Preverite, ali je med istima entitetama določen več kot en odnos.
   - Preverite, ali je odnos ustvarjen med entitetama, ki sta vključeni v postopek poenotenja. Med vsemi entitetami, vključenimi v postopek združevanja, je določen implicitni odnos.
1. Odstranite vse prepoznane podvojene odnose.

Po odstranitvi podvojenih odnosov poskusite znova konfigurirati povezovalnik storitve Power BI.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Napake v datumskih poljih pri nalaganju entitet v Power BI Desktop

Pri nalaganju entitet, ki vsebujejo polja z datumsko obliko, kot je MM/DD/LLLL, lahko naletite na napake zaradi neujemajočih se področnih oblik. To neskladje se zgodi, ko vaš Power BI Desktop je nastavljena na drug jezik kot angleščina (Združene države), ker so datumska polja v Customer Insights shranjena v ameriški obliki.

Datoteka Power BI Desktop ima eno območno nastavitev, ki se uporablja pri pridobivanju podatkov. Če želite popraviti datumske napake, [nastavite področne nastavitve datoteke .BPI](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop) v angleščino (Združene države).

[!INCLUDE [footer-include](includes/footer-banner.md)]
