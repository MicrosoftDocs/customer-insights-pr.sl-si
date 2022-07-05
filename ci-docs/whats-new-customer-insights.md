---
title: Novosti v rešitvi Dynamics 365 Customer Insights
description: Informacije o novih funkcijah, izboljšavah in popravkih napak.
ms.date: 06/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 4b5b95d1774d22827b3c08c2b6ccbb7858f1b04b
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054038"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Novosti v rešitvi Dynamics 365 Customer Insights

Navdušeno sporočamo, da so najnovejše posodobitve pripravljene! V tem članku so povzete funkcije predogledne različice za javnost, splošne izboljšave razpoložljivosti in posodobitve funkcij. Če si želite ogledati dolgoročne načrte za funkcije, glejte [Načrti za izdajo storitev Dynamics 365 in Power Platform](/dynamics365/release-plans/).

Posodobitve izdajamo po posameznih regijah. Tako lahko nekatere regije vidijo funkcije pred drugimi. Če ni določeno drugače, vam ni treba ničesar storiti in aplikacijo bomo samodejno posodobili brez izpadov.

> [!TIP]
> Če želite predložiti zahteve glede funkcij in predloge za izdelke ter glasovati o njih, pojdite na [portal zamisli za aplikacijo Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="may-2022-updates"></a>Posodobitve za maj 2022

Posodobitve maja 2022 vključujejo nove funkcije, nadgradnje zmogljivosti in popravke napak.

### <a name="updated-data-unification-experience"></a>Posodobljena izkušnja združevanja podatkov

 Združevanje podatkov vam omogoča poenotenje nekoč ločenih virov podatkov v en sam glavni nabor podatkov, ki zagotavlja enoten pogled na te podatke. Podatke je mogoče poenotiti na eni sami ali več entitetah. Najprej ti [izberite entitete in izvorna polja](map-entities.md),[odstranite podvojene zapise](remove-duplicates.md), določite pravila za [ujemanje pogojev](match-entities.md), in definiraj katero [polja za vključitev v enotne profile strank](merge-entities.md).

Za več informacij glejte [Pregled poenotenja podatkov](data-unification.md).

### <a name="refreshed-home-page-in-customer-insights"></a>Osvežena domača stran v storitvi Customer Insights

**Domov** vas vodi skozi proces konfiguracije za ključne funkcije in nudi pregled segmentov, meritev in podatkov o obogatitvi. Osvežili smo izkušnjo, da na prvi pogled zagotovimo ustreznejše informacije.

Za več informacij glejte [Raziščite vpogled v stranke](home.md).

### <a name="track-usage-of-a-segment"></a>Sledite uporabi segmenta

Zdaj lahko [sledite uporabi segmenta](segments.md#track-usage-of-a-segment) v aplikacijah, ki temeljijo na Dataverse organizacija, ki je povezana s Customer Insights. Za [Segmenti Customer Insights, ki se uporabljajo na poteh strank v Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), vas sistem obvesti o uporabi tega segmenta.

### <a name="export-to-criteo"></a>Izvozi v Criteo

Criteo je spletna platforma, ki uporabnikom pomaga upravljati digitalno oglaševanje. Zdaj lahko izvozite segmente enotnih profilov strank za ustvarjanje akcij, zagotavljanje e-poštnega trženja in uporabo posebnih skupin strank s Criteo.

Za več informacij glejte [Izvozi segmente v Criteo (predogled)](export-criteo.md).

### <a name="refined-documentation-structure-for-environment-creation"></a>Izpopolnjena struktura dokumentacije za ustvarjanje okolja

Ponovno smo pregledali dokumente pomoči v zvezi z ustvarjanjem in upravljanjem okolij v storitvi Customer Insights. Članki so zdaj združeni pod vozliščem Okolja v kazalu vsebine. Prestrukturirani članki zagotavljajo več smernic za različne načine za nastavitev okolij in imajo jasnejšo strukturo. Če želite deliti povratne informacije, nam to sporočite prek kontrolnikov na koncu člankov pomoči.

Za več informacij glejte [Kako: ustvariti novo okolje](create-environment.md).

## <a name="april-2022-updates"></a>Posodobitve iz aprila 2022

Posodobitve aprila 2022 vključujejo nove funkcije, nadgradnje zmogljivosti in popravke napak.

### <a name="dun--bradstreet-enrichment-preview"></a>Obogatitev Dun & Bradstreet (predogled)

Dun & Bradstreet ponuja komercialne podatke, analitiko in vpoglede za podjetja. Strankam omogoča poenoten profil strank, s katerimi podjetja obogatijo svoje podatke. Obogatitve vključujejo atribute, kot so številka DUNS, velikost podjetja, lokacija, industrija in drugo.

Za več informacij glejte [Obogatitev profilov podjetij z Dun & Bradstreet (predogled)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>Določite vrsto mere pri ustvarjanju nove mere

Zdaj lahko ločite med ukrepi za posamezne profile in meritvami v celotnem podjetju. Medtem ko so poslovni ukrepi prikazani na domači strani Customer Insights, so ukrepi za stranke izpostavljeni na podrobnih pogledih strank.

Za več informacij glejte [Uporabite graditelj meril za ustvarjanje ukrepov iz nič](measure-builder.md).

### <a name="consolidation-of-customer-insights-documentation"></a>Konsolidacija dokumentacije Customer Insights

Ponovno smo pregledali naše članke o dokumentaciji in odstranili omembe vpogledov v sodelovanje in zmožnosti vpogledov občinstvo. V nadaljevanju se bomo dosledno sklicevali na ime izdelka Customer Insights, ko bomo pisali o temeljnih funkcijah aplikacije. Ta sprememba vodi tudi do pomembnega prestrukturiranja kazala vsebine, strukture URL-jev in poti datotek v osnovnem repozitoriju dokumentacije. Vsi vaši zaznamki ali obstoječe povezave še naprej delujejo in preusmerjajo na posodobljene URL-je.

Če nam želite sporočiti, kako dojemate to spremembo ali opazite, da nekaj ne deluje po pričakovanjih, nam to sporočite [pošiljanje povratnih informacij za to stran](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**).

## <a name="march-2022-updates"></a>Posodobitve marca 2022

Posodobitve marca 2022 vključujejo nove funkcije, nadgradnje zmogljivosti in popravke napak.

### <a name="liveramp-abilitec-enrichment-preview"></a>Obogatitev LiveRamp AbiliTec (predogled)

LiveRamp zagotavlja razrešitev identitete in konsolidacijo podatkov strank. Osebne identifikatorje v svojih podatkih o strankah lahko preslikate v graf identitete AbiliTec in prejmete AbiliTec ID-je. Te ID-je lahko nato uporabite za boljše poenotenje podatkov vaših strank.

Za več informacij glejte [Obogatite profile strank s podatki o identiteti iz LiveRamp (predogled)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Organizirajte segmente in mere z oznakami in filtri

Če vaša organizacija vzdržuje veliko segmentov ali ukrepov, je iskanje pravega včasih težko. Ta nova funkcija vam omogoča organiziranje seznamov z uporabo oznak in stolpcev. Pomaga hitro in enostavno najti podatke ter prilagoditi poglede.

Za več informacij glejte [Delo z oznakami in stolpci](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Omogoči skupno rabo podatkov z Dataverse pri uporabi lastnega računa za shranjevanje

Če vaše okolje uporablja Azure Data Lake Storage za shranjevanje podatkov Customer Insights, skupno rabo podatkov Microsoft Dataverse potrebuje dodatno konfiguracijo.
Prej ste lahko omogočili samo skupno rabo podatkov z Dataverse ko so bili vaši podatki shranjeni v našem upravljanem podatkovnem jezeru.

Za več informacij glejte [Omogoči skupno rabo podatkov z Dataverse od svojega Azure Data Lake Storage (predogled)](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Nove izvozne destinacije: Iterable in Braze

Še naprej širimo naš ekosistem izvoznih destinacij z novimi povezavami. Sedaj lahko izvozite segmente v Iterable in Braze, da uporabite njihove aktivacijske storitve.

Za več informacij glejte [Izvozi segmente v Iterable (predogled)](export-iterable.md) in [Izvozi segmente v Braze (predogled)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Izboljšave izvoza Marketo in Google Ads

Sprememba API-jev v povezanih storitvah vodi do posodobitev za zanesljivo in nemoteno delovanje priključkov. Izdali smo nekaj posodobitev za izvoz v storitve Marketo in Google Ads:

- Google Ads: Nova različica priključka za izvoz Google Ads poenostavlja izkušnjo preverjanja pristnosti in vam zdaj omogoča samodejno ustvarjanje novih ciljnih skupin Google Ads. 
- Marketo: Nova različica priključka za izvoz Marketo zagotavlja podporo za ID Marketo, ki vam omogoča, da se izognete podvajanju podatkov, posodobite obstoječe zapise in ustvarite nove zapise v Marketu. 

## <a name="february-2022-updates"></a>Posodobitve februarja 2022

Posodobitve februarja 2022 vključujejo nove funkcije, nadgradnje zmogljivosti in popravke napak.

### <a name="general-availability-for-prediction-models"></a>Splošna razpoložljivost za modele predvidevanje

Izdelani modeli predvidevanje, vključno z **odliv naročnin**, **odliv**, in **življenjska vrednost stranke (CLV)** postanejo splošno dostopni kot del Customer Insights. 

Za več informacij glejte [Pregled napovedi](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Novo vir podatkov: Integracija z Azure Synapse Analytics (predogled)

Azure Synapse Analytics je analitična storitev podjetja, ki pospeši čas do vpogledov v podatkovna skladišča in sisteme velikih podatkov.

Organizacije, ki že uporabljajo Azure Synapse Analytics lahko te podatke vnese v Customer Insights. 

Za več informacij glejte [Povežite an Azure Synapse vir podatkov (predogled)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>Obogatitev LiveRamp (predogled)

LiveRamp zagotavlja razrešitev identitete in konsolidacijo podatkov strank. Osebne identifikatorje v svojih podatkih o strankah lahko preslikate v graf identitete AbiliTec in prejmete AbiliTec ID-je. Te ID-je lahko nato uporabite za boljše poenotenje podatkov vaših strank.

Za več informacij glejte [Obogatite profile strank s podatki o identiteti iz LiveRamp (predogled)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Obogatitev za vire podatkov (predogled)

Uporabite podatke iz virov, kot so Microsoft in drugi partnerji, da obogatite svoje podatke o strankah pred poenotenjem podatkov. Obogatitve vir podatkov pomagajo ustvariti večjo popolnost in kakovost podatkov, kar lahko pomaga doseči boljše rezultate, ko poenotite svoje podatke.

Za več informacij glejte [Obogatitev za vire podatkov (predogled)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Sprememba lastnika okolja

Medtem ko ima lahko več uporabnikov skrbniška dovoljenja v Customer Insights, je samo en uporabnik lastnik okolja. Izboljšana izkušnja vam omogoča, da spremenite lastnike okolja in zahtevate lastništvo, če je nekdanji lastnik zapustil organizacijo. 

Za več informacij glejte [Spremenite lastnika okolja](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>V postopku priprave podatkov so navedeni razlogi za korupcijo za poškodovane zapise

Priprava podatkov zdaj pokaže razlog za korupcijo za vsa polja s poškodovanimi podatki. Informacije so na voljo na ravni posameznega zapisa za enostavno identifikacijo. 

Za več informacij glejte [Poškodovani viri podatkov](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Konec predogleda za funkcije poročanja v zmožnosti vpogleda v dejavnost

The Dynamics 365 Customer Insights Predogled zmožnosti vpogleda v angažiranost se je končal 15. februarja 2022.  
Ta sprememba pomeni, da preizkusna izkušnja Customer Insights ne vključuje več možnosti ustvarjanja tokov ali drugih funkcij poročanja.

Vabimo vas, da raziščete in ocenite številne druge lastnosti [Vpogled v stranke](https://dynamics.microsoft.com/ai/customer-insights/), Microsoftova platforma za podatke o strankah (CDP).    
 
V prehodnem obdobju imajo obstoječi udeleženci predogleda še vedno dostop do nekaterih zmožnosti in funkcionalnosti predogleda:

- Pridobite kodo za instrumentiranje spletnega mesta ali mobilne aplikacije 
- Oglejte si dogodke in lastnosti dogodkov 
- Izboljšajte poenotene profile s prevzetimi in izpopolnjenimi dogodki, da izkoristite polno vrednost svojih podatkov o strankah
  
V prehodnem obdobju se zajeti dogodki še vedno pretakajo v povezano podatkovno jezero. Ko je ta funkcija izklopljena, se skupna raba podatkov ustavi in v povezani pomnilnik se ne pošiljajo novi dogodki.
Če imate vprašanja o koncu predogleda zmogljivosti, se obrnite neposredno na skupino za Microsoftov račun. Vaša skupina za račun vas bo obveščala o prihodnjih izdajah. 

## <a name="january-2022-updates"></a>Posodobitve v januarju 2022

Posodobitve januarja 2022 vključujejo nove funkcije, nadgradnje zmogljivosti in popravke napak.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Analiza razpoloženja povratnih informacij vaših strank

Customer Insights ponuja novo funkcijo, ki jo poganja umetna inteligenca, za sintetiziranje razpoloženja strank in prepoznavanje posebnih poslovnih vidikov kot priložnosti za ciljno usmerjene izboljšave. Z analizo pisnih povratnih informacij vaših strank lahko dobite natančne vpoglede po nizki ceni. Analiza občutkov, ki jo poganjajo modeli obdelave naravnega jezika (NLP), ki ustvarjajo dva izpeljana vpogleda za vsak ID stranke. Ocena razpoloženja (od –5 do 5) in seznam veljavnih poslovnih vidikov. 

Za več informacij glejte [Analizirajte razpoloženje v povratnih informacijah strank (predogled)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]