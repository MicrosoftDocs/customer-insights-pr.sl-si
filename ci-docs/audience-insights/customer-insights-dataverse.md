---
title: Podatki Customer Insights v okolju Microsoft Dataverse
description: Uporabite entitete Customer Insights kot tabele v okoljih Microsoft Dataverse.
ms.date: 11/25/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 9f730f5856221592cddf34b714beeaca24c52130
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355449"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Delo s podatki Customer Insights v okolju Microsoft Dataverse

Storitev Customer Insights nudi možnost omogočanja izhodnih entitet v okolju [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Ta integracija omogoča enostavno izmenjavo podatkov in razvoj po meri s pristopom, ki zahteva programiranje z malo kode/brez kode. Izhodne entitete bodo na voljo v obliki tabel v okolju Dataverse. Te tabele omogočajo scenarije, kot so [samodejni poteki dela prek Power Automate](/power-automate/getting-started), [aplikacije, ki temeljijo na modelu](/powerapps/maker/model-driven-apps/) in [aplikacije s platnom](/powerapps/maker/canvas-apps/) prek Power Apps. Podatke lahko uporabite za katero koli drugo aplikacijo, ki temelji na tabelah Dataverse. Trenutna izvedba v glavnem podpira iskanje, kjer je mogoče pridobiti podatke iz razpoložljivih entitet vpogledov občinstva za izbrani ID stranke.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Priložite okolje Dataverse v Customer Insights

**Organizacije z obstoječimi okolji Dataverse**

Organizacije, ki že uporabljajo okolje Dataverse, lahko [uporabijo enega od obstoječih okolij Dataverse](create-environment.md), ko skrbnik nastavi vpoglede občinstva. Če navedete URL v okolje Dataverse, se priloži njegovemu novemu okolju za vpoglede občinstva. Da bi zagotovili najboljšo možno uspešnost, morata biti okolji Customer Insights in Dataverse gostovani v isti regiji.

**Nova organizacija**

Če ustvarite novo organizacijo, ko nastavljate Customer Insights, boste samodejno pridobili novo okolje Dataverse.

> [!NOTE]
> Če vaše organizacije že uporabljajo okolje Dataverse v svojem najemniku, si je dobro zapomniti, da [ustvarjanje okolja Dataverse upravlja skrbnik](/power-platform/admin/control-environment-creation.md). Če na primer s svojim organizacijskim računom nastavljate novo okolje za vpoglede občinstva in je skrbnik onemogočil ustvarjanje preizkusnih okolij Dataverse za vse, razen za skrbnike, ne morete ustvariti novega preizkusnega okolja.
> 
> Preizkusna okolja Dataverse, ustvarjena v Customer Insights, imajo 3 GB prostora za shranjevanje, kar se ne bo vštelo v celotno zmogljivost, ki pripada najemniku. Plačljive naročnine so upravičene do okolja Dataverse s 15 GB prostora za zbirko podatkov in 20 GB prostora za shranjevanje datotek.

## <a name="output-entities"></a>Izhodne entitete

Nekatere izhodne entitete iz vpogledov občinstva so na voljo kot tabele v okolju Dataverse. Spodnji razdelki opisujejo pričakovano shemo teh tabel.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Obogatitev](#enrichment)
- [Predvidevanje](#prediction)
- [Članstvo v segmentu](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Ta tabela vsebuje poenoteni profil stranke iz Customer Insights. Shema za poenoteni profil stranke je odvisna od entitet in atributov, uporabljenih v postopku združevanja. Shema profila stranke običajno vsebuje podmnožico atributov iz [definicije Common Data Model atributa CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Tabela AlternateKey vsebuje ključe entitet, ki so sodelovale v postopku poenotenja.

|Column  |Vnesi  |Opis  |
|---------|---------|---------|
|DataSourceName    |String         | Ime vira podatkov. Primer: `datasource5`.        |
|EntityName        | String        | Ime entitete v vpogledih občinstva. Primer: `contact1`.        |
|AlternateValue    |String         |Nadomestni ID, ki se preslika na ID stranke. Primer: `cntid_1078`         |
|KeyRing           | Večvrstično besedilo        | Vrednost JSON  </br> Vzorec: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | String        | ID poenotenega profila stranke.         |
|AlternateKeyId     | GUID         |  Determinirani GUID AlternateKey, ki temelji na identifikatorju msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Vzorec: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Ta tabela vsebuje dejavnosti uporabnikov, ki so na voljo v Customer Insights.

| Column            | Vnesi        | Opis                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | ID profila stranke                                                                      |
| ActivityId        | String      | Interni ID dejavnosti stranke (primarni ključ)                                       |
| SourceEntityName  | String      | Ime izvorne entitete                                                                |
| SourceActivityId  | String      | Primarni ključ izvorne entitete                                                       |
| ActivityType      | String      | Vrsta semantične dejavnosti ali ime dejavnosti po meri                                        |
| ActivityTimeStamp | DATETIME    | Časovni žig dejavnosti                                                                      |
| Naslov             | String      | Naziv ali ime dejavnosti                                                               |
| Opis       | String      | Opis dejavnosti                                                                     |
| Spletni naslov               | String      | Povezava do zunanjega URL-ja, specifičnega za dejavnost                                         |
| SemanticData      | Niz JSON | Vključuje seznam parov ključnih vrednosti za semantična polja preslikave, specifična za vrsto dejavnosti |
| RangeIndex        | String      | Časovni žig Unix, ki se uporablja za razvrščanje časovnice dejavnosti in poizvedb obseg v uporabi |
| mydynci_unifiedactivityid   | GUID | Interni ID dejavnosti stranke (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Ta tabela vsebuje izhodne podatke ukrepov, ki temeljijo na atributih strank.

| Column             | Vnesi             | Opis                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | ID profila stranke        |
| Mere           | Niz JSON      | Vključuje seznam parov ključnih vrednosti za ime in vrednosti ukrepa za določeno stranko | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | ID profila stranke |


### <a name="enrichment"></a>Obogatitev

Ta tabela vsebuje rezultat postopka obogatitve.

| Column               | Vnesi             |  Opis                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | ID profila stranke                                 |
| EnrichmentProvider   | String           | Ime ponudnika obogatitve                                  |
| EnrichmentType       | String           | Vrsta obogatitve                                      |
| Vrednosti               | Niz JSON      | Seznam atributov, pridobljenih v postopku obogatitve |
| msdynci_enrichmentid | GUID             | Determinirani GUID, ustvarjen iz identifikatorja msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Predvidevanje

Ta tabela vsebuje rezultat predvidevanj modela.

| Column               | Vnesi        | Opis                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | ID profila stranke                                  |
| ModelProvider        | String      | Ime ponudnika modela                                      |
| Model                | String      | Ime modela                                                |
| Vrednosti               | Niz JSON | Seznam atributov, ki jih izdela model |
| msdynci_predictionid | GUID        | Determinirani GUID, ustvarjen iz identifikatorja msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Članstvo v segmentu

Ta tabela vsebuje informacije o članstvu v segmentih profilov strank.

| Column        | Vnesi | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | ID profila stranke        |
| Ponudnik segmenta      | String       | Aplikacija, ki objavlja segmente. Privzeto: občinstvo vpogledi         |
| SegmentMembershipType | String       | Vrsta stranke ta zapis članstva v segmentu. Podpira več vrst, kot so stranka, stik ali račun. Privzeto: Stranka  |
| Segmenti       | Niz JSON  | Seznam edinstvenih segmentov, katerih član je profil stranke      |
| msdynci_identifier  | String   | Enolični identifikator zapisa članstva v segmentu. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministični GUID, ustvarjen iz`msdynci_identifier`          |
