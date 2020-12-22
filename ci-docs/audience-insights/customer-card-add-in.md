---
title: Namestitev in konfiguracija dodatka za kartice strank
description: Namestite in konfigurirajte dodatek za kartico stranke za Dynamics 365 Customer Insights.
ms.date: 08/04/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: aab5deaf89b4b019f6688a1bca950ec2277ad5fb
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644063"
---
# <a name="customer-card-add-in-preview"></a>Dodatek za kartico stranke (predogled)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Pridobite 360-stopinjski pogled svojih strank neposredno v aplikacijah Dynamics 365. Z dodatkom za kartico stranke si oglejte demografske podatke, vpoglede in časovnice z dejavnostmi.

## <a name="prerequisites"></a>Zahteve

- Aplikacija Dynamics 365 (kot je Središče za prodajo ali Središče storitev za stranke), različica 9.0 in novejše z omogočenim poenotenim vmesnikom.
- Profili strank, [vključeni iz aplikacije Dynamics 365 prek storitve Common Data Service](connect-power-query.md).
- Uporabniki dodatka za kartice stranke morajo biti [dodani kot uporabniki](permissions.md) pri vpogledih v občinstvo.
- [Konfigurirane možnosti iskanja in filtriranja](search-filter-index.md).
- Demografski kontrolnik: v poenotenem profilu strank so na voljo demografska polja, kot sta starost ali spol.
- Kontrolnik obogatitve: zahteva, da so za profile strank uporabljene aktivne [obogatitve](enrichment-hub.md).
- Kontrolnik za obveščanje: zahteva podatke, ustvarjene s strojnim učenjem Azure ([modeli predvidevanja](predictions.md) ali [modeli po meri](custom-models.md))
- Kontrolnik merjenja: zahteva [konfigurirane ukrepe](measures.md).
- Kontrolnik časovnice: zahteva [konfigurirane dejavnosti](activities.md).

## <a name="install-the-customer-card-add-in"></a>Namestitev dodatka za kartice strank

Dodatek za kartico stranke je rešitev za aplikacije za sodelovanje s strankami v rešitvi Dynamics 365. Če želite namestiti rešitev, odprite AppSource in poiščite možnost **Kartica za stranke Dynamics**. Izberite [dodatek za kartice strank v trgovini AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) in izberite **Prenesi zdaj**.

Morda se boste morali vpisati s svojimi skrbniškimi poverilnicami za aplikacijo Dynamics 365, da boste lahko namestili rešitev.

Namestitev rešitve v vaše okolje lahko traja nekaj časa.

## <a name="configure-the-customer-card-add-in"></a>Konfiguriranje dodatka za kartico stranke

1. Kot skrbnik pojdite v razdelek **Nastavitve** v storitvi Dynamics 365 in izberite **Rešitve**.

1. Izberite povezavo **Prikazno ime** za rešitev dodatka kartice za stranke za **Dynamics 365 Customer Insights (predogled)**.

   > [!div class="mx-imgBorder"]
   > ![Izberite prikazano ime](media/select-display-name.png "Izberite prikazano ime")

1. Izberite **Vpis** in vnesite poverilnice za skrbniški račun, ki ga uporabljate za konfiguriranje storitve Customer Insights.

   > [!NOTE]
   > Preverite, ali preprečevalnik pojavnih oken v brskalniku ne blokira okna za preverjanje pristnosti, ko izberete gumb **Vpis**.

1. Izberite okolje, iz katerega želite pridobiti podatke.

1. Določite, katera preslikava polja se zabeleži v aplikaciji Dynamics 365.
   - Če želite preslikavo opraviti s stikom, izberite polje pri entiteti stranke, ki se ujema z ID-jem entitete stika.
   - Če želite preslikavo opraviti s stranko, izberite polje pri entiteti stranke, ki se ujema z ID-jem entitete kupca.

   > [!div class="mx-imgBorder"]
   > ![Polje ID-ja stika](media/contact-id-field.png "Polje ID-ja stika")

1. Če želite shraniti nastavitve, izberite **Shrani konfiguracijo**.

1. Nato morate v storitvi Dynamics 365 dodeliti varnostne vloge, da lahko uporabniki prilagodijo in si ogledajo kartico stranke. V storitvi Dynamics 365 odprite **Nastavitve** > **Varnost** > **Uporabniki**. Izberite uporabnike za urejanje vlog in izberite možnost **Upravljanje vlog**.

1. Dodelite vlogo **Prilagojevalec kartic v Customer Insights** uporabnikom, ki bodo prilagajali vsebino, prikazano na kartici, za celo organizacijo.

## <a name="add-customer-card-controls-to-forms"></a>Dodajanje kontrolnikov kartic strank v obrazce
  
1. Če želite v obrazec za stik dodati kontrolnike kartice stranke, v storitvi Dynamics 365 odprite **Nastavitve** > **Prilagoditve**.

1. Izberite **Prilagajanje sistema**.

1. Z brskanjem se pomaknite do entitete **Stik**, jo razširite in izberite možnost **Obrazci**.

1. Izberite obrazec za stik, v katerega želite dodati kontrolnike kartice stranke.

    > [!div class="mx-imgBorder"]
    > ![Izbira obrazca za stik](media/contact-active-forms.png "Izbira obrazca za stik")

1. Če želite dodati kontrolnik, povlecite poljubno polje iz možnosti **Raziskovalec polj** na želeno mesto za kontrolnik.

1. Na obrazcu izberite polje, ki ste ga pravkar dodali, in izberite **Spremeni lastnosti**.

1. Odprite zavihek **Kontrolniki** in izberite **Dodaj kontrolnik**. Izberite enega od razpoložljivih kontrolnikov po meri in izberite **Dodaj**.

1. V pogovornem oknu **Lastnosti polja** počistite potrditveno polje **Prikaži oznako na obrazcu**.

1. Izberite možnost **Splet** za kontrolnik. Za kontrolnik obogatitve izberite vrsto obogatitve, ki jo želite prikazati, in sicer tako, da konfigurirate polje **enrichmentType**. Za vsako vrsto obogatitve morate dodati ločen kontrolnik obogatitve.

1. Izberite **Shrani** in **Objavi**, da objavite posodobljeni obrazec za stik.

1. Pojdite na objavljeni obrazec za stik. Novo dodani kontrolnik bo prikazan. Morda se boste morali prijaviti, ko ga boste prvič uporabili.

1. Če želite prilagoditi prikaz na kontrolniku po meri, v zgornjem desnem kotu izberite gumb za urejanje.
