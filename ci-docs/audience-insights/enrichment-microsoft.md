---
title: Obogatitev profilov strank s podatki družbe Microsoft
description: Uporabite lastniške podatke družbe Microsoft, da obogatite podatke o strankah z priljubljenostjo znamk in zanimanj.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 45c81a037258e42d8975e0372c104865a9d4cbfe
ms.sourcegitcommit: 2acda3c5adf40bc3f5bbb4b2b4b6c22f84371da7
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466644"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Obogatitev profilov strank s podatki o afiniteti do blagovnih znamk in zanimanj (predogled)

Uporabite Microsoftove lastniške podatke, da obogatite podatke o strankah z priljubljenostjo znamk in zanimanj. Te afinitete temeljijo na podatkih oseb iz podobne demografske skupine kot vaše stranke. Te informacije vam pomagajo bolje razumeti in segmentirati vaše stranke na podlagi njihovih afinitet do določenih blagovnih znamk in zanimanj.

V vpogledih v občinstvo odprite razdelek **Podatki** > **Obogatitev**, da [konfigurirate in si ogledate obogatitve](enrichment-hub.md).

Če želite konfigurirati obogatitev priljubljenih blagovnih znamk, se pomaknite na zavihek **Odkrivanje** in izberite **Obogatitev podatkov** na ploščici **Blagovne znamke**.

Če želite konfigurirati obogatitev priljubljenih zanimanj, se pomaknite na zavihek **Odkrivanje** in izberite **Obogatitev podatkov** na ploščici **Zanimanja**.

   > [!div class="mx-imgBorder"]
   > ![Ploščici Blagovne znamke in Zanimanja.](media/BrandsInterest-tile-Hub.png "Ploščici Blagovne znamke in Zanimanja")

## <a name="how-we-determine-affinities"></a>Določitev priljubljenosti

Microsoftove podatke o spletnih iskanjih uporabljamo za ugotavljanje priljubljenosti blagovnih znamk in interesov v različnih demografskih segmentih (opredeljenih s starostjo, spolom ali lokacijo). Obseg spletnega iskanja blagovne znamke ali zanimanja določa raven afinitete do blagovnih znamk ali zanimanj v posameznem demografskem segmentu v primerjavi z drugimi segmenti.

## <a name="affinity-level-and-score"></a>Stopnja afinitete in ocena

Za vsak obogateni profil stranke zagotavljamo dve povezani vrednosti: stopnjo afinitete in oceno afinitete. Te vrednosti vam pomagajo ugotoviti, kako močna je afiniteta demografskega segmenta tega profila za blagovno znamko ali zanimanje v primerjavi z drugimi demografskimi segmenti.

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

Če želite izbrati državo ali regijo, odprite **Obogatitev blagovnih znamk** ali **Obogatitev interesov** in izberite možnost **Spremeni** poleg možnost **Država/regija**. V podoknu **Nastavitve države/regije** izberite možnost in izberite ukaz **Uporabi**.

### <a name="implications-related-to-country-selection"></a>Posledice, povezane z izbiro države/regije

