---
title: Dodatek za kartico stranke v aplikacijah Dynamics 365
description: S tem dodatkom prikažite podatke iz vpogledov v občinstvo v aplikacijah Dynamics 365.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0f6c922104df229980b308136a4d764938121b35d6d744f41b1530bdb5515e7f
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033008"
---
# <a name="customer-card-add-in-preview"></a>Dodatek za kartico stranke (predogled)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Pridobite 360-stopinjski pogled svojih strank neposredno v aplikacijah Dynamics 365. Z dodatkom za kartico stranke, nameščenim v podprti aplikaciji Dynamics 365, lahko izberete prikaz demografskih podatkov, vpogledov in časovnic dejavnosti. Dodatek bo pridobil podatke iz Customer Insights, ne da bi to vplivalo na podatke v povezani aplikaciji Dynamics 365. 

## <a name="prerequisites"></a>Zahteve

- Dodatek deluje samo z aplikacijami Dynamics 365, ki temeljijo na modelu, na primer Sales ali Customer Service, različice 9.0 in novejše.
- Da se bodo vaši podatki iz aplikacije Dynamics 365 preslikali v profile strank za vpoglede v občinstvo, morajo biti [uvoženi iz aplikacije Dynamics 365 s priključkom Microsoft Dataverse](connect-power-query.md).
- Vsi uporabniki aplikacije Dynamics 365 in dodatka za kartice strank morajo biti za ogled podatkov [dodani kot uporabniki](permissions.md) v vpogledih v občinstvo.
- Za delovanje iskanja podatkov so zahtevane [konfigurirane možnosti iskanja in filtriranja](search-filter-index.md) v vpogledih v občinstvo.
- Vsak kontrolnik dodatka se zanaša na določene podatke v vpogledih v občinstvo:
  - Kontrolnik merjenja: zahteva [konfigurirane ukrepe](measures.md).
  - Kontrolnik obveščanja: zahteva podatke, ustvarjene z [napovedmi](predictions.md) ali [modeli po meri](custom-models.md).
  - Demografski kontrolnik: v poenotenem profilu strank so na voljo demografska polja (kot sta starost ali spol).
  - Kontrolnik obogatitve: zahteva, da so za profile strank uporabljene aktivne [obogatitve](enrichment-hub.md).
  - Kontrolnik časovnice: zahteva [konfigurirane dejavnosti](activities.md).

## <a name="install-the-customer-card-add-in"></a>Namestitev dodatka za kartice strank

Dodatek za kartico stranke je rešitev za aplikacije za sodelovanje s strankami v rešitvi Dynamics 365. Če želite namestiti rešitev, odprite AppSource in poiščite možnost **Kartica za stranke Dynamics**. Izberite [dodatek za kartice strank v trgovini AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) in izberite **Prenesi zdaj**.

Morda se boste morali vpisati s svojimi skrbniškimi poverilnicami za aplikacijo Dynamics 365, da boste lahko namestili rešitev.

Namestitev rešitve v vaše okolje lahko traja nekaj časa.

## <a name="configure-the-customer-card-add-in"></a>Konfiguriranje dodatka za kartico stranke

1. Kot skrbnik pojdite v razdelek **Nastavitve** v storitvi Dynamics 365 in izberite **Rešitve**.

1. Izberite povezavo **Prikazno ime** za rešitev dodatka kartice za stranke za **Dynamics 365 Customer Insights (predogled)**.

   > [!div class="mx-imgBorder"]
   > ![Izberite prikazano ime.](media/select-display-name.png "Izberite prikazano ime")

1. Izberite **Vpis** in vnesite poverilnice za skrbniški račun, ki ga uporabljate za konfiguriranje storitve Customer Insights.

   > [!NOTE]
   > Preverite, ali preprečevalnik pojavnih oken v brskalniku ne blokira okna za preverjanje pristnosti, ko izberete gumb **Vpis**.

1. Izberite okolje storitve Customer Insights, iz katerega želite pridobiti podatke.

