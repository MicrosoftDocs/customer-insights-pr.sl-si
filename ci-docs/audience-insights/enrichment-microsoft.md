---
title: Obogatitev profilov strank s podatki družbe Microsoft
description: Uporabite Microsoftove lastniške podatke, da obogatite svoje podatke o strankah z afinitetami in Delež prisotnosti.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 12704ec46832e9463e6115db6c4df64e72bf4f97
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/02/2022
ms.locfileid: "8372709"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Obogatite profile strank z afinitetami in Delež prisotnosti (predogled)

Uporabite Microsoftove lastniške podatke, da obogatite svoje podatke o strankah z afinitetami blagovnih znamk, interesnimi afinitetami in Delež prisotnosti (SoV). Te afinitete in SoV temeljijo na podatkih ljudi s podobnimi demografskimi podatki kot vaše stranke. Te informacije vam pomagajo bolje razumeti in segmentirati svoje stranke glede na njihove afinitete ali SoV do določenih blagovnih znamk in interesov.

V vpogledih v občinstvo odprite razdelek **Podatki** > **Obogatitev**, da [konfigurirate in si ogledate obogatitve](enrichment-hub.md).

Če želite konfigurirati afinitete blagovne znamke in obogatitev SoV, pojdite na **Odkrij** zavihek in izberite **Obogatite moje podatke** na **Blagovne znamke** ploščice.

Če želite konfigurirati interesne afinitete in obogatitev SoV, pojdite na **Odkrij** zavihek in izberite **Obogatite moje podatke** na **Zanimanja** ploščice.

   > [!div class="mx-imgBorder"]
   > ![Ploščici Blagovne znamke in Zanimanja.](media/BrandsInterest-tile-Hub.png "Ploščici Blagovne znamke in Zanimanja")

## <a name="how-we-determine-affinities-and-sov"></a>Kako ugotavljamo afinitete in SoV

Microsoftove podatke spletnega iskanja uporabljamo za iskanje afinitet in SoV za blagovne znamke in interese v različnih demografskih segmentih (opredeljenih glede na starost, spol ali lokacijo). Obseg spletnega iskanja za blagovno znamko ali zanimanje je osnova za določanje afinitete ali SoV. Vendar pa vsak ponuja drugačno perspektivo za razumevanje vaših strank.

- Afiniteta je primerjava med demografskimi segmenti. Te podatke lahko uporabite za prepoznavanje demografskih segmentov, ki imajo največjo afiniteto do določene blagovne znamke ali zanimanja v primerjavi z drugimi segmenti.

- Delež prisotnosti je primerjava med vašimi izbranimi blagovnimi znamkami ali zanimanji. S temi informacijami lahko ugotovite, katera blagovna znamka ali zanimanje ima najvišji delež glasov za določen demografski segment v primerjavi z drugimi blagovnimi znamkami ali zanimanji, ki ste jih izbrali.

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

## <a name="share-of-voice-sov"></a>Delež prisotnosti (SoV)

SoV izračunamo na 100-točkovni lestvici. Skupni SoV za vse blagovne znamke ali interese za vsak obogateni profil stranke znaša do 100. Za razliko od afinitet je SoV sorazmeren z blagovnimi znamkami in interesi, ki jih izberete. Vrednosti SoV za 'Microsoft' so lahko na primer drugačne, če so izbrane blagovne znamke ('Microsoft', 'GitHub') in ('Microsoft', 'LinkedIn').

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

Izberite **Obogatena entiteta** in izberite nabor podatkov, ki ga želite obogatiti s podatki iz Microsofta. Izberete lahko entiteto Stranka, da obogatite vse vaše profile strank, ali entiteto segmenta, da obogatite samo profile strank, ki jih vsebuje ta segment.

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

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Rezultati obogatitve

Po zagonu postopka obogatitve odprite razdelek **Moje obogatitve** in preglejte skupno število obogatenih strank ter razčlenitev blagovnih znamk in zanimanj obogatenih profilih strank.

:::image type="content" source="media/my-enrichments.png" alt-text="Predogled rezultatov po zagonu postopka obogatitve.":::

Našli boste grafikon s številom obogatenih profilov strank skozi čas in predogledi obogatenih entitet. Preglejte obogatene podatke z izbiro **Poglej več** v **Raven afinitete** oz **Delež prisotnosti** grafikoni. Obogateni podatki za blagovne znamke gredo v **BrandAffinityFromMicrosoft** in **BrandShareOfVoiceFromMicrosoft** subjekti. Podatki za interese so v **InterestAffinityOd Microsofta** in **InterestShareOfVoiceFromMicrosoft** subjekti. Te entitete boste našli navedene tudi v skupini **Obogatitev** v **Podatki** > **Entitete**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Glejte podatke o obogatitvi na kartici stranke

Blagovna znamka in interes SoV si lahko ogledate tudi na posameznih karticah strank. Odprite možnost **Stranke** in izberite profil stranke. V kartici stranke boste našli grafikone za blagovno znamko ali zanimanje SoV na podlagi ljudi v demografskem profilu te stranke.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kartica stranke z obogatenimi podatki.":::

## <a name="next-steps"></a>Naslednji koraki

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
