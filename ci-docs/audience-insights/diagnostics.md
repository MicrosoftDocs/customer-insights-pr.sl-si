---
title: revizija Dynamics 365 Customer Insights z Azure Monitor
description: Naučite se pošiljati dnevnike na Microsoft Azure Monitor.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
ms.openlocfilehash: d962c359d70a068fcf939b61e340f86de088b419
ms.sourcegitcommit: 0c3c473e0220de9ee3c1f1ee1825de0b3b3663c3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920878"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Posredovanje dnevnika Dynamics 365 Customer Insights z Azure Monitor (predogled)

Dynamics 365 Customer Insights zagotavlja neposredno integracijo z Azure Monitor. Dnevniki virov Azure Monitor vam omogočajo spremljanje in pošiljanje dnevnikov [Azure Storage](https://azure.microsoft.com/services/storage/),[Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview), ali jih pretakajte na [Azure Središča za dogodke](https://azure.microsoft.com/services/event-hubs/).

Customer Insights pošilja naslednje dnevnike dogodkov:

- **Revizijski dogodki**
  - **APIEvent** - omogoča sledenje spremembam preko Dynamics 365 Customer Insights uporabniški vmesnik.
- **Operativni dogodki**
  - **WorkflowEvent** - Potek dela omogoča nastavitev [Viri podatkov](data-sources.md),[poenotiti](data-unification.md) in [obogatiti](enrichment-hub.md) in končno [izvoz](export-destinations.md) podatke v druge sisteme. Vse te korake je mogoče izvesti posamezno (npr. sprožiti en sam izvoz) ali organizirati (npr. osvežitev podatkov iz podatkovnih virov, ki sproži proces poenotenja, ki bo potegnil dodatne obogatitve in po končanem izvozu podatkov v drug sistem). Za več podrobnosti si oglejte [Shema dogodka delovnega toka](#workflow-event-schema).
  - **APIEvent** - vsi klici API-ja do primerka strank Dynamics 365 Customer Insights. Za več podrobnosti si oglejte [APIEvent shema](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Nastavite diagnostične nastavitve

### <a name="prerequisites"></a>Zahteve

Za konfiguriranje diagnostike v Customer Insights morajo biti izpolnjeni naslednji predpogoji:

- Imate aktivno [Naročnina na Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- Imaš [skrbnik](permissions.md#administrator) dovoljenja v Customer Insights.
- Imate **sodelavec** in **Skrbnik uporabniškega dostopa** vlogo na ciljnem viru v Azure. Vir je lahko račun Azure Storage, središče dogodkov Azure ali delovni prostor Azure Log Analytics. Za več informacij glejte [Dodajte ali odstranite dodelitve vlog Azure s portalom Azure](/azure/role-based-access-control/role-assignments-portal).
- [Zahteve za destinacijo](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) za Azure Storage, Azure Event Hub ali Azure Log Analytics met.
- Imate vsaj **Uporabnik z dovoljenjem za branje** vlogo v skupini virov, ki ji vir pripada.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Nastavite diagnostiko z Azure Monitor

1. V storitvi Customer Insights izberite **sistem** > **Diagnostika** za ogled diagnostičnih ciljev, ki so konfigurirani za ta primerek.

1. Izberite **Dodaj cilj**.

   > [!div class="mx-imgBorder"]
   > ![Diagnostična povezava](media/diagnostics-pane.png "Diagnostična povezava")

1. Navedite ime v **Ime za cilj diagnostike** polje.

1. Izberite **Najemnik** naročnine Azure s ciljnim virom in izberite **Vpiši se**.

1. Izberite **Vrsta vira** (Račun za shranjevanje, središče dogodkov ali analitika dnevnika).

1. Izberite **Naročnina** za ciljni vir.

1. Izberite **Skupina virov** za ciljni vir.

1. Izberite **Vir**.

1. Potrdite **Zasebnost podatkov in skladnost** izjava.

1. Izberite **Povežite se s sistemom** za povezavo s ciljnim virom. Dnevniki se začnejo pojavljati na ciljnem mestu po 15 minutah, če je API v uporabi in generira dogodke.

### <a name="remove-a-destination"></a>Odstranite cilj

1. Pojdi do **sistem** > **Diagnostika**.

1. Na seznamu izberite cilj diagnostike.

1. V **Dejanja** stolpec, izberite **Izbriši** ikona.

1. Potrdite izbris, da ustavite posredovanje dnevnika. Vir v naročnini Azure ne bo izbrisan. Povezavo lahko izberete v **Dejanja** stolpec, da odprete portal Azure za izbrani vir in ga tam izbrišete.

## <a name="log-categories-and-event-schemas"></a>Kategorije dnevnikov in sheme dogodkov

trenutno [API dogodki](apis.md) in dogodki poteka dela so podprti in veljajo naslednje kategorije in sheme.
Dnevniška shema sledi [Skupna shema Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategorije

Customer Insights ponuja dve kategoriji:

- **Revizijski dogodki** :[API dogodki](#api-event-schema) za sledenje spremembam konfiguracije storitve. `POST|PUT|DELETE|PATCH` operacije spadajo v to kategorijo.
- **Operativni dogodki** :[API dogodki](#api-event-schema) oz [dogodki poteka dela](#workflow-event-schema) ki nastane med uporabo storitve.  Na primer`GET` zahteve ali izvedbene dogodke delovnega toka.

## <a name="configuration-on-the-destination-resource"></a>Konfiguracija ciljnega vira

Glede na vašo izbiro vrste vira bodo samodejno uporabljeni naslednji koraki:

### <a name="storage-account"></a>Račun za shrambo

Direktor storitve Customer Insights prejme **Račun za shranjevanje sodelavec** dovoljenje za izbrani vir in ustvari dva vsebnika pod izbranim imenskim prostorom:

- `insight-logs-audit` ki vsebuje **revizijske dogodke**
- `insight-logs-operational` ki vsebuje **operativni dogodki**

### <a name="event-hub"></a>Središče za dogodke

Direktor storitve Customer Insights prejme **Lastnik podatkov Azure Središča za dogodke** dovoljenje za vir in bo ustvaril dva Središča za dogodke pod izbranim imenskim prostorom:

- `insight-logs-audit` ki vsebuje **revizijske dogodke**
- `insight-logs-operational` ki vsebuje **operativni dogodki**

### <a name="log-analytics"></a>Log Analytics

Direktor storitve Customer Insights prejme **Log Analytics sodelavec** dovoljenje za vir. Dnevniki bodo na voljo pod **Dnevniki** > **mize** > **Upravljanje dnevnikov** na izbranem delovnem prostoru Log Analytics. Razširite **Upravljanje dnevnikov** rešitev in poiščite`CIEventsAudit` in`CIEventsOperational` mize.

- `CIEventsAudit` ki vsebuje **revizijske dogodke**
- `CIEventsOperational` ki vsebuje **operativni dogodki**

Pod **Poizvedbe** okno, razširite **revizija** rešitev in poiščite primere poizvedb, ki ste jih dobili z iskanjem `CIEvents`.

## <a name="event-schemas"></a>Sheme dogodkov

Dogodki API in dogodki poteka dela imajo skupno strukturo in podrobnosti, kjer se razlikujejo, glej [Shema dogodkov API](#api-event-schema) oz [shema dogodkov poteka dela](#workflow-event-schema).

### <a name="api-event-schema"></a>Shema dogodkov API

| Polje             | DataType  | Obvezno/izbirno | Description       | Primer        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Časovni žig | Zahtevano          | Časovni žig dogodka (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Zahtevano          | ResourceId primerka, ki je oddal dogodek         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Zahtevano          | Ime operacije, ki jo predstavlja ta dogodek.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Zahtevano          | Kategorija dnevnika dogodka. bodisi`Operational` oz `Audit`. Vse zahteve HTTP POST/PUT/PATCH/DELETE so označene z`Audit`, vse ostalo z`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Zahtevano          | Stanje dogodka. `Success`,`ClientError`,`Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Po izbiri          | Status rezultata dogodka. Če operacija ustreza klicu REST API, je to koda stanja HTTP.        | `200`             |
| `durationMs`      | Dolgo      | Po izbiri          | Trajanje operacije v milisekundah.     | `133`     |
| `callerIpAddress` | String    | Po izbiri          | IP naslov klicatelja, če operacija ustreza klicu API, ki prihaja z javno dostopnega naslova IP.                                                 | `144.318.99.233`         |
| `identity`        | String    | Po izbiri          | Objekt JSON, ki opisuje identiteto uporabnika ali aplikacije, ki je opravila operacijo.       | Glej [Identiteta](#identity-schema) oddelek.     |  |
| `properties`      | String    | Po izbiri          | Objekt JSON z več lastnostmi za določeno kategorijo dogodkov.      | Glej [Lastnosti](#api-properties-schema) oddelek.    |
| `level`           | String    | Zahtevano          | Stopnja resnosti dogodka.    | `Informational`,`Warning`,`Error`, oz `Critical`.           |
| `uri`             | String    | Po izbiri          | URI absolutne zahteve.    |               |

#### <a name="identity-schema"></a>Identitetna shema

The`identity` Objekt JSON ima naslednjo strukturo

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Polje                         | Description                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Dodeljena vloga za uporabnika ali aplikacijo. Za več informacij glejte [uporabniška dovoljenja](permissions.md).                                     |
| `Authorization.RequiredRoles` | Zahtevane vloge za izvedbo operacije. `Admin` vlogi je dovoljeno izvajati vse operacije.                                                    |
| `Claims`                      | Zahtevki spletnega žetona JSON uporabnika ali aplikacije (JWT). Lastnosti zahtevka se razlikujejo glede na organizacijo in Azure Active Directory konfiguracijo. |

#### <a name="api-properties-schema"></a>Shema lastnosti API-ja

[API dogodki](apis.md) imajo naslednje lastnosti.

| Polje                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Nenehno`ApiEvent`, kar označi dogodek dnevnika kot dogodek API.                                                                 |
| `properties.userAgent`       | Agent brskalnika, ki pošlje zahtevo oz `unknown`.                                                                        |
| `properties.method`          | Metoda HTTP:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Relativna pot zahteve.                                                                                          |
| `properties.origin`          | URI, ki označuje, od kod prihaja pridobivanje oz `unknown`.                                                                  |
| `properties.operationStatus` | `Success` za kodo stanja HTTP < 400 <br> `ClientError` za kodo stanja HTTP < 500 <br> `Error` za stanje HTTP >= 500 |
| `properties.tenantId`        | ID organizacije                                                                                                        |
| `properties.tenantName`      | Ime organizacije.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjectId klicatelja.                                                                         |
| `properties.instanceId`      | Vpogled v stranke`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Shema dogodka poteka dela

Potek dela vsebuje več korakov. [Zaužijte vire podatkov](data-sources.md),[poenotiti](data-unification.md),[obogatiti](enrichment-hub.md), in [izvoz](export-destinations.md) podatkov. Vsi ti koraki se lahko izvajajo posamezno ali usklajeno z naslednjimi procesi. 

#### <a name="operation-types"></a>Vrste operacij

| OperationType     | Združi                                     |
| ----------------- | ----------------------------------------- |
| Zaužitje         | [Viri podatkov](data-sources.md)           |
| Priprava podatkov   | [Viri podatkov](data-sources.md)           |
| Preslikava               | [Poenotenje podatkov](data-unification.md)   |
| Povezovanje             | [Poenotenje podatkov](data-unification.md)   |
| Spajanje             | [Poenotenje podatkov](data-unification.md)   |
| ProfileStore      | [Profili strank](customer-profiles.md) |
| Poišči            | [Profili strank](customer-profiles.md) |
| Dejavnost          | [Dejavnosti](activities.md)                  |
| AttributeMeasures | [Segmenti in ukrepi](segments.md)      |
| EntityMeasures    | [Segmenti in ukrepi](segments.md)      |
| Mere          | [Segmenti in ukrepi](segments.md)      |
| Segmentacija      | [Segmenti in ukrepi](segments.md)      |
| Obogatitev        | [Obogatitev](enrichment-hub.md)                                          |
| Obveščanje      | [Predvidevanja](predictions-overview.md)                                          |
| AiBuilder         | [Predvidevanja](predictions-overview.md)                                          |
| Vpogledi          | [Predvidevanja](predictions-overview.md)                                          |
| Export            | [Izvozi](export-destinations.md)                                          |
| Upravljanje modelov   | [Predvidevanja](custom-models.md)                                           |
| Odnos      | [Poenotenje podatkov](relationships.md)                                           |

#### <a name="field-description"></a>Opis polja

| Polje           | DataType  | Obvezno/izbirno | Description                                                                                                                                                   | Primer                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Časovni žig | Zahtevano          | Časovni žig dogodka (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Zahtevano          | ResourceId primerka, ki je oddal dogodek.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Zahtevano          | Ime operacije, ki jo predstavlja ta dogodek. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Glej [Vrste operacij](#operation-types) za referenco. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Zahtevano          | Kategorija dnevnika dogodka. Nenehno`Operational` za dogodke delovnega toka                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | String    | Zahtevano          | Stanje dogodka. `Running`,`Skipped`,`Successful`,`Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Dolgo      | Po izbiri          | Trajanje operacije v milisekundah.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Po izbiri          | Objekt JSON z več lastnostmi za določeno kategorijo dogodkov.                                                                                        | Glej pododdelek [Lastnosti delovnega toka](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Zahtevano          | Stopnja resnosti dogodka.                                                                                                                                  | `Informational`, `Warning` ali `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Shema lastnosti delovnega toka

Dogodki poteka dela imajo naslednje lastnosti.

| Polje              | Workflow | opravilo, | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Da      | Da  | Nenehno`WorkflowEvent`, ki dogodek označi kot dogodek poteka dela.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Da      | Da  | Identifikator poteka delovnega toka. Vsi dogodki poteka dela in opravil v okviru izvajanja poteka dela imajo enake `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Da      | Da  | Identifikator operacije, glejte [Vrste operacij].(#operation-types)                                                                                                                                                                                       |
| `properties.tasksCount`                      | Da      | No   | Samo potek dela. Število opravil, ki jih sproži potek dela.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Da      | No   | Izbirno. Samo dogodki poteka dela. The Azure Active Directory [objectId uporabnika](/azure/marketplace/find-tenant-object-id#find-user-object-id) kdo je sprožil potek dela, glejte tudi `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Da      | No   | `full` oz`incremental` osveži.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Da      | No   | `OnDemand` ali `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Da      | No   | `Running` oz `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Da      | Da  | Časovni žig UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Da      | Da  | Časovni žig UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Da      | Da  | Časovni žig UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Da      | Da  | Vpogled v stranke`instanceId`                                                                                                                                                                                                                              |  |
| `properties.identifier`                      | No       | Da  | - Za OperationType =`Export`, je identifikator vodilo konfiguracije izvoza. <br> - Za OperationType =`Enrichment`, je vodilo za obogatitev <br> - Za OperationType`Measures` in`Segmentation`, identifikator je ime entitete. |
| `properties.friendlyName`                    | No       | Da  | Uporabniku prijazno ime izvoza ali subjekta, ki se obdeluje.                                                                                                                                                                                           |
| `properties.error`                           | No       | Da  | Izbirno. Sporočilo o napaki z več podrobnostmi.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Da  | Izbirno. Za OperationType`Export` samo. Označuje vrsto izvoza. Za več informacij glejte [pregled izvoznih destinacij](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Da  | Izbirno. Za OperationType`Export` samo. Vsebuje seznam konfiguriranih entitet v izvozu.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Da  | Izbirno. Za OperationType`Export` samo. Podrobno sporočilo za izvoz.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Da  | Izbirno. Za OperationType`Segmentation` samo. Označuje skupno število članov, ki jih ima segment.                                                                                                                                                    |
