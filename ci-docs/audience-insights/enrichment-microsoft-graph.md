---
title: Obogatite profile strank z storitvijo Microsoft Graph
description: Uporabite lastniške podatke iz orodja Microsoft Graph, če želite obogatiti podatke o strankah s podatki o afiniteti do blagovnih znamk in zanimanj.
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406959"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Obogatitev profilov strank s podatki o afiniteti do blagovnih znamk in zanimanj (predogled)

Uporabite lastniške podatke iz orodja Microsoft Graph, če želite obogatiti podatke o strankah s podatki o afiniteti do blagovnih znamk in zanimanj. Te afinitete so določene na podlagi podatkov ljudi s podobno demografijo, kot jo imajo vaše stranke. Te informacije vam pomagajo bolje razumeti in segmentirati vaše stranke na podlagi njihovih afinitet do določenih blagovnih znamk in zanimanj.

Pri razdelku vpogledov v občinstvo izberite **Podatki** > **Obogatitev**, da [konfigurirate in si ogledate obogatitve](enrichment-hub.md).

Če želite konfigurirati obogatitev priljubljenih blagovnih znamk, se pomaknite na zavihek **Odkrivanje** in izberite **Obogatitev podatkov** na ploščici **Blagovne znamke**.

Če želite konfigurirati obogatitev priljubljenih zanimanj, se pomaknite na zavihek **Odkrivanje** in izberite **Obogatitev podatkov** na ploščici **Zanimanja**.

   > [!div class="mx-imgBorder"]
   > ![Ploščice z blagovnimi znamkami in zanimanji](media/BrandsInterest-tile-Hub.png "Ploščice z blagovnimi znamkami in zanimanji")

## <a name="about-microsoft-graph"></a>O orodju Microsoft Graph

Podatke spletnega iskanja iz orodja Microsoft Graph uporabljamo za iskanje podatkov o afiniteti do blagovnih znamk in zanimanj v različnih demografskih segmentih (glede na starost, spol ali lokacijo). Obseg spletnega iskanja blagovne znamke ali zanimanja določa raven afinitete do blagovnih znamk ali zanimanj v posameznem demografskem segmentu v primerjavi z drugimi segmenti.

