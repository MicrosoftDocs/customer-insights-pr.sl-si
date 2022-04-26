---
title: Nove in prihajajoče funkcije
description: Informacije o novih funkcijah, izboljšavah in popravkih napak.
ms.date: 04/05/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 2f081306271a170cf3e250fc1a193cedb70aeec6
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547692"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Kaj je novega pri zmogljivosti vpogledov v občinstvo Dynamics 365 Customer Insights

Navdušeno sporočamo, da so najnovejše posodobitve pripravljene! V tem članku so povzete funkcije predogledne različice za javnost, splošne izboljšave razpoložljivosti in posodobitve funkcij. Če si želite ogledati dolgoročne načrte za funkcije, glejte [Načrti za izdajo storitev Dynamics 365 in Power Platform](/dynamics365/release-plans/).

Posodobitve izdajamo po posameznih regijah. Tako lahko nekatere regije vidijo funkcije pred drugimi. Če ni določeno drugače, vam ni treba ničesar storiti in aplikacijo bomo samodejno posodobili brez izpadov.

> [!TIP]
> Če želite predložiti zahteve glede funkcij in predloge za izdelke ter glasovati o njih, pojdite na [portal zamisli za aplikacijo Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="march-2022-updates"></a>Posodobitve marca 2022

Posodobitve marca 2022 vključujejo nove funkcije, nadgradnje zmogljivosti in popravke napak.

### <a name="liveramp-abilitec-enrichment-preview"></a>Obogatitev LiveRamp AbiliTec (predogled)

LiveRamp zagotavlja razrešitev identitete in konsolidacijo podatkov o strankah. Osebne identifikatorje v svojih podatkih o strankah lahko preslikate v graf identitete AbiliTec in prejmete AbiliTec ID-je. Te ID-je lahko nato uporabite za boljše poenotenje podatkov vaših strank.

Za več informacij glejte [Obogatite profile strank s podatki o identiteti iz LiveRamp (Predogled)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Organizirajte segmente in mere z oznakami in filtri
Če vaša organizacija vzdržuje veliko segmentov ali ukrepov, je iskanje pravega včasih težko. Ta nova funkcija vam omogoča organiziranje seznamov z uporabo oznak in stolpcev. Pomaga pri hitrem in preprostem iskanju podatkov ter prilagajanju pogledov.

Za več informacij glejte [Delo z oznakami in stolpci](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Omogoči skupno rabo podatkov z Dataverse pri uporabi lastnega računa za shranjevanje

Če vaše okolje uporablja Azure Data Lake Storage za shranjevanje podatkov Customer Insights, skupno rabo podatkov Microsoft Dataverse potrebuje dodatno konfiguracijo.
Prej ste lahko omogočili samo skupno rabo podatkov z Dataverse ko so bili vaši podatki shranjeni v našem upravljanem podatkovnem jezeru. 

Za več informacij glejte [Omogoči skupno rabo podatkov z Dataverse od svojega Azure Data Lake Storage (predogled)](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

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

Izdelani modeli predvidevanje, vključno z **odtok naročnin**, **odliv**, in **življenjska vrednost stranke (CLV)** postanejo splošno dostopni kot del Customer Insights. 

Za več informacij glejte [Pregled napovedi](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Novo vir podatkov: Integracija z Azure Synapse Analytics (predogled)

Azure Synapse Analytics je analitična storitev podjetja, ki pospeši čas do vpogledov v podatkovna skladišča in sisteme velikih podatkov.

Organizacije, ki že uporabljajo Azure Synapse Analytics lahko te podatke vnese v Customer Insights. 

Za več informacij glejte [Povežite an Azure Synapse vir podatkov (predogled)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>Obogatitev LiveRamp (predogled)

LiveRamp zagotavlja razrešitev identitete in konsolidacijo podatkov o strankah. Osebne identifikatorje v svojih podatkih o strankah lahko preslikate v graf identitete AbiliTec in prejmete AbiliTec ID-je. Te ID-je lahko nato uporabite za boljše poenotenje podatkov vaših strank.

Za več informacij glejte [Obogatite profile strank s podatki o identiteti iz LiveRamp (Predogled)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Obogatitev za vire podatkov (predogled)

Uporabite podatke iz virov, kot so Microsoft in drugi partnerji, da obogatite svoje podatke o strankah pred poenotenjem podatkov. Obogatitve vir podatkov pomagajo ustvariti večjo popolnost in kakovost podatkov, kar lahko pomaga doseči boljše rezultate, ko poenotite svoje podatke.

Za več informacij glejte [Obogatitev za vire podatkov (predogled)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Sprememba lastnika okolja

Medtem ko ima lahko več uporabnikov skrbniška dovoljenja v Customer Insights, je samo en uporabnik lastnik okolja. Izboljšana izkušnja vam omogoča, da zamenjate lastnike okolja in zahtevate lastništvo, če je nekdanji lastnik zapustil organizacijo. 

Za več informacij glejte [Spremenite lastnika okolja](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Postopek priprave podatkov navaja razloge za poškodovanje zapisov

Priprava podatkov zdaj pokaže razlog za korupcijo za vsa polja s poškodovanimi podatki. Informacije so na voljo na ravni posameznega zapisa za enostavno identifikacijo. 

Za več informacij glejte [Poškodovani viri podatkov](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Konec predogleda za funkcije poročanja v zmožnosti vpogleda v dejavnost

The Dynamics 365 Customer Insights Predogled zmogljivosti vpogledov v angažiranost se je končal 15. februarja 2022.  
Ta sprememba pomeni, da preizkusna izkušnja Customer Insights ne vključuje več možnosti ustvarjanja tokov ali drugih funkcij poročanja.

Vabimo vas, da raziščete in ocenite številne druge lastnosti [Vpogled v stranke](https://dynamics.microsoft.com/ai/customer-insights/), Microsoftova platforma za podatke o strankah (CDP).    
 
V prehodnem obdobju imajo obstoječi udeleženci predogleda še vedno dostop do nekaterih zmožnosti in funkcionalnosti predogleda:

- Pridobite kodo za instrumentiranje spletnega mesta ali mobilne aplikacije 
- Oglejte si dogodke in lastnosti dogodkov 
- Izboljšajte poenotene profile s prevzetimi in izpopolnjenimi dogodki, da izkoristite polno vrednost svojih podatkov o strankah
  
V prehodnem obdobju se zajeti dogodki še vedno pretakajo v povezano podatkovno jezero. Ko je ta funkcija izklopljena, se skupna raba podatkov med vpogledi v dejavnost in vpogledi občinstvo ustavi in v povezani pomnilnik se ne pošiljajo novi dogodki.
Če imate vprašanja o koncu predogleda zmogljivosti, se obrnite neposredno na skupino za Microsoftov račun. Vaša skupina za račun vas bo obveščala o prihodnjih izdajah. 

## <a name="january-2022-updates"></a>Posodobitve v januarju 2022

Posodobitve januarja 2022 vključujejo nove funkcije, nadgradnje zmogljivosti in popravke napak.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Analiza razpoloženja povratnih informacij vaših strank

Customer Insights ponuja novo funkcijo, ki jo poganja umetna inteligenca, za sintetiziranje razpoloženja strank in prepoznavanje posebnih poslovnih vidikov kot priložnosti za ciljno usmerjene izboljšave. Z analizo pisnih povratnih informacij vaših strank lahko dobite natančne vpoglede po nizki ceni. Analiza občutkov, ki jo poganjajo modeli obdelave naravnega jezika (NLP), ki ustvarjajo dva izpeljana vpogleda za vsak ID stranke. Ocena razpoloženja (od –5 do 5) in seznam veljavnih poslovnih vidikov. 

Za več informacij glejte [Analizirajte razpoloženje v povratnih informacijah strank (predogled)](sentiment-analysis.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]