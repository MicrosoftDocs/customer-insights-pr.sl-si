---
title: Eksperimentiranje za studio za strojno učenje (klasični način)
description: Uporabite modele za studio za strojno učenje (klasični način) v storitvi Dynamics 365 Customer Insights.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: ameetj
manager: shellyha
ms.openlocfilehash: 8a861d62bdfee6a3a82468fe1ab4a3fbbdad43d4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270224"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Uporabite modele na podlagi studia za strojno učenje Azure (klasični način)

Združeni podatki v storitvi Dynamics 365 Customer Insights so vir za gradnjo modelov strojnega učenja, ki lahko ustvarijo dodatne vpoglede v poslovanje. Customer Insights se integrira s studiom za strojno učenje (klasični način), da lahko uporabljate lastne modele po meri. Če si želite ogledati, kako se modeli, razviti s storitvijo Strojno učenje Azure, integrirajo s storitvijo Customer Insights, glejte [Eksperimentiranje s strojnim učenjem Azure](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Zahteve

- Dostop do storitve Customer Insights
- Aktivna naročnina na storitev Azure Enterprise
- [Poenoteni profili strank](data-unification.md)
- Nastavitev [izvoza entitete v shrambo Azure Blob](export-azure-blob-storage.md)

## <a name="set-up-machine-learning-studio-classic"></a>Nastavitev studia za strojno učenje (klasični način)

V prvem koraku moramo ustvariti delovni prostor in odpreti Studio za strojno učenje (klasični način).

1. Pojdite v[https://www.portal.azure.com](https://www.portal.azure.com/) in se vpišite.

1. Izberite možnost **Ustvarjanje vira**.

1. Poiščite **Delovni prostor studia za strojno učenje** in izberite **Ustvari**.

1. Vnesite zahtevane podatke, da [ustvarite delovni prostor](https://docs.microsoft.com/azure/machine-learning/studio/create-workspace). Izberite **Cena za razred cen paketa spletne storitve** na podlagi količine podatkov, ki jih nameravate uvoziti. Za boljše delovanje izberite **Lokacija**, ki vam je geografsko najbližje.

1. Ko ste ustvarili vir, se vam bo prikazala nadzorna plošča delovnega prostora studia za strojno učenje. Izberite **Zaženi studio za strojno učenje**.

   ![Uporabniški vmesnik studia za strojno učenje Azure](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Uporaba studia za strojno učenje Azure

Zdaj lahko ustvarite nov poskus ali uvozite obstoječo predlogo poskusa iz galerije vzorcev. Na voljo je vzorčno eksperimentiranje za tri standardne scenarije:

- [Predvidevanje izgube strank](#churn-analysis)

- [Skupna vrednost stranke](#customer-lifetime-value-prediction)

- [Priporočilo izdelka ali naslednje najboljše dejanje](#productrecommendation-or-next-best-action)

1. Če ustvarite nov poskus ali uporabite predlogo poskusa iz galerije, morate konfigurirati lastnosti **Podatki za uvoz**. Uporabite vodeno izkušnjo ali neposredno navedite podrobnosti za dostop do shrambe zbirke dvojiških podatkov Azure, ki vsebuje vaše podatke.  

   ![Poskus studia za strojno učenje Azure](media/azure-machine-learning-studio-experiment.png)

1. Zdaj lahko ustvarite prodajni lijak za obdelavo po meri, s katerim lahko počistite in predobdelate podatke, izvlečete funkcije in pripravite ustrezni model.

1. Preizkusite in optimizirajte delovanje modela.

1. Ko boste zadovoljni s kakovostjo modela, izberite **Nastavitev spletne storitve** > **Spletna storitev za napovedovanje**. S to možnostjo boste uvozili pripravljeni model in prodajni lijak lastnosti iz poskusa usposabljanja v napovedno storitev. Napovedna storitev lahko sprejme tudi kak drug niz vhodnih podatkov s shemo, uporabljeno v poskusu usposabljanja za ustvarjanje napovedi.

   ![Nastavitev spletne storitve za napovedovanje](media/predictive-webservice-control.png)

1. Ko vam poskus spletne storitve za napovedovanje uspe, ga lahko uporabite za samodejno načrtovanje. Če želite uporabiti spletno storitev skupaj z aplikacijo Customer Insights, izberite **Uvedba spletne storitve** > **[Nov] predogled uvedbe spletne storitve**. [Podrobno se seznanite z uvedbo spletne storitve](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service).

   ![Uvedba spletne storitve za napovedovanje](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>Vzorčni modeli iz galerije

Za modele v tem članku bomo uporabili izmišljeni scenarij hotela Contoso. Hotel Contoso zbira naslednje podatke:

- Podatki CRM o bivanju v hotelu. Nabor podatkov vključuje podatke o datumih bivanja za vsako registrirano stranko. Vsebuje tudi informacije o rezervaciji, vrstah sob, podrobnostih o porabi in podobno. Podatki zajemajo obdobje štirih let, od januarja 2014 do januarja 2018.
- Profili strank, tj. hotelskih gostov. Ti profili vsebujejo podatke o vsaki stranki, vključno z njihovim imenom, rojstnim dnem, poštnim naslovom, spolom in telefonsko številko.
- Uporaba storitev, ki jih nudi hotel, kot so wellness center, pralnica, WiFi ali pošta. Ti podatki se beležijo za vsako registrirano stranko. Uporaba storitev je običajno povezana z bivanjem. V nekaterih primerih lahko storitve uporabljajo stranke, ne da bi bivale v hotelu.

## <a name="churn-analysis"></a>Analiza izgube strank

Analiza izgube strank se nanaša na različna poslovna področja. V tem primeru si bomo ogledali izgubo storitev, zlasti v okviru hotelskih storitev, ki so opisane zgoraj. Ponuja delovni primer celovitega modela prodajnega lijaka, ki ga je mogoče uporabiti kot izhodišče za katero koli drugo vrsto modela za izgubo.

### <a name="definition-of-churn"></a>Opredelitev izgube

Opredelitev izgube se lahko razlikuje glede na scenarij. V tem primeru je treba gosta, ki v zadnjem letu ni obiskal hotela, označiti kot izgubljenega.  

Predlogo poskusa lahko uvozite iz galerije. Najprej se prepričajte, da uvažate podatke za **Bivanje v hotelu**, **Podatki o stranki** in **Podatki o uporabi storitve** iz shrambe zbirke dvojiških podatkov Azure.

   ![Uvozi podatke za model menjavanja strank](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>Določanje lastnosti

Na podlagi opredelitve izgube moramo najprej prepoznati osnovne lastnosti, ki bodo vplivale na to oznako. Nato obdelamo osnovne lastnosti v številčne lastnosti, ki jih je mogoče uporabiti pri modelih strojnega učenja. Integracija podatkov se zgodi v storitvi Customer Insights, tako da se lahko tabelam pridružimo z uporabo možnosti *ID stranke*.

   ![Združevanje uvoženih podatkov](media/join-imported-data.png)

Določitev lastnosti za ustvarjanje modela za analizo izgube je lahko zapletena. Podatki so funkcija časa z novo dejavnostjo hotela, ki se beleži vsakodnevno. Med določanjem lastnosti želimo ustvariti statične lastnosti iz dinamičnih podatkov. V tem primeru ustvarimo več funkcij iz hotelske dejavnosti z drsnim oknom, ki označuje obdobje enega leta. Razširimo tudi kategorične lastnosti, kot sta vrsta sobe ali vrsta rezervacije, in sicer v ločene lastnosti z uporabo kodiranja z eno kategorično vrednostjo.  

Končni seznam funkcij:

| **Številka**  | **Original_Column**          | **Izpeljane funkcije**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | Vrsta sobe                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | Vrsta rezervacije                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | Kategorija potovanja              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 4           | Porabljen denar                | TotalDollarSpent                                                                                                                          |
| 5           | Datuma prijave in odjave  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | Uporaba storitve                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>Izbira modela

Zdaj moramo izbrati še optimalen algoritem, ki ga bomo uporabili. V tem primeru večina lastnosti temelji na kategoričnih lastnostih. Običajno dobro delujejo modeli, ki temeljijo na odločitvenem drevesu. Če so lastnosti izključno številčne, bi bilo morda bolje izbrati nevronsko mrežo. Metoda podpornih vektorjev (SVM) je ravno tako dobra možnost v takšnih situacijah; vendar jo je treba za optimalno delovanje kar precej prilagoditi. Kot prvi model izbire izberimo **Dvorazredno izboljšano odločitveno drevo**, kot drugi model pa **Dvorazredno metodo podpornih vektorjev**. Studio za strojno učenje Azure omogoča testiranje A/B, zato je morda bolje začeti z dvema modeloma kot z enim.

Spodnja slika prikazuje prodajni lijak modela za usposabljanje in ocenjevanje iz studia za strojno učenje Azure:

![Model izgube v studiu za strojno učenje Azure](media/azure-machine-learning-model.png)

Uporabljamo tudi tehniko, ki se imenuje **Pomembnost permutacije lastnosti** in je pomemben vidik optimizacije modelov. Vgrajeni modeli imajo malo ali nič vpogleda v vpliv katere koli posebne lastnosti na končno napoved. Kalkulator pomembnosti lastnosti uporablja algoritem po meri za izračun vpliva posameznih lastnosti na rezultat posebnega modela. Pomembnost lastnosti je normalizirana med +1 in –1. Negativen vpliv pomeni, da ima ustrezna lastnost kontraintuitiven vpliv na rezultat in jo je treba odstraniti iz modela. Pozitiven vpliv pomeni, da lastnost močno prispeva k napovedi. Te vrednosti niso korelacijski koeficienti, saj gre za drugačne metrike. Za več informacij glejte [Pomembnost lastnosti permutacije](https://docs.microsoft.com/azure/machine-learning/studio-module-reference/permutation-feature-importance).

Celoten [poskus z izgubo je na voljo v galeriji Azure AI](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp).

## <a name="customer-lifetime-value-prediction"></a>Napovedana skupna vrednost stranke

Izračun vrednosti življenjske dobe stranke (CLTV) je ena ključnih meritev, ki jo lahko podjetje uporabi za oceno in segmentiranje strank. V hotelskem poslu je poznavanje strank ključnega pomena. Ključno je na primer razumevanje dejavnikov, ki ustvarjajo dobre stranke. Vodstvo hotela tako lažje oceni, na katere funkcije se morajo osredotočiti in jih izboljšati, da bi zadovoljili svoje najpremožnejše stranke. Te odločitve lahko neposredno vplivajo na prodajo in zaslužek.  

### <a name="definition-of-cltv"></a>Opredelitev CLTV

Za ta primer bomo CLTV stranke opredelili kot skupno vsoto v dolarjih, ki naj bi jo stranka porabila v naslednjih 365 dneh. To vrednost bomo napovedali tako, da bomo uporabili podatke iz preteklih treh letih za vse stranke.

### <a name="featurization"></a>Določanje lastnosti

V tem primeru bo določanje lastnosti precej podobno scenariju z izgubo strank. Oznake in predvidene vrednosti pa so drugačne, kot je opredeljeno zgoraj.

### <a name="model-selection"></a>Izbira modela

Napovedovanje CLTV je regresijska težava, saj je predvidena vrednost neprekinjena spremenljivka s pozitivno vrednostjo. Na podlagi lastnosti funkcije izberemo **Regresijo izboljšanega odločitvenega drevesa** kot prvi algoritem in **Regresijo nevronske mreže** kot drugi algoritem za usposabljanje modela.

## <a name="product-recommendation-or-next-best-action"></a>Priporočilo izdelka ali naslednje najboljše dejanje

Priporočilo izdelka v hotelskem scenariju se razlaga kot priporočilo storitev, ki jih hotel ponuja strankam. Cilj je izbrati ustrezne storitve za stranke, da bo njihova uporaba čim večja. Podobno je s filmskimi priporočili za uporabnike storitev pretakanja video vsebin.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>Opredelitev priporočila izdelka ali naslednjega najboljšega dejanja

Cilj opredelimo kot maksimiranje uporabe storitve po dolarski vrednosti, tako da strankam hotela ponudimo njim najustreznejše storitve glede na njihovo zanimanje.

### <a name="featurization"></a>Določanje lastnosti

Tako kot model izgube tudi mi združujemo atribut ServiceCustomerID s CustomerID, da bi dosledno ustvarjali priporočila za vsak CustomerID.

![Določanje lastnosti modela priporočil](media/azure-machine-learning-model-featurization.png)

Podatki se pridobivajo iz treh različnih entitet, iz katerih nato izhajajo lastnosti. Določanje lastnosti za priporočila se razlikuje od izgube ali scenarijev CLTV. Model priporočil potrebuje vhodne podatke v obliki treh sklopov lastnosti.

### <a name="model-selection"></a>Izbira modela

Izdelke ali storitve napovedujemo z algoritmom, ki se imenuje **Usposabljanje orodja za priporočanje ujemanja**, da z njim pripravimo model napovedovanja.

![Algoritem za priporočanje izdelkov](media/azure-machine-learning-model-recommendation-algorithm.png)

Tri vhodna vrata za model **Usposabljanje orodja za priporočanje ujemanja** upoštevajo podatke o uporabi storitve usposabljanja, opis stranke (izbirno) in opis storitve. Obstajajo trije različni načini ocenjevanja modela. Prvi je za ocenjevanje modela, pri katerem se izračuna ocena Normaliziran znižan skupni dobiček (NDCG) za razvrščanje ocenjenih elementov. V tem poskusu je ocena NDCG 0,97. Ostali dve možnosti ocenjujeta model v celotnem katalogu priporočljivih storitev ali pa le za elemente, ki jih uporabniki prej niso uporabljali.

Če si podrobneje pogledamo distribucijo priporočil v celotnem katalogu storitev, opazimo, da so najpogosteje priporočene storitve telefon, WiFi in pošta. To je skladno z našimi ugotovitvami iz distribucij podatkov o porabi storitev:

![Izhod modela priporočil](media/azure-machine-learning-model-output.png)

Celoten [poskus priporočila izdelka je na voljo v galeriji Azure AI.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>Integracija modelov po meri

Če želite te napovedi uporabiti v aplikaciji Customer Insights, morate **izvoziti** predvidevanja skupaj z ID-ji strank. [Izvozite jih na isto mesto v shrambi v zbirki dvojiških podatkov Azure](https://docs.microsoft.com/azure/storage/common/storage-import-export-data-from-blobs), kamor izvažate izvorne podatke. Napovedno spletno storitev je mogoče načrtovati tako, da se redno izvaja in posodablja rezultate.

Podatke, ki jih ustvari model po meri, lahko uporabimo za dodatno obogatitev podatkov o strankah. Za več informacij glejte [Modeli strojnega učenja po meri](custom-models.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]