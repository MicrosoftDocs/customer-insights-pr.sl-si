---
title: Obogatite profile strank z Microsoftovimi podatki o blagovnih znamkah in zanimanjih
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
ms.openlocfilehash: 61262980cafdcd130430e200e466ce7da6cc4d07
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953785"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Obogatite profile strank z afinitetami in Delež prisotnosti (predogled)

Uporabite Microsoftove lastniške podatke, da obogatite svoje podatke o strankah z afinitetami blagovnih znamk, interesnimi afinitetami in Delež prisotnosti (SoV). Te afinitete in SoV temeljijo na podatkih ljudi s podobnimi demografskimi podatki kot vaše stranke. Te informacije vam pomagajo bolje razumeti in segmentirati svoje stranke glede na njihove afinitete ali SoV do določenih blagovnih znamk in interesov.

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

## <a name="configure-the-enrichment"></a>Konfiguriranje obogatitve

1. Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.

   - Če želite konfigurirati afinitete blagovne znamke in obogatitev SoV, izberite **Obogatite moje podatke** na **Blagovne znamke** ploščice.

   - Če želite konfigurirati interesne afinitete in obogatitev SoV, izberite **Obogatite moje podatke** na **Zanimanja** ploščice.

   > [!div class="mx-imgBorder"]
   > ![Ploščici Blagovne znamke in Zanimanja.](media/BrandsInterest-tile-Hub.png "Ploščici Blagovne znamke in Zanimanja")

1. Preglejte pregled in nato izberite **Naslednji**.

1. Če želite spremeniti državo ali regijo, izberite **Spremeni se** zraven **Država/regija**. V podoknu **Nastavitve države/regije** izberite [podprto državo/regijo](#supported-countriesregions) in izberite **Uporabi**.

   > [!NOTE]
   > Pri izbiri lastnih blagovnih znamk sistem ponuja predloge glede na izbrano državo ali regijo. Pri izbiri panoge boste pridobili najbolj ustrezne blagovne znamke ali interese glede na izbrano državo oziroma regijo.

1. Izberite do pet blagovnih znamk ali zanimanj z izbiro ene ali obeh možnosti:

   - **Panoga**: Na spustnem seznamu izberite svojo panogo, nato pa izbirajte med najboljšimi blagovnimi znamkami ali zanimanji za to panogo.
   - **Izberite svojo**: vnesite blagovno znamko ali zanimanje, ki je relevantno za vašo organizacijo, in nato izberite enega izmed predlogov ujemanja. Če med predlogi ni blagovne znamke ali zanimanja, ki ga iščete, nam pošljite povratne informacije prek povezave **Predlagaj**.

1. Izberite **Naslednji** in preglejte svoje privzete nastavitve obogatitve ter jih po potrebi posodobite.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Posnetek zaslona okna z nastavitvami obogatitve.":::

1. Izberite **Naprej**.

1. Izberite **Stranka nabor podatkov** in izberite profil ali segment, ki ga želite obogatiti s podatki iz Microsofta. The *Stranka* entiteta obogati vse vaše profile strank, medtem ko segment obogati samo profile strank, ki jih vsebuje ta segment.

1. Izberite **Naprej**.

1. Preslikajte svoja polja iz vaše enotne stranke v Microsoftove podatke.

   > [!NOTE]
   > Zahtevani so vsaj atributi datuma rojstva ali spola. Obvezna sta država/regija in vsaj mesto (in država/provinca) ali poštna številka. Priporočamo, da se datum rojstva med vnosom podatkov pretvori v vrsto DateTime. Lahko pa gre za niz v standardu [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html), in sicer v obliki »llll-MM-dd« ali »llll-MM-ddTHH: mm: ss«.

1. Izberite možnost **Naprej**, da dokončate preslikavo polj.

1. Navedite ime obogatitve. The **Ime izhodne entitete** je samodejno izbrana.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Stran za pregled in poimenovanje interesov.":::

1. Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.

1. Izberite **teci** za začetek procesa obogatitve ali blizu vrnitve na **Obogatitve** stran.

   Med obogatitvijo profilov bomo obogatili vse profile strank, za katere dobimo podatke za izbrane blagovne znamke in interese, vključno s profili, ki niso v izbrani državi ali regiji. Če na primer izberete Nemčijo, bomo obogatili profile iz Združenih državah Amerike, če imamo na voljo podatke o izbranih blagovnih znamkah in interesih v ZDA.

## <a name="enrichment-results"></a>Rezultati obogatitve

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Predogled rezultatov po zagonu postopka obogatitve.":::

Rezultati vključujejo **Raven afinitete** oz **Delež prisotnosti** grafikoni.

Subjekti, ustvarjeni iz obogatitev, so navedeni pod **Obogatitev** skupina v **Podatki** > **Entitete**. Obogateni podatki za blagovne znamke gredo v **BrandAffinityFromMicrosoft** in **BrandShareOfVoiceFromMicrosoft** subjekti. Podatki za interese so v **InterestAffinityOd Microsofta** in **InterestShareOfVoiceFromMicrosoft** subjekti.

## <a name="see-enrichment-data-on-the-customer-card"></a>Glejte podatke o obogatitvi na kartici stranke

Blagovna znamka in interes SoV si lahko ogledate tudi na posameznih karticah strank. Odprite možnost **Stranke** in izberite profil stranke. V kartici stranke boste našli grafikone za blagovno znamko ali zanimanje SoV na podlagi ljudi v demografskem profilu te stranke.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kartica stranke z obogatenimi podatki.":::

## <a name="next-steps"></a>Naslednji koraki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
