---
title: Podatki Customer Insights v okolju Microsoft Dataverse
description: Uporabite entitete Customer Insights kot tabele v okoljih Microsoft Dataverse.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 1e629cd218b104b115f74f59a53a14e9d60fcc8a
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741385"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Delo s podatki Customer Insights v okolju Microsoft Dataverse

Storitev Customer Insights nudi možnost omogočanja izhodnih entitet v okolju [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Ta integracija omogoča preprosto izmenjavo podatkov in razvoj po meri s pristopom z nizko kodo/brez kode. The [izhodne entitete](#output-entities) so na voljo kot tabele v a Dataverse okolje. Podatke lahko uporabite za katero koli drugo aplikacijo, ki temelji na Dataverse mize. Te tabele omogočajo scenarije, kot so avtomatizirani potek dela Power Automate ali ustvarjanje aplikacij z Power Apps. Trenutna izvedba večinoma podpira iskanja, kjer je mogoče pridobiti podatke iz razpoložljivih entitet Customer Insights za dani ID stranke.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Priložite okolje Dataverse v Customer Insights

**Obstoječa organizacija**

Skrbniki lahko konfigurirajo Customer Insights na [uporabite obstoječo Dataverse okolje](create-environment.md) ko ustvarijo okolje Customer Insights. Z posredovanjem URL-ja za Dataverse okolju, se povezuje z njihovim novim okoljem Customer Insights. Vpogled v stranke in Dataverse okolja morajo gostovati v isti regiji. 

Če ne želite uporabiti obstoječega Dataverse okolje, sistem ustvari novo okolje za podatke Customer Insights v vašem najemniku. 

> [!NOTE]
> Če vaša organizacija že uporablja Dataverse pri njihovem najemniku je pomembno, da se tega spomnite [Dataverse ustvarjanje okolja nadzoruje skrbnik](/power-platform/admin/control-environment-creation) . Na primer, če s svojim organizacijskim računom nastavljate novo okolje Customer Insights in je skrbnik onemogočil ustvarjanje Dataverse preizkusna okolja za vse, razen za skrbnike, ne morete ustvariti novega preizkusnega okolja.
> 
> Preizkusna okolja Dataverse, ustvarjena v Customer Insights, imajo 3 GB prostora za shranjevanje, kar se ne bo vštelo v celotno zmogljivost, ki pripada najemniku. Plačljive naročnine so upravičene do okolja Dataverse s 15 GB prostora za zbirko podatkov in 20 GB prostora za shranjevanje datotek.

**Nova organizacija**

Če ustvarite novo organizacijo pri nastavitvi Customer Insights, sistem samodejno ustvari novo Dataverse okolje v vaši organizaciji za vas.

## <a name="output-entities"></a>Izhodne entitete

Nekatere izhodne entitete iz Customer Insights so na voljo kot tabele v Dataverse. Spodnji razdelki opisujejo pričakovano shemo teh tabel.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Obogatitev](#enrichment)
- [Predvidevanje](#prediction)
- [Članstvo v segmentu](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Ta tabela vsebuje poenoteni profil stranke iz Customer Insights. Shema za poenoten profil stranke je odvisna od entitet in atributov, uporabljenih v postopku poenotenja podatkov. Shema profila stranke običajno vsebuje podmnožico atributov iz [definicije Common Data Model atributa CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Tabela AlternateKey vsebuje ključe entitet, ki so sodelovale v postopku poenotenja.

|Column  |Vnesi  |Opis  |
|---------|---------|---------|
|DataSourceName    |String         | Ime vira podatkov. Primer: `datasource5`.        |
|EntityName        | String        | Ime subjekta v Customer Insights. Primer: `contact1`.        |
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
| Ponudnik segmenta      | String       | Aplikacija, ki objavlja segmente.      |
| SegmentMembershipType | String       | Vrsta stranke ta zapis članstva v segmentu. Podpira več vrst, kot so stranka, stik ali račun. Privzeto: Stranka  |
| Segmenti       | Niz JSON  | Seznam edinstvenih segmentov, katerih član je profil stranke      |
| msdynci_identifier  | String   | Enolični identifikator zapisa članstva v segmentu. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministični GUID, ustvarjen iz`msdynci_identifier`          |