1. Določite preslikavo polj v zapise v aplikaciji Dynamics 365. Glede na vaše podatke v rešitvi Customer Insights lahko preslikate naslednje možnosti:
   - Če želite preslikavo opraviti s stikom, izberite polje pri entiteti stranke, ki se ujema z ID-jem entitete stika.
   - Če želite preslikavo opraviti s stranko, izberite polje pri entiteti stranke, ki se ujema z ID-jem entitete kupca.

   > [!div class="mx-imgBorder"]
   > ![Polje ID-ja stika.](media/contact-id-field.png "Polje ID-ja stika")

1. Če želite shraniti nastavitve, izberite **Shrani konfiguracijo**.

1. Nato morate v storitvi Dynamics 365 dodeliti varnostne vloge, da lahko uporabniki prilagodijo in si ogledajo kartico stranke. V storitvi Dynamics 365 odprite **Nastavitve** > **Varnost** > **Uporabniki**. Izberite uporabnike za urejanje vlog in izberite možnost **Upravljanje vlog**.

1. Dodelite vlogo **Prilagojevalec kartic v Customer Insights** uporabnikom, ki bodo prilagajali vsebino, prikazano na kartici, za celo organizacijo.

## <a name="add-customer-card-controls-to-forms"></a>Dodajanje kontrolnikov kartic strank v obrazce
  
1. Če želite v obrazec za stik dodati kontrolnike kartice stranke, v storitvi Dynamics 365 odprite **Nastavitve** > **Prilagoditve**.

1. Izberite **Prilagajanje sistema**.

1. Z brskanjem se pomaknite do entitete **Stik**, jo razširite in izberite možnost **Obrazci**.

1. Izberite obrazec za stik, v katerega želite dodati kontrolnike kartice stranke.

    > [!div class="mx-imgBorder"]
    > ![Izberite obrazec stika.](media/contact-active-forms.png "Izbira obrazca za stik")

1. Če želite dodati kontrolnik, povlecite poljubno polje iz možnosti **Raziskovalec polj** na želeno mesto za kontrolnik.

1. Na obrazcu izberite polje, ki ste ga pravkar dodali, in izberite **Spremeni lastnosti**.

1. Odprite zavihek **Kontrolniki** in izberite **Dodaj kontrolnik**. Izberite enega od razpoložljivih kontrolnikov po meri in izberite **Dodaj**.

1. V pogovornem oknu **Lastnosti polja** počistite potrditveno polje **Prikaži oznako na obrazcu**.

1. Izberite možnost **Splet** za kontrolnik. Za kontrolnik obogatitve izberite vrsto obogatitve, ki jo želite prikazati, in sicer tako, da konfigurirate polje **enrichmentType**. Za vsako vrsto obogatitve dodajte ločen kontrolnik obogatitve.

1. Izberite **Shrani** in **Objavi**, da objavite posodobljeni obrazec za stik.

1. Pojdite na objavljeni obrazec za stik. Novo dodani kontrolnik bo prikazan. Morda se boste morali prijaviti, ko ga boste prvič uporabili.

1. Če želite prilagoditi prikaz na kontrolniku po meri, v zgornjem desnem kotu izberite gumb za urejanje.

## <a name="upgrade-customer-card-add-in"></a>Nadgraditev dodatka za kartico stranke
Dodatek za kartico stranke se ne nadgradi samodejno. Če ga želite nadgraditi na najnovejšo različico, upoštevajte navodila v aplikaciji Dynamics 365, v kateri je nameščen dodatek.

1. V aplikaciji Dynamics 365 odprite razdelek **Nastavitve** > **Prilagajanje** in izberite možnost **Rešitve**.

1. V tabeli dodatkov poiščite **CustomerInsightsCustomerCard** in izberite vrstico.

1. V vrstici z dejanji izberite možnost **Uporabi nadgradnjo rešitve**.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Nadgradite rešitev na območju za prilagoditve v aplikacijah Dynamics 365.":::

1. Po začetku postopka nadgradnje je do zaključka prikazan kazalnik stanja nalaganja. Če novejše različice ni, se pri nadgradnji prikaže sporočilo o napaki.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
