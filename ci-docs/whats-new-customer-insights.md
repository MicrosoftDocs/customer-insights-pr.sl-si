---
title: Novosti v rešitvi Dynamics 365 Customer Insights
description: Informacije o novih funkcijah, izboljšavah in popravkih napak.
ms.date: 08/31/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: dcee60a73e0c32278553253040478c31e45237ae
ms.sourcegitcommit: 618ef15b434de0a68213383b6521ce2a60753afb
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 10/07/2022
ms.locfileid: "9638371"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Novosti v rešitvi Dynamics 365 Customer Insights

Navdušeno sporočamo, da so najnovejše posodobitve pripravljene! V tem članku so povzete funkcije predogledne različice za javnost, splošne izboljšave razpoložljivosti in posodobitve funkcij. Če si želite ogledati dolgoročne načrte za funkcije, glejte [Načrti za izdajo storitev Dynamics 365 in Power Platform](/dynamics365/release-plans/).

Posodobitve izdajamo po posameznih regijah. Tako lahko nekatere regije vidijo funkcije pred drugimi. Če ni določeno drugače, vam ni treba storiti ničesar, aplikacijo bomo posodobili samodejno brez izpadov.

> [!TIP]
> Če želite predložiti zahteve glede funkcij in predloge za izdelke ter glasovati o njih, pojdite na [portal zamisli za aplikacijo Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="september-2022-updates"></a>Posodobitve v septembru 2022

Posodobitve v septembru 2022 vključujejo nove funkcije, nadgradnje zmogljivosti in popravke napak.

### <a name="export-data-to-hubspot"></a>Izvoz podatkov v HubSpot

Izvozite segmente poenotenih profilov strank v HubSpot in jih uporabite za e-poštno trženje.

Za več informacij glejte [Izvozi segmente v HubSpot](export-hubspot.md).

### <a name="remove-a-unified-field-or-entity-from-data-unification"></a>Odstranite poenoteno polje ali entiteto iz poenotenja podatkov

Polja in entitete lahko odstranite iz postopka poenotenja podatkov.

Za več informacij glejte [Odstranite poenoteno polje](data-unification-update.md#remove-a-unified-field).

### <a name="manage-unknown-customer-profiles"></a>Upravljajte profile neznanih strank

Nepozabna personalizacija je odvisna od bogastva in popolnosti vaših podatkov o strankah in Customer Insights vam pomaga doseči te cilje. Upravljate lahko profile strank za uporabnike, za katere razen ID-ja nimate drugih podatkov.

Za več informacij glejte [Upravljajte neznane profile s Customer Insights](manage-unknown-profiles.md).

## <a name="august-2022-updates"></a>Posodobitve v avgustu 2022

Posodobitve v avgustu 2022 vključujejo nove funkcije, nadgradnje zmogljivosti in popravke napak.

### <a name="contact-unification-in-b-to-b-environments"></a>Poenotenje stikov v B-to-B okoljih

Okolja B-to-B v Customer Insights zdaj podpirajo izboljšano izkušnjo poenotenja podatkov.

Zdaj lahko poleg računov poenotite tudi stike, da dobite popoln pregled svojih poslovnih stikov. Poenoteni stiki so povezani z poenotenimi računi in so zdaj navedeni na karticah strank. 

Za več informacij glejte [Ustvarite enoten kontaktni profil](data-unification-contacts.md).

### <a name="create-and-export-of-segments-based-on-unified-contacts"></a>Ustvarjanje in izvoz segmentov na podlagi poenotenih kontaktov

Zahvaljujoč novemu poenotenju stikov lahko ustvarite segmente stikov z uporabo meril iz stikov, računov ali obojega. Te segmente je mogoče izvoziti za aktivacijo v drugih storitvah.

Za več informacij glejte [Pregled izvoza](export-destinations.md).

### <a name="deployment-regions-aligned-with-microsoft-dataverse"></a>Območja uvajanja so usklajena z Microsoft Dataverse

Ko ustvarjate novo okolje Customer Insights, lahko izberete regijo, kjer želite, da se storitev uvede in gosti. Posodobili smo izbiro regije, da se uskladimo z njo Microsoft Dataverse in Power Platform.

Sedaj lahko enostavno izberete isto regijo kot vaša obstoječa Microsoft Dataverse okolje ali vaš račun za shranjevanje podatkov Azure Data Lake (če izberete to možnost), odvisno od razpoložljivosti Customer Insights v tej regiji.

Za več informacij glejte [Ustvari novo okolje](create-environment.md) in [Razpoložljivost izdelkov glede na geografsko območje](https://dynamics.microsoft.com/availability-reports/).

## <a name="july-2022-updates"></a>Posodobitve za julij 2022

Posodobitve v juliju 2022 vključujejo nove funkcije, nadgradnje zmogljivosti in popravke napak.

### <a name="export-to-moengage"></a>Izvoz v MoEngage

Izvozite segmente poenotenih profilov strank v MoEngage in jih uporabite za e-poštno trženje v MoEngage.

Za več informacij glejte [Izvozi segmente v MoEngage](export-moengage.md).

### <a name="ssh-support-for-sftp-based-exports"></a>Podpora SSH za izvoze, ki temeljijo na SFTP

Izberite, ali želite preverjanje pristnosti prek SSH ali uporabniškega imena/gesla za povezave do izvoznih ciljev SFTP.

Za več informacij glejte [Izvoz podatkov na gostitelje SFTP](export-sftp.md).

### <a name="personalize-experiences-with-data-about-known-and-unknown-users"></a>Personalizirajte izkušnje s podatki o znanih in neznanih uporabnikih

Upravljanje podatkov o strankah ni nov izziv, vendar postaja vse težje, ko uporabniki krmarijo po različnih digitalnih kanalih, ki jih ponujajo blagovne znamke. Uporabnik, ki je znan (preverjen) na enem kanalu, postane neznan (nepreverjen) na drugem, če ni prijavljen. Pogosto je težava v tem, da nepreverjeni (neznani) uporabniki nimajo skupnega ID-ja. Lahko bi ga uporabili za povezovanje pomembnih atributov profilov in ustvarjanje enotnih profilov strank. Customer Insights pomaga rešiti to težavo tako, da zaužije podatke iz metod sledenja v vaših izvornih sistemih.

Za več informacij glejte [Prilagodite svoje izkušnje s podatki o znanih in neznanih uporabnikih](unknown-to-known.md).

## <a name="june-2022-updates"></a>Posodobitve za junij 2022

Posodobitve v juniju 2022 vključujejo nove funkcije, nadgradnje zmogljivosti in popravke napak.

### <a name="updated-user-experience-for-data-sources-and-data-ingestion"></a>Posodobljena uporabniška izkušnja za vire podatkov in vnos podatkov

Uvoz podatkov iz širokega nabora podatkovnih virov je osnova za konsolidacijo vaših podatkov o strankah Dynamics 365 Customer Insights. Ponovno smo pregledali uporabniško izkušnjo za uvoz in povezovanje podatkovnih virov. Namen te posodobitve je olajšati vnašanje podatkov v Customer Insights.

Za več informacij glejte [Pregled podatkovnih virov](data-sources.md).

### <a name="export-to-inmobi"></a>Izvozi v InMobi

InMobi pomaga blagovnim znamkam razumeti, prepoznati, vključiti in pridobiti potrošnike. Segmente in druge podatke lahko izvozite v storitev InMobi prek računov Azure Blob Storage.

Za več informacij glejte [Izvoz v InMobi (predogled)](export-inmobi.md)

### <a name="lockbox-support-in-customer-insights"></a>Podpora za ključavnico v Customer Insights

Customer Lockbox ponuja vmesnik za pregled in odobritev (ali zavrnitev) zahtev za dostop do podatkov. Te zahteve se pojavijo, ko je za razrešitev primera podpore potreben dostop do podatkov o strankah.

Za več informacij glejte [Varen dostop do podatkov strank s Customer Lockbox (predogled)](security-overview.md#securely-access-customer-data-with-customer-lockbox-preview).

### <a name="connect-to-your-data-using-azure-private-link"></a>Povežite se s svojimi podatki prek zasebne povezave Azure

Azure Private Link naj se Customer Insights poveže z vašim Azure Data Lake Storage računa prek zasebnega končna točka v vašem virtualnem omrežju. Za podatke v računu za shranjevanje, ki ni izpostavljen javnemu internetu, Zasebna povezava omogoča povezavo s tem omejenim omrežjem.

Za več informacij glejte [Uporabite zasebno povezavo v storitvi Customer Insights](security-overview.md#set-up-an-azure-private-link).

## <a name="may-2022-updates"></a>Posodobitve za maj 2022

Posodobitve maja 2022 vključujejo nove funkcije, nadgradnje zmogljivosti in popravke napak.

### <a name="updated-data-unification-experience"></a>Posodobljena izkušnja poenotenja podatkov

 Poenotenje podatkov vam omogoča poenotenje nekoč različnih podatkovnih virov v en sam glavni nabor podatkov, ki zagotavlja poenoten pogled na te podatke. Podatki so lahko poenoteni na eni ali več entitetah. Najprej ti [izberite entitete in izvorna polja](map-entities.md),[odstranite podvojene zapise](remove-duplicates.md), navedite pravila za [ujemanje pogojev](match-entities.md), in določite kateri [polja za vključitev v poenotene profile strank](merge-entities.md).

Za več informacij glejte [Pregled poenotenja podatkov](data-unification.md).

### <a name="refreshed-home-page-in-customer-insights"></a>Osvežena domača stran v storitvi Customer Insights

**domov** vas vodi skozi postopek konfiguracije za ključne funkcije in nudi pregled segmentov, mer in podatkov o obogatitvi. Osvežili smo izkušnjo, da na prvi pogled zagotovimo ustreznejše informacije.

Za več informacij glejte [Raziščite Customer Insights](home.md).

### <a name="track-usage-of-a-segment"></a>Sledite uporabi segmenta

Zdaj lahko [sledite uporabi segmenta](segments.md#track-usage-of-a-segment) v aplikacijah, ki temeljijo na Dataverse organizacija, ki je povezana s Customer Insights. Za [Segmenti Customer Insights, ki se uporabljajo na poti strank Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), vas sistem obvesti o uporabi tega segmenta.

### <a name="export-to-criteo"></a>Izvoz v Criteo

Criteo je spletna platforma, ki uporabnikom pomaga upravljati digitalno oglaševanje. Zdaj lahko izvozite segmente poenotenih profilov strank za ustvarjanje kampanj, zagotavljanje e-poštnega trženja in uporabo določenih skupin strank s Criteo.

Za več informacij glejte [Izvoz segmentov v Criteo (predogled)](export-criteo.md).

### <a name="refined-documentation-structure-for-environment-creation"></a>Izpopolnjena struktura dokumentacije za ustvarjanje okolja

Ponovno smo pregledali dokumente za pomoč v zvezi z ustvarjanjem in upravljanjem okolij v Customer Insights. Članki so zdaj združeni pod vozliščem Okolja v kazalu vsebine. Prestrukturirani članki nudijo več smernic za različne načine nastavitve okolij in imajo jasnejšo strukturo. Če želite deliti povratne informacije, nam to sporočite prek kontrolnikov na koncu člankov s pomočjo.

Za več informacij glejte [Kako: Ustvarite novo okolje](create-environment.md).

## <a name="april-2022-updates"></a>Posodobitve iz aprila 2022

Posodobitve v aprilu 2022 vključujejo nove funkcije, nadgradnje zmogljivosti in popravke napak.

### <a name="dun--bradstreet-enrichment-preview"></a>Obogatitev Dun & Bradstreeta (predogled)

Dun & Bradstreet zagotavlja komercialne podatke, analitiko in vpoglede za podjetja. Strankam omogoča poenoten profil strank, s katerimi podjetja obogatijo svoje podatke. Obogatitve vključujejo atribute, kot so številka DUNS, velikost podjetja, lokacija, panoga in drugo.

Za več informacij glejte [Obogatitev profilov podjetij z Dun & Bradstreet (predogled)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>Pri ustvarjanju nove mere določite vrsto mere

Zdaj lahko razlikujete med meritvami za posamezne profile in meritvami za celotno podjetje. Medtem ko so poslovne mere prikazane na domači strani Customer Insights, so meritve strank izpostavljene v podrobnih pogledih strank.

Za več informacij glejte [Uporabite graditelj mer za ustvarjanje mer iz nič](measure-builder.md).

### <a name="consolidation-of-customer-insights-documentation"></a>Konsolidacija dokumentacije Customer Insights

Ponovno smo pregledali članke o naši dokumentaciji in odstranili omembe vpogledov v sodelovanje in zmožnosti vpogledov občinstvo. V prihodnje se bomo dosledno sklicevali na ime izdelka Customer Insights, ko bomo pisali o osnovnih funkcijah aplikacije. Ta sprememba vodi tudi do pomembnega prestrukturiranja kazala vsebine, strukture URL-jev in poti datotek v osnovnem repozitoriju dokumentacije. Vsi vaši zaznamki ali obstoječe povezave še naprej delujejo in preusmerjajo na posodobljene URL-je.

Če nam želite sporočiti, kako dojemate to spremembo ali opazite, da nekaj ne deluje po pričakovanjih, nam to sporočite [pošiljanje povratnih informacij za to stran](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**).

## <a name="march-2022-updates"></a>Posodobitve marca 2022

Posodobitve v marcu 2022 vključujejo nove funkcije, nadgradnje zmogljivosti in popravke napak.

### <a name="liveramp-abilitec-enrichment-preview"></a>Obogatitev LiveRamp AbiliTec (predogled)

LiveRamp zagotavlja razrešitev identitete in konsolidacijo podatkov o strankah. Osebne identifikatorje v svojih podatkih o strankah lahko preslikate v graf identitete AbiliTec in prejmete ID-je AbiliTec. Te ID-je lahko nato uporabite za boljše poenotenje podatkov o strankah.

Za več informacij glejte [Obogatite profile strank z identitetnimi podatki iz LiveRamp (predogled)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Organizirajte segmente in mere z oznakami in filtri

Če vaša organizacija vzdržuje veliko segmentov ali ukrepov, je iskanje pravega včasih težko. Ta nova funkcija vam omogoča organiziranje seznamov z uporabo oznak in stolpcev. Pomaga pri hitrem in preprostem iskanju podatkov ter prilagajanju pogledov.

Za več informacij glejte [Delajte z oznakami in stolpci](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Omogoči skupno rabo podatkov z Dataverse pri uporabi lastnega računa za shranjevanje

Če vaše okolje uporablja Azure Data Lake Storage za shranjevanje podatkov Customer Insights, deljenje podatkov s Microsoft Dataverse potrebuje dodatno konfiguracijo.
Prej ste lahko omogočili le skupno rabo podatkov z Dataverse ko so bili vaši podatki shranjeni v našem upravljanem podatkovnem jezeru.

Za več informacij glejte [Omogoči skupno rabo podatkov z Dataverse od svojega Azure Data Lake Storage (predogled)](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Nove izvozne destinacije: Iterable in Braze

Še naprej širimo naš ekosistem izvoznih destinacij z novimi povezavami. Zdaj lahko izvozite segmente v Iterable in Braze za uporabo njunih aktivacijskih storitev.

Za več informacij glejte [Izvozi segmente v Iterable (predogled)](export-iterable.md) in [Izvoz segmentov v Braze (predogled)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Izboljšave izvoza Marketo in Google Ads

Spreminjanje API-jev v povezanih storitvah vodi do posodobitev konektorjev za zanesljivo in gladko delovanje. Izdali smo nekaj posodobitev za izvoze v storitve Marketo in Google Ads:

- Google Ads: Nova različica priključka za izvoz Google Ads poenostavlja izkušnjo preverjanja pristnosti in vam zdaj omogoča samodejno ustvarjanje novih ciljnih skupin Google Ads. 
- Marketo: Nova različica izvoznega konektorja Marketo nudi podporo za ID Marketo, kar vam omogoča, da se izognete podvajanju podatkov, posodobite obstoječe zapise in ustvarite nove zapise v Marketu. 

## <a name="february-2022-updates"></a>Posodobitve februarja 2022

Posodobitve v februarju 2022 vključujejo nove funkcije, nadgradnje zmogljivosti in popravke napak.

### <a name="general-availability-for-prediction-models"></a>Splošna razpoložljivost za modele predvidevanje

Vključno z že pripravljenimi modeli predvidevanje **odliv naročnin**, **odliv**, in **življenjska vrednost stranke (CLV)** postanejo splošno dostopni kot del Customer Insights. 

Za več informacij glejte [Pregled napovedi](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Novo vir podatkov: integracija z Azure Synapse Analytics (predogled)

Azure Synapse Analytics je podjetniška analitična storitev, ki pospeši čas do vpogledov v podatkovna skladišča in velike podatkovne sisteme.

Organizacije, ki že uporabljajo Azure Synapse Analytics lahko te podatke prenese v Customer Insights. 

Za več informacij glejte [Povežite an Azure Synapse vir podatkov (predogled)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>Obogatitev LiveRamp (predogled)

LiveRamp zagotavlja razrešitev identitete in konsolidacijo podatkov o strankah. Osebne identifikatorje v svojih podatkih o strankah lahko preslikate v graf identitete AbiliTec in prejmete ID-je AbiliTec. Te ID-je lahko nato uporabite za boljše poenotenje podatkov o strankah.

Za več informacij glejte [Obogatite profile strank z identitetnimi podatki iz LiveRamp (predogled)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Obogatitev za vire podatkov (predogled)

Uporabite podatke iz virov, kot so Microsoft in drugi partnerji, da obogatite svoje podatke o strankah pred poenotenjem podatkov. Vir podatkov obogatitve pomagajo ustvariti višjo popolnost in kakovost podatkov, kar lahko pomaga doseči boljše rezultate, ko poenotite podatke.

Za več informacij glejte [Obogatitev za vire podatkov (predogled)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Sprememba lastnika okolja

Medtem ko ima lahko več uporabnikov skrbniška dovoljenja v Customer Insights, je samo en uporabnik lastnik okolja. Izboljšana izkušnja vam omogoča, da spremenite lastnike okolja in zahtevate lastništvo, če prejšnji lastnik zapusti organizacijo. 

Za več informacij glejte [Spremenite lastnika okolja](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Postopek priprave podatkov navaja razloge za poškodovane zapise

Priprava podatkov zdaj prikazuje vzrok za pokvarjenost za vsa polja s pokvarjenimi podatki. Informacije so na voljo na ravni posameznega zapisa za lažjo identifikacijo.

Za več informacij glejte [Pokvarjeni viri podatkov](data-sources.md#corrupt-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Konec predogleda za funkcije poročanja v zmožnosti vpogledov v sodelovanje

The Dynamics 365 Customer Insights Predogled zmogljivosti vpogledov v sodelovanje se je končal 15. februarja 2022.  
Ta sprememba pomeni, da preskusna izkušnja Customer Insights ne vključuje več možnosti ustvarjanja tokov ali drugih funkcij poročanja.

Vabimo vas, da raziščete in ocenite številne druge funkcije [Vpogledi strank](https://dynamics.microsoft.com/ai/customer-insights/), Microsoftova platforma za podatke o strankah (CDP).    
 
V prehodnem obdobju imajo obstoječi udeleženci predogleda še vedno dostop do nekaterih zmožnosti in funkcionalnosti predogleda:

- Pridobite kodo za instrumentiranje spletnega mesta ali mobilne aplikacije 
- Oglejte si dogodke in lastnosti dogodkov 
- Izboljšajte poenotene profile z vnesenimi in izpopolnjenimi dogodki, da izkoristite celotno vrednost svojih podatkov o strankah
  
V prehodnem obdobju se zajeti dogodki še vedno pretakajo v povezano Data Lake. Ko je ta funkcija izklopljena, se bo skupna raba podatkov ustavila in novi dogodki se ne pošiljajo v povezani pomnilnik.
Če imate vprašanja o koncu predogleda zmožnosti, se neposredno obrnite na skupino za Microsoftov račun. Vaša skupina za račun vas bo obveščala o prihodnjih izdajah. 

## <a name="january-2022-updates"></a>Posodobitve v januarju 2022

Posodobitve v januarju 2022 vključujejo nove funkcije, nadgradnje zmogljivosti in popravke napak.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Analiza razpoloženja povratnih informacij vaših strank

Customer Insights ponuja novo funkcijo, ki temelji na umetni inteligenci, za sintetiziranje občutkov strank in prepoznavanje posebnih poslovnih vidikov kot priložnosti za ciljno usmerjene izboljšave. Z analizo pisnih povratnih informacij vaših strank lahko dobite natančne vpoglede po nizki ceni. Analiza razpoloženja, ki jo poganjajo modeli obdelave naravnega jezika (NLP), ki ustvarjajo dva izpeljana vpogleda za vsak ID stranke. Ocena razpoloženja (od –5 do 5) in seznam ustreznih poslovnih vidikov. 

Za več informacij glejte [Analizirajte razpoloženje v povratnih informacijah strank (predogled)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]