[Več informacij o orodju Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="affinity-score-and-confidence"></a>Ocena afinitete in zanesljivost

**Ocena afinitete** je izračunana na 100-točkovni lestvici, kjer 100 predstavlja segment, ki ima najvišjo afiniteto do blagovne znamke ali zanimanja.

**Zanesljivost afinitete** se izračuna tudi na 100-točkovni lestvici. Prikazuje raven zanesljivosti sistema glede prisotnosti afinitete do blagovne znamke ali zanimanje v segmentu. Raven zanesljivosti temelji na velikosti segmenta in granularnosti segmenta. Velikost segmenta določa količina podatkov, ki jih imamo za dani segment. Granularnost segmenta je določena glede na to koliko atributov (starost, spol, lokacija) je na voljo v profilu.

Ocen za vaš nabor podatkov ne normaliziramo. Posledično morda ne boste videli vseh vrednosti ocene afinitete za svoj nabor podatkov. V vaših podatkih, na primer, ni nobenega obogatenega profila stranke z oceno afinitete 100. To je mogoče, če v demografskem segmentu ni strank, ki bi za določeno blagovno znamko ali zanimanje dosegle vrednost 100.

> [!TIP]
> Ko [ustvarjate segmente](segments.md) z uporabo ocen afinitet, preglejte porazdelitev ocen afinitet za nabor podatkov, preden se odločite o primernih pragih ocene. Na primer ocena afinitete 10 se lahko smatra za pomembno v naboru podatkov, ki ima najvišjo oceno afinitete samo 25 za dano blagovno znamko ali zanimanje.

## <a name="supported-countriesregions"></a>Podprte države/regije

Trenutno podpiramo naslednje države/regije: Avstralija, Kanada (angleščina), Francija, Nemčija, Združeno kraljestvo ali Združene države (angleščina).

Če želite izbrati državo, odprite meni **Obogatitev blagovnih znamk** ali **Obogatitev zanimanja** in izberite možnost **Sprememba** zraven polja **Država/regija**. V podoknu **Nastavitve države/regije** izberite možnost in izberite ukaz **Uporabi**.

### <a name="implications-related-to-country-selection"></a>Posledice, povezane z izbiro države/regije

- Ob [izbiri lastnih blagovnih znamk](#define-your-brands-or-interests) bomo podali predloge glede na izbrano državo/regijo.

- Ko [izbirate panogo](#define-your-brands-or-interests), na podlagi izbrane države/regije prepoznamo najpomembnejše blagovne znamke ali interese.

- Če ob [preslikavi polj](#map-your-fields) država/regija ni preslikana, bomo za obogatitev profilov strank uporabili podatke orodja Microsoft Graph iz izbrane države/regije. To izbiro bomo uporabili tudi za obogatitev profilov strank, ki nimajo na voljo podatkov o državi/regiji.

- Ob [obogatitvi profilov](#refresh-enrichment) bomo obogatili vse profile strank, za katere imamo na voljo podatke orodja Microsoft Graph za izbrane blagovne znamke in zanimanja, vključno s profili, ki niso v izbrani državi/regiji. Na primer, če ste izbrali Nemčijo, bomo obogatili profile v Združenih državah, če imamo na voljo podatke orodja Microsoft Graph za izbrane blagovne znamke in zanimanja v ZDA.

## <a name="configure-enrichment"></a>Konfiguracija obogatitve

Konfiguriranje obogatitve blagovnih znamk ali zanimanj obsega dva koraka:

### <a name="define-your-brands-or-interests"></a>Določite svoje blagovne znamke ali zanimanja

Izberite eno od teh možnosti:

- **Panoga**: sistem prepozna glavne blagovne znamke ali zanimanja, pomembne za vašo panogo, in z njimi obogati podatke o strankah.
- **Izberite svoje**: na seznamu blagovnih znamk ali zanimanj, ki so najbolj pomembni za vašo organizacijo, izberite največ pet elementov.

Če želite dodati blagovno znamko ali zanimanje, ga vnesite v območje za vnos, da pridobite predloge glede na ustrezne pogoje. Če med predlogi ni blagovne znamke ali zanimanja, ki ga iščete, nam pošljite povratne informacije prek povezave **Predlagaj**.

### <a name="map-your-fields"></a>Preslikajte polja

Preslikajte polja iz svoje poenotene entitete stranke v vsaj dva atributa, da določite demografski segment, za katerega želite, da ga uporabimo za obogatitev vaših podatkov o stranki. Izberite **Uredi**, da določite preslikavo polj, in izberite **Uporabi**, ko končate. Izberite **Shrani** za dokončanje preslikave polj.

Podprti so naslednji formati in vrednosti; vrednosti niso občutljive na male in male črke:

- **Datum rojstva**: priporočamo, da se datum rojstva med uvozom podatkov pretvori v vrsto DateTime. Lahko pa je tudi niz v [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) oblika "yyyy-MM-dd" ali "yyyy-MM-ddTHH: mm: ssZ".
- **Spol**: moški, ženska, neznano
- **Poštna številka**: petmestne poštne številke za ZDA, standardne poštne številke povsod drugje
- **Mesto**: ime mesta v angleščini
- **Država/provinca**: dvočrkovna okrajšava za ZDA in Kanado. Okrajšava z dvema ali tremi črkami za Avstralijo. Ne velja za Francijo, Nemčijo ali Združeno kraljestvo.
- **Država/regija**:

  - ZDA: Združene države Amerike, Združene države, ZDA, Amerika
  - CA: Kanada, CA
  - GB: Združeno kraljestvo, Velika Britanija, Združeno kraljestvo Velike Britanije in Severne Irske, Združeno kraljestvo Velike Britanije
  - AU: Avstralija, AU, Skupnost narodov Avstralije
  - FR: Francija, FR, republika Francija
  - DE: Nemčija, Zvezna republika Nemčija, Republika Nemčija

## <a name="refresh-enrichment"></a>Osvežite obogatitev

Zaženite obogatitev po tem, ko konfigurirate blagovne znamke, zanimanja in preslikavo polj za demografske skupine. Če želite začeti postopek, na strani za konfiguracijo blagovne znamke ali zanimanja izberite **Zagon**. Poleg tega lahko pustite, da sistem samodejno zažene obogatitev kot del načrtovane osvežitve.
Glede na velikost podatkov o strankah lahko postopek obogatitve traja nekaj minut.

> [!TIP]
> Na voljo je [šest vrst stanja](system.md#status-types) za opravila/postopke. Poleg tega je večina postopkov [odvisna od drugih nadaljnjih postopkov](system.md#refresh-policies). Izberete lahko stanje postopka in si ogledate podrobnosti o poteku celotnega posla. Ko za enega izmed poslov izberete **Prikaži podrobnosti**, se prikažejo dodatne informacije: čas obdelave, zadnji datum obdelave ter vse napake in opozorila, povezana z opravilom.

## <a name="enrichment-results"></a>Rezultati obogatitve

Po zagonu postopka obogatitve odprite razdelek **Moje obogatitve** in preglejte skupno število obogatenih strank ter razčlenitev blagovnih znamk in zanimanj obogatenih profilih strank.

:::image type="content" source="media/my-enrichments.png" alt-text="Predogled rezultatov po zagonu postopka obogatitve":::

Preglejte obogatene podatke tako, da v grafikonu izberete možnost **Ogled obogatenih podatkov**. Obogateni podatki za blagovne znamke so poslani v entiteto **BrandAffinityFromMicrosoft**. Podatki za zanimanje so v entiteti **InteresAffinityFromMicrosoft**. Te entitete boste našli navedene tudi v skupini **Obogatitev** v **Podatki** > **Entitete**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Glejte podatke o obogatitvi na kartici stranke

Afinitete do blagovnih znamk in interesov si je mogoče ogledati tudi na posameznih karticah strank. Odprite možnost **Stranke** in izberite profil stranke. Na kartici stranke boste našli grafikone blagovnih znamk ali zanimanj, ki so priljubljeni pri osebah v demografskem profilu stranke.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kartica stranke z obogatenimi podatki":::

## <a name="next-steps"></a>Naslednji koraki

Nadgradite svoje obogatene podatke o strankah. Ustvarite [Segmente](segments.md), [Mere](measures.md) in celo [izvozite podatke](export-destinations.md), da svojim strankam zagotovite prilagojeno izkušnjo.
