---
title: Obogatite profile strank z storitvijo Microsoft Graph
description: Uporabite lastniške podatke iz orodja Microsoft Graph, če želite obogatiti podatke o strankah s podatki o afiniteti do blagovnih znamk in zanimanj.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2c95369c778f592bc1460799aca0fa8cff813d68
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269350"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Obogatitev profilov strank s podatki o afiniteti do blagovnih znamk in zanimanj (predogled)

Uporabite lastniške podatke iz orodja Microsoft Graph, če želite obogatiti podatke o strankah s podatki o afiniteti do blagovnih znamk in zanimanj. Te afinitete so določene na podlagi podatkov ljudi s podobno demografijo, kot jo imajo vaše stranke. Te informacije vam pomagajo bolje razumeti in segmentirati vaše stranke na podlagi njihovih afinitet do določenih blagovnih znamk in zanimanj.

V vpogledih v občinstvo odprite razdelek **Podatki** > **Obogatitev**, da [konfigurirate in si ogledate obogatitve](enrichment-hub.md).

Če želite konfigurirati obogatitev priljubljenih blagovnih znamk, se pomaknite na zavihek **Odkrivanje** in izberite **Obogatitev podatkov** na ploščici **Blagovne znamke**.

Če želite konfigurirati obogatitev priljubljenih zanimanj, se pomaknite na zavihek **Odkrivanje** in izberite **Obogatitev podatkov** na ploščici **Zanimanja**.

   > [!div class="mx-imgBorder"]
   > ![Ploščice z blagovnimi znamkami in zanimanji](media/BrandsInterest-tile-Hub.png "Ploščice z blagovnimi znamkami in zanimanji")

## <a name="about-microsoft-graph"></a>O orodju Microsoft Graph

Podatke spletnega iskanja iz orodja Microsoft Graph uporabljamo za iskanje podatkov o afiniteti do blagovnih znamk in zanimanj v različnih demografskih segmentih (glede na starost, spol ali lokacijo). Obseg spletnega iskanja blagovne znamke ali zanimanja določa raven afinitete do blagovnih znamk ali zanimanj v posameznem demografskem segmentu v primerjavi z drugimi segmenti.

[Več informacij o orodju Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="affinity-level-and-score"></a>Stopnja afinitete in ocena

Za vsak obogateni profil stranke zagotavljamo dve povezani vrednosti – stopnjo afinitete in oceno afinitete. Te vrednosti vam pomagajo ugotoviti, kako močna je afiniteta demografskega segmenta tega profila za blagovno znamko ali zanimanje v primerjavi z drugimi demografskimi segmenti.

*Stopnja afinitete* je sestavljena iz štirih stopenj, *ocena afinitete* pa se izračuna na 100-stopenjski lestvici, ki se preslika v stopnje afinitete.


|Stopnja afinitete |Ocena afinitete  |
|---------|---------|
|Zelo visoka     | 85–100       |
|Velik     | 70–84        |
|Srednji     | 35–69        |
|Majhen     | 1–34        |

Glede na granularnost, ki jo želite za merjenje afinitete, lahko uporabite možnost stopnje afinitete ali ocene afinitete. Ocena afinitete omogoča natančnejši nadzor.

## <a name="supported-countriesregions"></a>Podprte države/regije

Trenutno podpiramo naslednje države/regije: Avstralija, Kanada (angleščina), Francija, Nemčija, Združeno kraljestvo ali Združene države (angleščina).

Če želite izbrati državo, odprite meni **Obogatitev blagovnih znamk** ali **Obogatitev zanimanja** in izberite možnost **Sprememba** zraven polja **Država/regija**. V podoknu **Nastavitve države/regije** izberite možnost in izberite ukaz **Uporabi**.

### <a name="implications-related-to-country-selection"></a>Posledice, povezane z izbiro države/regije

- Pri [izbiri lastnih blagovnih znamk](#define-your-brands-or-interests) sistem ponuja predloge glede na izbrano državo ali regijo.

- Pri [izbiri panoge](#define-your-brands-or-interests) boste pridobili najbolj ustrezne blagovne znamke ali interese glede na izbrano državo oziroma regijo.

- Pri [obogatitvi profilov](#refresh-enrichment) bomo obogatili vse profile strank, za katere dobimo podatke za izbrane blagovne znamke in interese. Vključno s profili, ki niso v izbrani državi ali regiji. Na primer, če ste izbrali Nemčijo, bomo obogatili profile v Združenih državah, če imamo na voljo podatke orodja Microsoft Graph za izbrane blagovne znamke in zanimanja v ZDA.

## <a name="configure-enrichment"></a>Konfiguracija obogatitve

### <a name="define-your-brands-or-interests"></a>Določite svoje blagovne znamke ali zanimanja

Izberite eno od teh možnosti:

- **Panoga**: sistem prepozna glavne blagovne znamke ali zanimanja, pomembne za vašo panogo, in z njimi obogati podatke o strankah.
- **Izberite svoje**: na seznamu blagovnih znamk ali zanimanj, ki so najbolj pomembni za vašo organizacijo, izberite največ pet elementov.

Če želite dodati blagovno znamko ali zanimanje, ga vnesite v območje za vnos, da pridobite predloge glede na ustrezne pogoje. Če med predlogi ni blagovne znamke ali zanimanja, ki ga iščete, nam pošljite povratne informacije prek povezave **Predlagaj**.

### <a name="review-enrichment-preferences"></a>Pregled nastavitev obogatitve

Preglejte privzete nastavitve obogatitve in jih po potrebi posodobite.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Posnetek zaslona okna z nastavitvami obogatitve.":::

### <a name="select-entity-to-enrich"></a>Izberite entiteto za obogatitev

Izberite možnost **Obogatena entiteta** in izberite nabor podatkov, ki ga želite obogatiti s podatki iz orodja Microsoft Graph. Izberete lahko entiteto Stranka, da obogatite vse vaše profile strank, ali entiteto segmenta, da obogatite samo profile strank, ki jih vsebuje ta segment.

### <a name="map-your-fields"></a>Preslikajte polja

Preslikajte polja iz enotne entitete stranke, da določite demografski segment, ki ga mora sistem uporabiti za obogatitev podatkov o strankah. Preslikajte vrednosti za državo/regijo in vsaj datum rojstva ali spol. Poleg tega morate preslikati vsaj en atribut za mesto (in državo/območje) ali poštno številko. Izberite **Uredi**, da določite preslikavo polj, in izberite **Uporabi**, ko končate. Izberite **Shrani** za dokončanje preslikave polj.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]