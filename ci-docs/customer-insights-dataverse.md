---
title: Delo s podatki Customer Insights v okolju Microsoft Dataverse
description: Naučite se, kako povezati Customer Insights in Microsoft Dataverse in razumeti izhodne entitete, ki so izvoženi v Dataverse.
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 3848e143bc7cb2f345bc698a274b92148ef00669
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833696"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Delo s podatki Customer Insights v okolju Microsoft Dataverse

Customer Insights ponuja možnost, da izhodne entitete omogočite kot [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Ta integracija omogoča preprosto izmenjavo podatkov in razvoj po meri s pristopom z nizko kodo/brez kode. The [izhodne entitete](#output-entities) so na voljo kot tabele v a Dataverse okolje. Podatke lahko uporabite za katero koli drugo aplikacijo, ki temelji na Dataverse mize. Te tabele omogočajo scenarije, kot so avtomatizirani potek dela Power Automate ali ustvarjanje aplikacij z Power Apps.

Povezovanje z vašim Dataverse okolje vam tudi omogoča [prenesite podatke iz virov podatkov na mestu uporabe z uporabo Power Platform podatkovnih tokov in prehodov](data-sources.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Zahteve

- Vpogled v stranke in Dataverse okolja morajo gostovati v isti regiji.
- Imeti morate vlogo globalnega skrbnika v Dataverse okolje. Preverite, če je to [Dataverse okolje je povezano](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) v določene varnostne skupine in se prepričajte, da ste dodani v te varnostne skupine.
- Nobeno drugo okolje Customer Insights ni že povezano z Dataverse okolje, ki ga želite povezati. Naučite se [odstranite obstoječo povezavo z a Dataverse okolje](#remove-an-existing-connection-to-a-dataverse-environment).
- A Microsoft Dataverse okolje se lahko poveže samo z enim računom za shranjevanje. Velja le, če konfigurirate okolje na [uporabite svoje Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Povežite a Dataverse okolje za vpogled v stranke

The **Microsoft Dataverse** korak vam omogoča, da povežete Customer Insights z vašim Dataverse okolje, medtem ko [ustvarjanje okolja Customer Insights](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="deljenje podatkov z Microsoft Dataverse samodejno omogočeno za net nova okolja.":::

Skrbniki lahko konfigurirajo Customer Insights za povezavo obstoječega Dataverse okolje. Z posredovanjem URL-ja za Dataverse okolju, se povezuje z njihovim novim okoljem Customer Insights.

Če ne želite uporabiti obstoječega Dataverse okolje, sistem ustvari novo okolje za podatke Customer Insights v vašem najemniku. [Power Platform skrbniki lahko nadzorujejo, kdo lahko ustvarja okolja](/power-platform/admin/control-environment-creation). Ko nastavljate novo okolje Customer Insights in je skrbnik onemogočil ustvarjanje Dataverse okolja za vse, razen za skrbnike, morda ne boste mogli ustvariti novega okolja.

**Omogoči skupno rabo podatkov** z Dataverse tako, da izberete potrditveno polje za izmenjavo podatkov.

Če uporabljate svoj račun Data Lake Storage, potrebujete tudi **Identifikator dovoljenj**. Za več informacij o tem, kako pridobiti identifikator dovoljenja, preberite naslednji razdelek.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Omogoči skupno rabo podatkov z Dataverse od svojega Azure Data Lake Storage (predogled)

Omogočanje skupne rabe podatkov z Microsoft Dataverse ko vaše okolje [uporablja svoje Azure Data Lake Storage račun](own-data-lake-storage.md) potrebuje dodatno konfiguracijo. Uporabnik, ki nastavlja okolje Customer Insights, mora imeti vsaj **Podatki blobov za shranjevanje Uporabnik z dovoljenjem za branje** dovoljenja za *CustomerInsights* posoda v Azure Data Lake Storage račun.

1. Ustvarite dve varnostni skupini v svoji naročnini na Azure – eno **Uporabnik z dovoljenjem za branje** varnostna skupina in ena **sodelavec** varnostno skupino in nastavite Microsoft Dataverse kot lastnik za obe varnostni skupini.
2. Upravljajte seznam za nadzor dostopa (ACL) v vsebniku CustomerInsights v vašem računu za shranjevanje prek teh varnostnih skupin. Dodajte Microsoft Dataverse storitev in vse Dataverse poslovne aplikacije, kot je Dynamics 365 Marketing za **Uporabnik z dovoljenjem za branje** varnostna skupina z **le za branje** dovoljenja. Dodaj *samo* aplikacijo Customers Insights za **sodelavec** varnostna skupina za odobritev obojega **beri in piši** dovoljenja za pisanje profilov in vpogledov.

### <a name="limitations"></a>Omejitve

Pri uporabi sta dve omejitvi Dataverse s svojimi Azure Data Lake Storage račun:

- Obstaja preslikava ena proti ena med a Dataverse organizacija in an Azure Data Lake Storage račun. Enkrat a Dataverse je organizacija povezana z računom za shranjevanje, se ne more povezati z drugim računom za shranjevanje. Ta omejitev preprečuje, da bi a Dataverse ne zapolni več računov za shranjevanje.
- Skupna raba podatkov ne bo delovala, če je za dostop do vašega računa za shranjevanje podatkov Azure Data Lake potrebna nastavitev zasebne povezave Azure, ker je za požarnim zidom. Dataverse trenutno ne podpira povezave z zasebnimi končnimi točkami prek zasebne povezave.

### <a name="set-up-powershell"></a>Nastavite PowerShell

Če želite izvesti skripte PowerShell, morate najprej ustrezno nastaviti PowerShell.

1. Namestite najnovejšo različico [Azure Active Directory PowerShell za graf](/powershell/azure/active-directory/install-adv2).
   1. V računalniku izberite tipko Windows na tipkovnici in poiščite **Windows PowerShell** in izberite **Zaženi kot skrbnik**.
   1. V oknu PowerShell, ki se odpre, vnesite `Install-Module AzureAD`.
2. Uvozi tri module.
    1. V oknu PowerShell vnesite`Install-Module -Name Az.Accounts` in sledite korakom.
    1. Ponovite za`Install-Module -Name Az.Resources` in `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Koraki konfiguracije

1. Prenesite dva skripta PowerShell, ki ju morate zagnati, od našega inženirja [GitHub repo](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Potrebujete *skrbnik najemnika* dovoljenja za zagon tega skripta PowerShell.
       - Ta skript PowerShell ustvari dve varnostni skupini v vaši naročnini na Azure. Ena za skupino Uporabnik z dovoljenjem za branje in druga za skupino sodelavec in bo Microsoft Dataverse kot lastnik obeh varnostnih skupin.
       - Izvedite ta skript PowerShell v Windows PowerShell tako, da zagotovite ID naročnine Azure, ki vsebuje vaš Azure Data Lake Storage. Odprite skript PowerShell v urejevalniku, da si ogledate dodatne informacije in implementirano logiko.
       - Shranite obe vrednosti ID-ja varnostne skupine, ki ju generira ta skript, ker ju bomo uporabili v`ByolSetup.ps1` skripta.

        > [!NOTE]
        > Ustvarjanje varnostne skupine je mogoče onemogočiti v vašem najemniku. V tem primeru bi bila potrebna ročna nastavitev in vaša Azure AD admin bi moral [omogoči ustvarjanje varnostne skupine](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Potrebujete *Lastnik podatkov shranjevalnih blokov* dovoljenja na ravni računa za shranjevanje/vsebnika za zagon tega skripta ali pa ga bo ta skript ustvaril za vas. Vašo dodelitev vloge lahko ročno odstranite po uspešnem zagonu skripta.
        - Ta skript PowerShell doda zahtevan nadzor dostopa na osnovi tole (RBAC) za Microsoft Dataverse storitev in vse Dataverse -poslovne aplikacije. Prav tako posodobi seznam nadzora dostopa (ACL) v vsebniku CustomerInsights za varnostne skupine, ustvarjene z`CreateSecurityGroups.ps1` skripta. Skupina sodelavec bo imela *rwx* dovoljenje in skupina bralcev bo imela *rx* samo dovoljenje.
        - Izvedite ta skript PowerShell v Windows PowerShell tako, da zagotovite ID naročnine Azure, ki vsebuje vaš Azure Data Lake Storage, ime računa za shranjevanje, ime skupine sredstev ter vrednosti ID-ja varnostne skupine Uporabnik z dovoljenjem za branje in sodelavec. Odprite skript PowerShell v urejevalniku, da si ogledate dodatne informacije in implementirano logiko.
        - Kopirajte izhodni niz po uspešnem zagonu skripta. Izhodni niz izgleda takole:`https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Vnesite izhodni niz, kopiran od zgoraj, v **Identifikator dovoljenj** polje koraka konfiguracije okolja za Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Možnosti konfiguracije za omogočanje lastne skupne rabe podatkov Azure Data Lake Storage z Microsoft Dataverse .":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Odstranite obstoječo povezavo z a Dataverse okolje

Ko se povežete z a Dataverse okolje, sporočilo o napaki **Ta organizacija CDS je že povezana z drugim primerkom Customer Insights** pomeni, da Dataverse okolje se že uporablja v okolju Customer Insights. Obstoječo povezavo lahko odstranite kot globalni skrbnik na Dataverse okolje. Zapolnitev sprememb lahko traja nekaj ur.

1. Obiščite spletno mesto [Power Apps](https://make.powerapps.com).
1. Izberite okolje v izbirniku okolja.
1. Pojdi do **Rešitve**
1. Odstranite ali izbrišite imenovano rešitev **Dynamics 365 Customer Insights Dodatek za kartico stranke (predogled)**.

ALI

1. Odprite svojo Dataverse okolje.
1. Pojdi do **Napredne nastavitve** > **Rešitve**.
1. Odstranite **CustomerInsightsCustomerCard** rešitev.

Če odstranitev povezave ne uspe zaradi odvisnosti, morate odstraniti tudi odvisnosti. Za več informacij glejte [Odstranjevanje odvisnosti](/power-platform/alm/removing-dependencies).

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

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
