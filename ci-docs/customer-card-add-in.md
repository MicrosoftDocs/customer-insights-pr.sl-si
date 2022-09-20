---
title: Dodatek kartice stranke za aplikacije Dynamics 365 (predogled) (vsebuje video)
description: S tem dodatkom prikažite podatke o profilu stranke iz storitve Customer Insights v aplikacijah Dynamics 365.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: 65fd80cc563b8b3b8c8874b66f179f8b0c7a19f0
ms.sourcegitcommit: fe33cc76d015232ff8737f77193f44f2b884bb6b
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473662"
---
# <a name="customer-card-add-in-for-dynamics-365-apps-preview"></a>Dodatek kartice stranke za aplikacije Dynamics 365 (predogled)

Pridobite 360-stopinjski pogled svojih strank neposredno v aplikacijah Dynamics 365. Če je v podprti aplikaciji Dynamics 365 nameščen dodatek za kartico stranke, lahko izberete prikaz polj profila strank, vpogledov in časovnice dejavnosti. Dodatek bo pridobil podatke iz Customer Insights, ne da bi to vplivalo na podatke v povezani aplikaciji Dynamics 365.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Zahteve

- Aplikacije Dynamics 365, ki temeljijo na modelu, kot je Sales ali storitve za stranke, različica 9.0 in novejše.
- Če želite, da se vaši podatki Dynamics 365 preslikajo v profile strank Customer Insights, priporočamo, da [zaužito iz aplikacije Dynamics 365 z uporabo Microsoft Dataverse priključek](connect-power-query.md). Če uporabljate drug način za vnos stikov (ali računov) Dynamics 365, se prepričajte, da je`contactid` (oz. `accountid`) polje je nastavljeno kot [primarni ključ za ta vir podatkov med postopkom združevanja podatkov](map-entities.md#select-primary-key-and-semantic-type-for-attributes).
- Vsi uporabniki Dynamics 365 dodatka za kartico stranke morajo biti [dodani kot uporabniki](permissions.md) v Customer Insights, da si ogledate podatke.
- [Konfigurirane zmogljivosti iskanja in filtriranja](search-filter-index.md) v storitvi Customer Insights.
- Nekateri podatki in kontrolniki so na voljo samo v okoljih določenih vrst. Konfiguracija dodatka vas bo obvestila, če kontrolnik ni na voljo zaradi izbrane vrste okolja. Ta napaka bo prikazana v kontrolniku pri upodabljanju. Več informacij o [primerih uporabe okolja](work-with-business-accounts.md).
- Vsak kontrolnik dodatka se opira na določene podatke v Customer Insights.
  - **Nadzor meritev** zahteva [konfigurirane mere atributov strank](measures.md).
  - **Obveščevalni nadzor** zahteva podatke, ustvarjene z uporabo [napovedi ali modeli po meri](predictions-overview.md).
  - **Nadzor podrobnosti o stranki** prikazuje vsa polja iz profila, ki so na voljo v enotnem profilu stranke.
  - **Nadzor obogatitve** zahteva aktivno [obogatitve](enrichment-hub.md) uporabljeno za profile strank. Dodatek kartice podpira te obogatitve: [Blagovne znamke](enrichment-microsoft.md) zagotavlja Microsoft, [Zanimanja](enrichment-microsoft.md) ki jih zagotavlja Microsoft, in [Podatki o zaposlitvi v pisarni](enrichment-office.md) zagotavlja Microsoft.
  - **Nadzor stikov** zahteva vrsto semantične entitete stika.
  - **Nadzor časovnice** zahteva [konfigurirane dejavnosti](activities.md).

## <a name="install-the-customer-card-add-in"></a>Namestitev dodatka za kartice strank

Dodatek za kartico stranke je rešitev za aplikacije za sodelovanje s strankami v rešitvi Dynamics 365. Za namestitev rešitve:

1. Pojdi do AppSource in iskati **Kartica stranke Dynamics**.

1. Izberite [dodatek za kartice strank v trgovini AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) in izberite **Prenesi zdaj**.

Morda se boste morali vpisati s svojimi skrbniškimi poverilnicami za aplikacijo Dynamics 365, da boste lahko namestili rešitev. Namestitev rešitve v vaše okolje lahko traja nekaj časa.

## <a name="configure-the-customer-card-add-in"></a>Konfiguriranje dodatka za kartico stranke

1. Kot skrbnik pojdite v razdelek **Nastavitve** v storitvi Dynamics 365 in izberite **Rešitve**.

1. Izberite povezavo **Prikazno ime** za rešitev dodatka kartice za stranke za **Dynamics 365 Customer Insights (predogled)**.

   > [!div class="mx-imgBorder"]
   > ![Izberite prikazano ime.](media/select-display-name.png "Izberite prikazano ime.")

1. Izberite **Vpis** in vnesite poverilnice za skrbniški račun, ki ga uporabljate za konfiguriranje storitve Customer Insights.

   > [!NOTE]
   > Preverite, ali preprečevalnik pojavnih oken v brskalniku ne blokira okna za preverjanje pristnosti, ko izberete gumb **Vpis**.

1. Izberite okolje storitve Customer Insights, iz katerega želite pridobiti podatke.

1. Določite preslikavo polj v zapise v aplikaciji Dynamics 365. Glede na vaše podatke v rešitvi Customer Insights lahko preslikate naslednje možnosti:
   - Če želite preslikavo opraviti s stikom, izberite polje pri entiteti stranke, ki se ujema z ID-jem entitete stika.
   - Če želite preslikavo opraviti s stranko, izberite polje pri entiteti stranke, ki se ujema z ID-jem entitete kupca.

   > [!div class="mx-imgBorder"]
   > ![Polje ID-ja stika.](media/contact-id-field.png "Polje ID-ja stika.")

1. Če želite shraniti nastavitve, izberite **Shrani konfiguracijo**.

1. Nato morate v storitvi Dynamics 365 dodeliti varnostne vloge, da lahko uporabniki prilagodijo in si ogledajo kartico stranke. V storitvi Dynamics 365 odprite **Nastavitve** > **Varnost** > **Uporabniki**. Izberite uporabnike za urejanje vlog in izberite možnost **Upravljanje vlog**.

1. Dodelite vlogo **Prilagojevalec kartic v Customer Insights** uporabnikom, ki bodo prilagajali vsebino, prikazano na kartici, za celo organizacijo.

## <a name="add-customer-card-controls-to-forms"></a>Dodajanje kontrolnikov kartic strank v obrazce

Glede na vaš primer se lahko odločite, da dodate kontrolnike v obrazec **Stik** ali obrazec **Račun**. Če je vaše okolje Customer Insights namenjeno poslovnim računom, priporočamo, da dodate kontrolnike obrazcu Račun. V tem primeru »stik« v spodnjih korakih zamenjajte z »računom«

1. Če želite v obrazec za stik dodati kontrolnike kartice stranke, v storitvi Dynamics 365 odprite **Nastavitve** > **Prilagoditve**.

1. Izberite **Prilagajanje sistema**.

1. Z brskanjem se pomaknite do entitete **Stik**, jo razširite in izberite možnost **Obrazci**.

1. Izberite obrazec za stik, v katerega želite dodati kontrolnike kartice kupca.

    > [!div class="mx-imgBorder"]
    > ![Izberite obrazec stika.](media/contact-active-forms.png "Izbira obrazca za stik.")

1. Če želite dodati kontrolnik, povlecite poljubno polje iz možnosti **Raziskovalec polj** na želeno mesto za kontrolnik.

1. Na obrazcu izberite polje, ki ste ga pravkar dodali, in izberite **Spremeni lastnosti**.

1. Odprite zavihek **Kontrolniki** in izberite **Dodaj kontrolnik**. Izberite enega od razpoložljivih kontrolnikov po meri in izberite **Dodaj**.

1. V pogovornem oknu **Lastnosti polja** počistite potrditveno polje **Prikaži oznako na obrazcu**.

1. Izberite možnost **Splet** za kontrolnik. Za kontrolnik obogatitve izberite vrsto obogatitve, ki jo želite prikazati, in sicer tako, da konfigurirate polje **enrichmentType**. Za vsako vrsto obogatitve dodajte ločen kontrolnik obogatitve.

1. Izberite **Shrani** in **Objavi**, da objavite posodobljeni obrazec za stik.

1. Pojdite na objavljeni obrazec za stik. Novo dodani kontrolnik bo prikazan. Morda se boste morali prijaviti, ko ga boste prvič uporabili.

1. Če želite prilagoditi prikaz na kontrolniku po meri, v zgornjem desnem kotu izberite gumb za urejanje.

## <a name="upgrade-customer-card-add-in"></a>Nadgraditev dodatka za kartico stranke

Dodatek za kartico stranke se ne nadgradi samodejno. Če želite nadgraditi na najnovejšo različico, sledite tem korakom v aplikaciji Dynamics 365, v kateri je nameščen dodatek.

1. V aplikaciji Dynamics 365 odprite razdelek **Nastavitve** > **Prilagajanje** in izberite možnost **Rešitve**.

1. V tabeli dodatkov poiščite **CustomerInsightsCustomerCard** in izberite vrstico.

1. V vrstici z dejanji izberite možnost **Uporabi nadgradnjo rešitve**.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Nadgradite rešitev na območju za prilagoditve v aplikacijah Dynamics 365.":::

1. Po začetku postopka nadgradnje je do zaključka prikazan kazalnik stanja nalaganja. Če novejše različice ni, se pri nadgradnji prikaže sporočilo o napaki.

## <a name="troubleshooting"></a>Odpravljanje težav

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>Kontrolniki iz dodatka kartice stranke ne najdejo podatkov

**Težava:**

Tudi s pravilno konfiguriranimi ID polji kontrolniki ne najdejo podatkov za nobeno stranko.  

**Rešitev:**

1. Preverite, ali ste dodatek kartice konfigurirali v skladu z navodili: [Konfigurirajte dodatek kartice stranke](#configure-the-customer-card-add-in)

1. Preglejte konfiguracijo vnosa podatkov. Uredite vir podatkov za sistem Dynamics 365, ki vsebuje ID stika GUID. Če je ID stika GUID prikazan z velikimi črkami v Power Query urednik, poskusite naslednje korake:
    1. Uredite vir podatkov, da odprete vir podatkov v Power Query Urednik.
    1. Izberite stolpec ID stika.
    1. Izberite **Preobrazba** v naslovni vrstici, da vidite razpoložljiva dejanja.
    1. Izberite **male črke**. Preverite, ali so GUID-ji v tabeli zdaj napisani z malimi črkami.
    1. Shranite vir podatkov.
    1. Zaženite procese vnosa podatkov, poenotenja in nižje, da razširite spremembe v GUID.

Ko je sistem dokončal popolno osvežitev, bi morali kontrolniki dodatka kartice stranke prikazati pričakovane podatke.

[!INCLUDE [footer-include](includes/footer-banner.md)]