- Pri [izbiri lastnih blagovnih znamk](#define-your-brands-or-interests) sistem ponuja predloge glede na izbrano državo ali regijo.

- Pri [izbiri panoge](#define-your-brands-or-interests) boste pridobili najbolj ustrezne blagovne znamke ali interese glede na izbrano državo oziroma regijo.

- Med [obogatitvijo profilov](#refresh-enrichment) bomo obogatili vse profile strank, za katere dobimo podatke za izbrane blagovne znamke in interese, vključno s profili, ki niso v izbrani državi ali regiji. Če na primer izberete Nemčijo, bomo obogatili profile iz Združenih državah Amerike, če imamo na voljo podatke o izbranih blagovnih znamkah in interesih v ZDA.

## <a name="configure-enrichment"></a>Konfigurirajte obogatitev

Pri konfiguriranju obogatitev vam pomaga vodena izkušnja. 

### <a name="define-your-brands-or-interests"></a>Določite svoje blagovne znamke ali zanimanja

Izberite do pet blagovnih znamk ali zanimanj z izbiro ene ali obeh možnosti:

- **Panoga**: Na spustnem seznamu izberite svojo panogo, nato pa izbirajte med najboljšimi blagovnimi znamkami ali zanimanji za to panogo.
- **Izberite svojo**: vnesite blagovno znamko ali zanimanje, ki je relevantno za vašo organizacijo, in nato izberite enega izmed predlogov ujemanja. Če med predlogi ni blagovne znamke ali zanimanja, ki ga iščete, nam pošljite povratne informacije prek povezave **Predlagaj**.

### <a name="review-enrichment-preferences"></a>Pregled nastavitev obogatitve

Preglejte privzete nastavitve obogatitve in jih po potrebi posodobite.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Posnetek zaslona okna z nastavitvami obogatitve.":::

### <a name="select-entity-to-enrich"></a>Izberite entiteto za obogatitev

Izberite možnost **Obogatena entiteta** in izberite nabor podatkov, ki ga želite obogatiti s podatki podjetja družbe Microsoft. Izberete lahko entiteto Stranka, da obogatite vse vaše profile strank, ali entiteto segmenta, da obogatite samo profile strank, ki jih vsebuje ta segment.

### <a name="map-your-fields"></a>Preslikajte polja

Preslikajte polja iz enotne entitete stranke, da določite demografski segment, ki ga mora sistem uporabiti za obogatitev podatkov o strankah. Preslikajte vrednosti za državo/regijo in vsaj datum rojstva ali spol. Poleg tega morate preslikati vsaj en atribut za mesto (in državo/območje) ali poštno številko. Izberite **Uredi**, da določite preslikavo polj, in izberite **Uporabi**, ko končate. Izberite **Shrani** za dokončanje preslikave polj.

Podprti so naslednji formati in vrednosti (vrednosti ne razlikujejo med velikimi in malimi črkami):

- **Datum rojstva**: priporočamo, da se datum rojstva med uvozom podatkov pretvori v vrsto DateTime. Lahko pa gre za niz v standardu [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html), in sicer v obliki »llll-MM-dd« ali »llll-MM-ddTHH: mm: ss«.
- **Spol**: moški, ženski, neopredeljen.
- **Poštna številka**: za ZDA veljajo petmestne poštne številke, za druge države pa standardne poštne številke.
- **Mesto**: ime mesta v angleščini.
- **Država/provinca**: dvočrkovna okrajšava za ZDA in Kanado. Dvo- ali tričrkovna okrajšava za Avstralijo. Ne velja za Francijo, Nemčijo ali Združeno kraljestvo.
- **Država/regija**:

  - ZDA: Združene države Amerike, Združene države, ZDA, Amerika
  - CA: Kanada, CA
  - GB: Združeno kraljestvo, Velika Britanija, Združeno kraljestvo Velike Britanije in Severne Irske, Združeno kraljestvo Velike Britanije
  - AU: Avstralija, AU, Avstralska zveza
  - FR: Francija, FR, republika Francija
  - DE: Nemčija, Zvezna republika Nemčija, Republika Nemčija

## <a name="review-and-name-the-enrichment"></a>Pregled in poimenovanje obogatitve

Na koncu morate pregledati podatke in navesti ime obogatitve.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Stran za pregled in poimenovanje interesov.":::

## <a name="refresh-enrichment"></a>Osvežite obogatitev

Zaženite obogatitev po tem, ko konfigurirate blagovne znamke, zanimanja in preslikavo polj za demografske skupine. Če želite začeti postopek, na strani za konfiguracijo blagovne znamke ali zanimanja izberite **Zagon**. Poleg tega lahko pustite, da sistem samodejno zažene obogatitev kot del načrtovane osvežitve.

Glede na velikost podatkov o strankah lahko postopek obogatitve traja nekaj minut.

> [!TIP]
> Na voljo je [šest vrst stanja](system.md#status-types) za opravila/postopke. Poleg tega je večina postopkov [odvisna od drugih nadaljnjih postopkov](system.md#refresh-policies). Izberete lahko stanje postopka in si ogledate podrobnosti o poteku celotnega posla. Ko za eno izmed opravil izberete možnost **Prikaži podrobnosti**, boste lahko dostopali do naslednjih dodatnih informacij: čas obdelave, datum zadnjega poskusa obdelave ter vse napake in opozorila, povezana z nalogo.

## <a name="enrichment-results"></a>Rezultati obogatitve

Po zagonu postopka obogatitve odprite razdelek **Moje obogatitve** in preglejte skupno število obogatenih strank ter razčlenitev blagovnih znamk in zanimanj obogatenih profilih strank.

:::image type="content" source="media/my-enrichments.png" alt-text="Predogled rezultatov po zagonu postopka obogatitve.":::

Preglejte obogatene podatke tako, da v grafikonu izberete možnost **Ogled obogatenih podatkov**. Obogateni podatki za blagovne znamke so poslani v entiteto **BrandAffinityFromMicrosoft**. Podatki za zanimanje so v entiteti **InteresAffinityFromMicrosoft**. Te entitete boste našli navedene tudi v skupini **Obogatitev** v **Podatki** > **Entitete**.

Prikazal se bo grafikon s številom obogatenih profilov strank v določenem obdobju in predogledna različica obogatene entitete. Izberite **Pokaži več** v ploščici za predogled, da odprete obogateno entiteto.

## <a name="see-enrichment-data-on-the-customer-card"></a>Glejte podatke o obogatitvi na kartici stranke

Afinitete do blagovnih znamk in interesov si je mogoče ogledati tudi na posameznih karticah strank. Odprite možnost **Stranke** in izberite profil stranke. Na kartici stranke boste našli grafikone blagovnih znamk ali zanimanj, ki so priljubljeni pri osebah v demografskem profilu stranke.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kartica stranke z obogatenimi podatki.":::

## <a name="next-steps"></a>Naslednji koraki

Nadgradite svoje obogatene podatke o strankah. Ustvarite [segmente](segments.md) in [mere](measures.md) ter celo [izvozite podatke](export-destinations.md) in tako svojim strankam zagotovite prilagojeno izkušnjo.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
