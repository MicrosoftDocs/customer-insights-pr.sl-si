---
title: Dodatek za kartico stranke za aplikacije Dynamics 365 (vsebuje video)
description: Pokažite podatke o profilu stranke iz Customer Insights v aplikacijah Dynamics 365 s tem dodatkom.
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
ms.openlocfilehash: 2dfa6c643cbe9a8531a085d8ce01b0f64776476f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643087"
---
# <a name="customer-card-add-in-preview"></a>Dodatek za kartico stranke (predogled)



Pridobite 360-stopinjski pogled svojih strank neposredno v aplikacijah Dynamics 365. Če je v podprti aplikaciji Dynamics 365 nameščen dodatek za kartico stranke, lahko izberete prikaz polj profila strank, vpogledov in časovnice dejavnosti. Dodatek bo pridobil podatke iz Customer Insights, ne da bi to vplivalo na podatke v povezani aplikaciji Dynamics 365.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Zahteve

- Dodatek deluje samo z aplikacijami Dynamics 365, ki temeljijo na modelu, na primer Sales ali Customer Service, različice 9.0 in novejše.
- Da bi se vaši podatki Dynamics 365 preslikali v profile strank Customer Insights, priporočamo, da [vneseno iz aplikacije Dynamics 365 z uporabo Microsoft Dataverse konektor](connect-power-query.md). Če za vnos stikov (ali računov) Dynamics 365 uporabljate drugačen način, se morate prepričati,`contactid` (oz`accountid`) polje je nastavljeno kot [primarni ključ za ta vir podatkov v koraku zemljevida postopka združevanja podatkov](map-entities.md#select-primary-key-and-semantic-type-for-attributes). 
- Vsi uporabniki Dynamics 365 dodatka za kartico stranke morajo biti [dodani kot uporabniki](permissions.md) v Customer Insights, da si ogledate podatke.
- [Konfigurirane zmožnosti iskanja in filtriranja](search-filter-index.md) v Customer Insights so potrebni za delovanje iskanja podatkov.
- Vsak nadzor nad dodatki se opira na določene podatke v Customer Insights. Nekateri podatki in kontrolniki so na voljo samo v okoljih določenih vrst. Konfiguracija dodatka vas bo obvestila, če kontrolnik zaradi izbrane vrste okolja ni na voljo. Več informacij o [primerih uporabe okolja](work-with-business-accounts.md).
  - **Nadzor meritev**: zahteva [konfigurirana merila](measures.md) za vrsto atributov stranke.
  - **Nadzor inteligence** : Zahteva podatke, ustvarjene z uporabo [napovedi ali modeli po meri](predictions-overview.md).
  - **Kontrolnik podrobnosti stranke**: vsa polja iz profila so na voljo v poenotenem profilu stranke.
  - **Kontrolnik obogatitve**: zahteva, da so za profile strank uporabljene aktivne [obogatitve](enrichment-hub.md). Dodatek za kartice podpira te obogatitve: [Blagovne znamke](enrichment-microsoft.md) zagotavlja Microsoft, [Zanimanja](enrichment-microsoft.md) ki ga zagotavlja Microsoft, in [Podatki o poslovanju s pisarno](enrichment-office.md) zagotavlja Microsoft.
  - **Kontrolnik stikov**: zahteva opredelitev pomenske entitete vrste stikov.
  - **Kontrolnik časovnice**: zahteva [konfigurirane dejavnosti](activities.md).

## <a name="install-the-customer-card-add-in"></a>Namestitev dodatka za kartice strank

Dodatek za kartico stranke je rešitev za aplikacije za sodelovanje s strankami v rešitvi Dynamics 365. Če želite namestiti rešitev, odprite AppSource in poiščite možnost **Kartica za stranke Dynamics**. Izberite [dodatek za kartice strank v trgovini AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) in izberite **Prenesi zdaj**.

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

Glede na vaš primer se lahko odločite, da dodate kontrolnike v obrazec **Stik** ali obrazec **Račun**. Če je vaše okolje Customer Insights za poslovne račune, priporočamo, da dodate kontrolnike v obrazec Račun. V tem primeru »stik« v spodnjih korakih zamenjajte z »računom«

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

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>Kontrolniki iz dodatka za kartico stranke ne najdejo podatkov

**Težava:**

Tudi s pravilno konfiguriranimi ID polji kontrolniki ne najdejo podatkov za nobeno stranko.  

**Rešitev:**

1. Prepričajte se, da ste konfigurirali dodatek za kartice v skladu z navodili: [Konfigurirajte dodatek za kartico stranke](#configure-the-customer-card-add-in) 

1. Preglejte konfiguracijo za vnos podatkov. Uredite vir podatkov za sistem Dynamics 365, ki vsebuje GUID ID stika. Če je ID stika GUID prikazan z velikimi črkami v Power Query urejevalnik, poskusite naslednje: 
    1. Uredite vir podatkov, da odprete vir podatkov v Power Query Urednik.
    1. Izberite stolpec ID stika.
    1. Izberite **Preoblikovanje** v vrstici glave, da si ogledate razpoložljiva dejanja.
    1. Izberite **male črke**. Preverite, ali so GUID-ji v tabeli zdaj male črke.
    1. Shranite vir podatkov.
    1. Zaženite procese vnosa podatkov, poenotenja in nadaljnjih procesov za širjenje sprememb v GUID. 

Po zaključku popolne osvežitve morajo kontrolniki dodatka za kartico stranke prikazati pričakovane podatke. 

[!INCLUDE [footer-include](includes/footer-banner.md)]