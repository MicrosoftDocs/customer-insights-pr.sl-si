---
title: Delo s podatki Customer Insights v okolju Microsoft Dataverse
description: Naučite se povezati Customer Insights in Microsoft Dataverse in razumeti izhodne entitete, ki so izvožene v Dataverse.
ms.date: 08/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 9433c411a2c7eb0db137c6392578993d47be82a2
ms.sourcegitcommit: 8559ca47a22d1d7cd9be13531c2eaf0c1083942b
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 10/12/2022
ms.locfileid: "9671271"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Delo s podatki Customer Insights v okolju Microsoft Dataverse

Storitev Customer Insights nudi možnost omogočanja izhodnih entitet v okolju [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Ta integracija omogoča enostavno skupno rabo podatkov in razvoj po meri s pristopom z nizko kodo/brez kode. The [izhodne entitete](#output-entities) so na voljo kot tabele v a Dataverse okolju. Podatke lahko uporabite za katero koli drugo aplikacijo, ki temelji na Dataverse mize. Te tabele omogočajo scenarije, kot so avtomatizirani delovni tokovi Power Automate ali ustvarjanje aplikacij z Power Apps.

Povezovanje z vašim Dataverse okolje vam omogoča tudi [vnos podatkov iz podatkovnih virov na mestu uporabe z uporabo Power Platform podatkovnih tokov in prehodov](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Zahteve

- Vpogledi strank in Dataverse okolja morajo gostovati v isti regiji.
- Vloga globalnega skrbnika, nastavljena v Dataverse okolju. Preverite, ali je to [Dataverse okolje je povezano](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) v določene varnostne skupine in se prepričajte, da ste dodani v te varnostne skupine.
- Nobeno drugo okolje Customer Insights ni povezano z Dataverse okolje, ki ga želite povezati. Naučite se [odstranite obstoječo povezavo z a Dataverse okolju](#remove-an-existing-connection-to-a-dataverse-environment).
- A Microsoft Dataverse okolje, povezano z enim samim računom za shranjevanje, če konfigurirate okolje za [uporabite svoje Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse pravica do zmogljivosti shranjevanja

Naročnina na Customer Insights vam daje pravico do dodatne zmogljivosti za obstoječo organizacijo [Dataverse skladiščna zmogljivost](/power-platform/admin/capacity-storage). Dodana zmogljivost je odvisna od števila profilov, ki jih uporablja vaša naročnina.

**Primer:**

Ob predpostavki, da dobite 15 GB prostora za shranjevanje baze podatkov in 20 GB prostora za shranjevanje datotek na 100.000 profilov strank. Če vaša naročnina vključuje 300.000 profilov strank, je vaša skupna kapaciteta pomnilnika 45 GB (3 x 15 GB) prostora za shranjevanje baze podatkov in 60 GB prostora za shranjevanje datotek (3 x 20 GB). Podobno, če imate naročnino B-to-B s 30.000 računi, je vaša skupna kapaciteta pomnilnika 45 GB (3 x 15 GB) prostora za shranjevanje baze podatkov in 60 GB prostora za shranjevanje datotek (3 x 20 GB).

Zmogljivost dnevnika ni prirastna in je fiksna za vašo organizacijo.

Za več informacij o podrobnih pooblastilih za zmogljivost glejte [Vodnik za licenciranje Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Povežite a Dataverse okolja do Customer Insights

The **Microsoft Dataverse** korak vam omogoča, da Customer Insights povežete s svojim Dataverse okolje, medtem ko [ustvarjanje okolja Customer Insights](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="deljenje podatkov z Microsoft Dataverse samodejno omogočeno za nova okolja.":::

1. Navedite URL do svojega Dataverse okolje ali pustite prazno, da ga ustvarimo za vas.

   > [!NOTE]
   > Po vzpostavitvi povezave med Customer Insights in Dataverse, ne spreminjajte imena organizacije za Dataverse okolju. Ime organizacije se uporablja v Dataverse URL in spremenjeno ime prekineta povezavo s Customer Insights.

   [Power Platform skrbniki lahko nadzorujejo, kdo lahko ustvari nov Dataverse okoljih](/power-platform/admin/control-environment-creation). Če poskušate nastaviti novo okolje Customer Insights in vam ne uspe, je skrbnik morda onemogočil ustvarjanje Dataverse okolja za vse razen skrbnikov.

1. Če uporabljate svoj račun Data Lake Storage:
   1. Izberite **Omogoči skupno rabo podatkov** z Dataverse.
   1. Vnesite **Identifikator dovoljenj**. Če želite pridobiti identifikator dovoljenja, [omogoči deljenje podatkov z Dataverse iz svojega lastnega Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Omogoči skupno rabo podatkov z Dataverse od svojega Azure Data Lake Storage (predogled)

notri [lastne Azure Data Lake Storage račun](own-data-lake-storage.md), preverite, ali ima uporabnik, ki nastavlja okolje Customer Insights, vsaj **Podatki bloba za shranjevanje Uporabnik z dovoljenjem za branje** dovoljenja za`customerinsights` vsebnik v računu za shranjevanje.

> [!NOTE]
> Deljenje podatkov je možno le, če uporabljate svoje Azure Data Lake Storage račun. Ta nastavitev ni na voljo, če okolje Customer Insights uporablja privzeto Dataverse shranjevanje.

### <a name="limitations"></a>Omejitve

- Samo preslikava ena proti ena med a Dataverse organizacija in an Azure Data Lake Storage račun. Enkrat a Dataverse organizacija povezana z računom za shranjevanje, se ne more povezati z drugim računom za shranjevanje. Ta omejitev preprečuje Dataverse iz zapolnjevanja več računov za shranjevanje.
- Skupna raba podatkov ne bo delovala, če je za dostop do vaših podatkov potrebna nastavitev zasebne povezave Azure Azure Data Lake Storage račun, ker je za požarnim zidom. Dataverse trenutno ne podpira povezave z zasebnimi končnimi točkami prek zasebne povezave.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Varnostne skupine nastavite sami Azure Data Lake Storage

1. Ustvarite dve varnostni skupini v svoji naročnini na Azure – eno **Uporabnik z dovoljenjem za branje** varnostna skupina in ena **sodelavec** varnostno skupino in nastavite Microsoft Dataverse storitev kot lastnik za obe varnostni skupini.

1. Upravljajte seznam za nadzor dostopa (ACL) na`customerinsights` vsebnik v vašem računu za shranjevanje prek teh varnostnih skupin.
   1. Dodajte Microsoft Dataverse storitev in karkoli Dataverse poslovne aplikacije, kot je Dynamics 365 Marketing **Uporabnik z dovoljenjem za branje** varnostna skupina z **le za branje** dovoljenja.
   1. Dodaj *samo* aplikacijo Customers Insights za **sodelavec** varnostna skupina za odobritev obeh **beri in piši** dovoljenja za pisanje profilov in vpogledov.

### <a name="set-up-powershell"></a>Nastavite PowerShell

Nastavite PowerShell za izvajanje skriptov PowerShell.

1. Namestite najnovejšo različico [Azure Active Directory PowerShell za Graph](/powershell/azure/active-directory/install-adv2).
   1. V računalniku izberite tipko Windows na tipkovnici in poiščite **Windows PowerShell** in izberite **Zaženi kot skrbnik**.
   1. V oknu PowerShell, ki se odpre, vnesite `Install-Module AzureAD`.

1. Uvozite tri module.
   1. V oknu PowerShell vnesite`Install-Module -Name Az.Accounts` in sledite korakom.
   1. Ponovi za`Install-Module -Name Az.Resources` in `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Izvedite skripte PowerShell in pridobite identifikator dovoljenja

1. Od našega inženirja prenesite dva skripta PowerShell, ki ju potrebujete za zagon [GitHub repo](https://github.com/trin-msft/byol).
   - `CreateSecurityGroups.ps1`: zahteva skrbniška dovoljenja najemnika.
   - `ByolSetup.ps1`: Zahteva dovoljenja lastnika podatkov Storage Blob na ravni računa/vsebnika za shranjevanje. Ta skript bo ustvaril dovoljenje za vas. Vašo dodelitev vloge lahko ročno odstranite po uspešnem izvajanju skripta.

1. Izvedi`CreateSecurityGroups.ps1` v lupini Windows PowerShell tako, da zagotovite ID naročnine Azure, ki vsebuje vaše Azure Data Lake Storage. Odprite skript PowerShell v urejevalniku, da si ogledate dodatne informacije in implementirano logiko.

   Ta skript ustvari dve varnostni skupini v vaši naročnini na Azure: eno za skupino Uporabnik z dovoljenjem za branje in drugo za skupino sodelavec. Microsoft Dataverse storitev je lastnik obeh varnostnih skupin.

1. Shranite obe vrednosti ID-ja varnostne skupine, ki jih ustvari ta skript, da jih uporabite v`ByolSetup.ps1` scenarij.

   > [!NOTE]
   > Ustvarjanje varnostne skupine lahko onemogočite na vašem najemniku. V tem primeru bi bila potrebna ročna nastavitev in vaša Azure AD admin bi moral [omogoči ustvarjanje varnostne skupine](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Izvedi`ByolSetup.ps1` v lupini Windows PowerShell tako, da zagotovite ID naročnine Azure, ki vsebuje vaše Azure Data Lake Storage, ime računa za shranjevanje, ime skupine virov ter vrednosti ID-ja varnostne skupine Uporabnik z dovoljenjem za branje in sodelavec. Odprite skript PowerShell v urejevalniku, da si ogledate dodatne informacije in implementirano logiko.

   Ta skript doda zahtevan nadzor dostopa na podlagi vloge za Microsoft Dataverse storitev in karkoli Dataverse poslovne aplikacije. Prav tako posodobi seznam za nadzor dostopa (ACL) na`customerinsights` vsebnik za varnostne skupine, ustvarjene z`CreateSecurityGroups.ps1` scenarij. Podana je skupina sodelavec *rwx* je dano dovoljenje in skupina bralcev *rx* samo dovoljenje.

1. Kopirajte izhodni niz, ki je videti tako:`https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Vnesite kopirani izhodni niz v **Identifikator dovoljenj** polje konfiguracijskega koraka okolja za Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Možnosti konfiguracije za omogočanje skupne rabe podatkov iz lastnega Azure Data Lake Storage z Microsoft Dataverse .":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Odstranite obstoječo povezavo z a Dataverse okolju

Pri povezovanju z a Dataverse okolje, sporočilo o napaki **Ta organizacija CDS je že povezana z drugim primerkom Customer Insights** pomeni, da Dataverse okolje se že uporablja v okolju Customer Insights. Obstoječo povezavo lahko odstranite kot globalni skrbnik na Dataverse okolju. Vnos sprememb lahko traja nekaj ur.

1. Obiščite spletno mesto [Power Apps](https://make.powerapps.com).
1. V izbirniku okolja izberite okolje.
1. Pojdi do **Rešitve**.
1. Odstranite ali izbrišite imenovano rešitev **Dynamics 365 Customer Insights Dodatek kartice stranke (predogled)**.

ALI

1. Odpri svojo Dataverse okolju.
1. Pojdi do **Napredne nastavitve** > **Rešitve**.
1. Odstranite **CustomerInsightsCustomerCard** rešitev.

Če odstranitev povezave ne uspe zaradi odvisnosti, morate odstraniti tudi odvisnosti. Za več informacij glejte [Odstranjevanje odvisnosti](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Izhodne entitete

Nekatere izhodne entitete iz Customer Insights so na voljo kot tabele v Dataverse. Spodnji razdelki opisujejo pričakovano shemo teh tabel.

- [CustomerProfile](#customerprofile)
- [ContactProfile](#contactprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Obogatitev](#enrichment)
- [Predvidevanje](#prediction)
- [Članstvo v segmentu](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Ta tabela vsebuje poenoteni profil stranke iz Customer Insights. Shema za poenoten profil stranke je odvisna od entitet in atributov, uporabljenih v procesu poenotenja podatkov. Shema profila stranke običajno vsebuje podmnožico atributov iz [definicije Common Data Model atributa CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile). Za scenarij B-to-B profil stranke vsebuje poenotene račune, shema pa običajno vsebuje podnabor atributov iz [Definicija skupnega podatkovnega modela računa](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account).

### <a name="contactprofile"></a>ContactProfile

ContactProfile vsebuje enotne informacije o stiku. Stiki so [posamezniki, ki so preslikani v račun](data-unification-contacts.md) v scenariju od B do B.

| Column                       | Vnesi                | Description     |
| ---------------------------- | ------------------- | --------------- |
|  Rojstni datum            | Datum/ura       |  Rojstni datum stika               |
|  Mesto                 | SMS-a |  Mesto kontaktnega naslova               |
|  ContactId            | SMS-a |  ID kontaktnega profila               |
|  ContactProfileId     | Enolični identifikator   |  GUID za stik               |
|  DržavaAliRegija      | SMS-a |  Država/regija kontaktnega naslova               |
|  CustomerId           | SMS-a |  ID računa, v katerega je preslikan stik               |
|  EntityName           | SMS-a |  Entiteta, iz katere prihajajo podatki                |
|  FirstName            | SMS-a |  Ime kontakta               |
|  Spol               | SMS-a |  Spol stika               |
|  ID                   | SMS-a |  Deterministični GUID, ki temelji na`Identifier`               |
|  Identifier           | SMS-a |  Notranji ID kontaktnega profila:`ContactProfile|CustomerId|ContactId`               |
|  JobTitle             | SMS-a |  Naziv delovnega mesta kontakta               |
|  LastName             | SMS-a |  Priimek kontakta               |
|  PostalCode           | SMS-a |  Poštna številka kontaktnega naslova               |
|  Primarni e-poštni naslov         | SMS-a |  E-poštni naslov kontakta               |
|  Primarni telefon         | SMS-a |  Telefonska številka kontakta               |
|  Zvezna država ali območje      | SMS-a |  Država ali provinca kontaktnega naslova               |
|  Naslov ceste        | SMS-a |  Ulica kontaktnega naslova               |

### <a name="alternatekey"></a>AlternateKey

Tabela AlternateKey vsebuje ključe entitet, ki so sodelovale v postopku poenotenja.

|Column  |Vnesi  |Description  |
|---------|---------|---------|
|DataSourceName    |SMS-a         | Ime vira podatkov. Primer: `datasource5`.        |
|EntityName        | SMS-a        | Ime subjekta v Customer Insights. Primer: `contact1`.        |
|AlternateValue    |SMS-a         |Nadomestni ID, ki se preslika na ID stranke. Primer: `cntid_1078`         |
|KeyRing           | SMS-a        | Vrednost JSON  </br> Vzorec: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | SMS-a        | ID poenotenega profila stranke.         |
|AlternateKeyId     | Enolični identifikator        |  AlternateKey deterministični GUID, ki temelji na`Identifier`      |
|Identifier |   SMS-a      |   `DataSourceName|EntityName|AlternateValue`  </br> Vzorec: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Ta tabela vsebuje dejavnosti uporabnikov, ki so na voljo v Customer Insights.

| Column            | Vnesi        | Description                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | SMS-a      | ID profila stranke                                                                      |
| ActivityId        | SMS-a      | Interni ID dejavnosti stranke (primarni ključ)                                       |
| SourceEntityName  | SMS-a      | Ime izvorne entitete                                                                |
| SourceActivityId  | SMS-a      | Primarni ključ izvorne entitete                                                       |
| ActivityType      | SMS-a      | Vrsta semantične dejavnosti ali ime dejavnosti po meri                                        |
| ActivityTimeStamp | Datum/ura    | Časovni žig dejavnosti                                                                      |
| Naziv             | SMS-a      | Naziv ali ime dejavnosti                                                               |
| Description       | SMS-a      | Opis dejavnosti                                                                     |
| URL               | SMS-a      | Povezava do zunanjega URL-ja, specifičnega za dejavnost                                         |
| SemanticData      | SMS-a | Vključuje seznam parov ključnih vrednosti za semantična polja preslikave, specifična za vrsto dejavnosti |
| RangeIndex        | SMS-a      | Časovni žig Unix, ki se uporablja za razvrščanje časovnice dejavnosti in poizvedb obseg v uporabi |
| UnifiedActivityId   | Enolični identifikator | Interni ID dejavnosti stranke (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Ta tabela vsebuje izhodne podatke ukrepov, ki temeljijo na atributih strank.

| Column             | Vnesi             | Description                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | SMS-a           | ID profila stranke        |
| Mere           | SMS-a      | Vključuje seznam parov ključnih vrednosti za ime in vrednosti ukrepa za določeno stranko |
| Identifier | SMS-a           | `Customer_Measure|CustomerId` |
| CustomerMeasureId | Enolični identifikator     | ID profila stranke |

### <a name="enrichment"></a>Obogatitev

Ta tabela vsebuje rezultat postopka obogatitve.

| Column               | Vnesi             |  Description                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | SMS-a           | ID profila stranke                                 |
| EnrichmentProvider   | SMS-a           | Ime ponudnika obogatitve                                  |
| EnrichmentType       | SMS-a           | Vrsta obogatitve                                      |
| Vrednosti               | SMS-a      | Seznam atributov, pridobljenih v postopku obogatitve |
| EnrichmentId | Enolični identifikator            | Deterministični GUID, ustvarjen iz`Identifier` |
| Identifier   | SMS-a           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Predvidevanje

Ta tabela vsebuje rezultat predvidevanj modela.

| Column               | Vnesi        | Description                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | SMS-a      | ID profila stranke                                  |
| ModelProvider        | SMS-a      | Ime ponudnika modela                                      |
| Model                | SMS-a      | Ime modela                                                |
| Vrednosti               | SMS-a | Seznam atributov, ki jih izdela model |
| PredictionId | Enolični identifikator       | Deterministični GUID, ustvarjen iz`Identifier` |
| Identifier   | SMS-a      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Članstvo v segmentu

Ta tabela vsebuje informacije o članstvu v segmentih profilov strank.

| Column        | Vnesi | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | SMS-a       | ID profila stranke        |
| SegmentProvider      | SMS-a       | Aplikacija, ki objavlja segmente.      |
| SegmentMembershipType | SMS-a       | Vrsta stranke za zapis članstva v tem segmentu. Podpira več vrst, kot so stranka, stik ali račun. Privzeto: Stranka  |
| Segmenti       | SMS-a  | Seznam edinstvenih segmentov, katerih član je profil stranke      |
| Identifier  | SMS-a   | Enolični identifikator zapisa članstva v segmentu. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| SegmentMembershipId | Enolični identifikator      | Deterministični GUID, ustvarjen iz`Identifier`          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
