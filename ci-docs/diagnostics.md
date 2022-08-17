---
title: Izvoz diagnostičnih dnevnikov (predogled)
description: Naučite se pošiljati dnevnike na Microsoft Azure Monitor.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 60b039173fd938482c782c7394420d4951c222a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245945"
---
# <a name="export-diagnostic-logs-preview"></a>Izvoz diagnostičnih dnevnikov (predogled)

Posredujte dnevnike iz Customer Insights z uporabo Azure Monitor. Dnevniki virov Azure Monitor vam omogočajo spremljanje in pošiljanje dnevnikov [Azure Storage](https://azure.microsoft.com/services/storage/),[Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview), ali jih pretakajte na [Azure Središča za dogodke](https://azure.microsoft.com/services/event-hubs/).

Customer Insights pošlje naslednje dnevnike dogodkov:

- **Revizijski dogodki**
  - **APIEvent** - omogoča sledenje spremembam preko Dynamics 365 Customer Insights uporabniški vmesnik.
- **Operativni dogodki**
  - **WorkflowEvent** - vam omogoča nastavitev [viri podatkov](data-sources.md),[poenotiti](data-unification.md),[obogatiti](enrichment-hub.md), in [izvoz](export-destinations.md) podatke v druge sisteme. Te korake je mogoče izvesti posamično (na primer sprožiti en izvoz). Lahko se izvajajo tudi orkestrirano (na primer osvežitev podatkov iz podatkovnih virov, ki sprožijo proces poenotenja, ki bo pritegnil obogatitve in izvozil podatke v drug sistem). Za več informacij glejte [Shema WorkflowEvent](#workflow-event-schema).
  - **APIEvent** - pošilja vse klice API-ja instance stranke Dynamics 365 Customer Insights. Za več informacij glejte [Shema APIEvent](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Nastavite diagnostične nastavitve

### <a name="prerequisites"></a>Zahteve

- Aktiven [Naročnina na Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- [Administrator](permissions.md#admin) dovoljenja v Customer Insights.
- [sodelavec in vloga skrbnika uporabniškega dostopa](/azure/role-based-access-control/role-assignments-portal) na ciljnem viru v Azure. Vir je lahko Azure Data Lake Storage račun, središče dogodkov Azure ali delovni prostor Azure Log Analytics. To dovoljenje je potrebno med konfiguriranjem diagnostičnih nastavitev v Customer Insights, vendar ga je mogoče spremeniti po uspešni nastavitvi.
- [Zahteve glede cilja](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) za Azure Storage, Azure Event Hub ali Azure Log Analytics.
- Vsaj **Uporabnik z dovoljenjem za branje** vlogo v skupini virov, ki ji vir pripada.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Nastavite diagnostiko z Azure Monitor

1. V Customer Insights pojdite na **skrbnik** > **Sistem** in izberite **Diagnostika** zavihek.

1. Izberite **Dodaj cilj**.

   :::image type="content" source="media/diagnostics-pane.png" alt-text="Diagnostična povezava.":::

1. Navedite ime v **Ime za cilj diagnostike** polje.

1. Izberite **Vrsta vira** (Storage Account, Event Hub ali Log Analytics).

1. Izberite **Naročnina**, **virov**, in **Vir** za ciljni vir. glej [Konfiguracija na ciljnem viru](#configuration-on-the-destination-resource) za dovoljenje in podatke dnevnika.

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite **Povežite se s sistemom** za povezavo s ciljnim virom. Dnevniki se začnejo pojavljati na cilju po 15 minutah, če je API v uporabi in ustvarja dogodke.

## <a name="configuration-on-the-destination-resource"></a>Konfiguracija na ciljnem viru

Na podlagi vaše izbire vrste vira se samodejno zgodijo naslednje spremembe:

### <a name="storage-account"></a>Račun za shrambo

Vodja storitve Customer Insights dobi **Račun za shranjevanje sodelavec** dovoljenje za izbrani vir in ustvari dva vsebnika pod izbranim imenskim prostorom:

- `insight-logs-audit` ki vsebuje **revizijski dogodki**
- `insight-logs-operational` ki vsebuje **operativni dogodki**

### <a name="event-hub"></a>Središče za dogodke

Vodja storitve Customer Insights dobi **Lastnik podatkov Azure Središča za dogodke** dovoljenje za vir in ustvari dva Središča za dogodke pod izbranim imenskim prostorom:

- `insight-logs-audit` ki vsebuje **revizijski dogodki**
- `insight-logs-operational` ki vsebuje **operativni dogodki**

### <a name="log-analytics"></a>Log Analytics

Vodja storitve Customer Insights dobi **Log Analytics sodelavec** dovoljenje za vir. Dnevniki so na voljo pod **Dnevniki** > **Mize** > **Upravljanje dnevnika** v izbranem delovnem prostoru Log Analytics. Razširite **Upravljanje dnevnika** rešitev in poiščite`CIEventsAudit` in`CIEventsOperational` mize.

- `CIEventsAudit` ki vsebuje **revizijski dogodki**
- `CIEventsOperational` ki vsebuje **operativni dogodki**

Pod **Poizvedbe** okno, razširite **revizija** rešitev in poiščite primere poizvedb, ki jih dobite pri iskanju `CIEvents`.

## <a name="remove-a-diagnostics-destination"></a>Odstranite cilj diagnostike

1. Pojdi do **skrbnik** > **Sistem** in izberite **Diagnostika** zavihek.

1. Na seznamu izberite cilj diagnostike.

   > [!TIP]
   > Odstranitev cilja ustavi posredovanje dnevnika, vendar ne izbriše vira v naročnini Azure. Če želite izbrisati vir v Azure, izberite povezavo v **Dejanja** stolpec, da odprete portal Azure za izbrani vir in ga tam izbrišete. Nato izbrišite cilj diagnostike.

1. V **Dejanja** izberite stolpec **Izbriši** ikona.

1. Potrdite izbris, da odstranite cilj in ustavite posredovanje dnevnika.

## <a name="log-categories-and-event-schemas"></a>Kategorije dnevnika in sheme dogodkov

Trenutno [API dogodki](apis.md) in dogodki poteka dela so podprti in veljajo naslednje kategorije in sheme.
Shema dnevnika sledi [Skupna shema Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategorije

Customer Insights nudi dve kategoriji:

- **Revizijski dogodki** :[API dogodki](#api-event-schema) za sledenje spremembam konfiguracije storitve. `POST|PUT|DELETE|PATCH` operacije spadajo v to kategorijo.
- **Operativni dogodki** :[API dogodki](#api-event-schema) oz [dogodki delovnega toka](#workflow-event-schema) ki nastane med uporabo storitve.  npr.`GET` zahteve ali dogodke izvajanja delovnega toka.

## <a name="event-schemas"></a>Sheme dogodkov

Dogodki API-ja in dogodki poteka dela imajo skupno strukturo, vendar z nekaj razlikami. Za več informacij glejte [Shema dogodkov API](#api-event-schema) oz [shema dogodkov poteka dela](#workflow-event-schema).

### <a name="api-event-schema"></a>Shema dogodkov API

| Polje             | DataType  | Obvezno/izbirno | Description       | Primer        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Časovni žig | Zahtevano          | Časovni žig dogodka (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Zahtevano          | ResourceId primerka, ki je sprožil dogodek         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Zahtevano          | Ime operacije, ki jo predstavlja ta dogodek.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Zahtevano          | Kategorija dnevnika dogodka. Bodisi`Operational` oz `Audit`. Vse HTTP zahteve POST/PUT/PATCH/DELETE so označene z`Audit`, vse ostalo z`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Zahtevano          | Status dogodka. `Success`,`ClientError`,`Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Po izbiri          | Rezultatski status dogodka. Če operacija ustreza klicu REST API, je to statusna koda HTTP.        | `200`             |
| `durationMs`      | Dolgo      | Po izbiri          | Trajanje operacije v milisekundah.     | `133`     |
| `callerIpAddress` | String    | Po izbiri          | Naslov IP kličočega, če operacija ustreza klicu API-ja, ki prihaja iz javno dostopnega naslova IP.                                                 | `144.318.99.233`         |
| `identity`        | String    | Po izbiri          | Objekt JSON, ki opisuje identiteto uporabnika ali aplikacije, ki je izvedla operacijo.       | glej [Identiteta](#identity-schema) razdelek.     |  
| `properties`      | String    | Po izbiri          | Objekt JSON z več lastnostmi za določeno kategorijo dogodkov.      | glej [Lastnosti](#api-properties-schema) razdelek.    |
| `level`           | String    | Zahtevano          | Stopnja resnosti dogodka.    | `Informational`,`Warning`,`Error`, oz `Critical`.           |
| `uri`             | String    | Po izbiri          | Absolutni URI zahteve.    |               |

#### <a name="identity-schema"></a>Shema identitete

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
| `Claims`                      | Zahtevki spletnega žetona JSON (JWT) uporabnika ali aplikacije. Lastnosti zahtevkov se razlikujejo glede na organizacijo in Azure Active Directory konfiguracijo. |

#### <a name="api-properties-schema"></a>Shema lastnosti API-ja

[API dogodki](apis.md) imajo naslednje lastnosti.

| Polje                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Nenehno`ApiEvent`, ki dogodek dnevnika označi kot dogodek API-ja.                                                                 |
| `properties.userAgent`       | Agent brskalnika, ki pošilja zahtevo oz `unknown`.                                                                        |
| `properties.method`          | Metoda HTTP:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Relativna pot zahteve.                                                                                          |
| `properties.origin`          | URI, ki označuje, od kod izvira pridobivanje oz `unknown`.                                                                  |
| `properties.operationStatus` | `Success` za kodo stanja HTTP < 400 <br> `ClientError` za kodo stanja HTTP < 500 <br> `Error` za HTTP status >= 500 |
| `properties.tenantId`        | ID organizacije                                                                                                        |
| `properties.tenantName`      | Ime organizacije.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjectId klicatelja.                                                                         |
| `properties.instanceId`      | Vpogledi strank`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Shema dogodkov poteka dela

Potek dela vsebuje več korakov. [Zaužijte vire podatkov](data-sources.md),[poenotiti](data-unification.md),[obogatiti](enrichment-hub.md), in [izvoz](export-destinations.md) podatke. Vsi ti koraki se lahko izvajajo posamezno ali orkestrirano z naslednjimi procesi.

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
| AttributeMeasures | [Segmenti in mere](segments.md)      |
| EntityMeasures    | [Segmenti in mere](segments.md)      |
| Mere          | [Segmenti in mere](segments.md)      |
| Segmentacija      | [Segmenti in mere](segments.md)      |
| Obogatitev        | [Obogatitev](enrichment-hub.md)                                          |
| Obveščanje      | [Predvidevanja](predictions-overview.md)                                          |
| AiBuilder         | [Predvidevanja](predictions-overview.md)                                          |
| Vpogledi          | [Predvidevanja](predictions-overview.md)                                          |
| Export            | [Izvozi](export-destinations.md)                                          |
| ModelManagement   | [Predvidevanja](custom-models.md)                                           |
| Odnos      | [Poenotenje podatkov](relationships.md)                                           |

#### <a name="field-description"></a>Opis polja

| Polje           | DataType  | Obvezno/izbirno | Description                                                                                                                                                   | Primer                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Časovni žig | Zahtevano          | Časovni žig dogodka (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Zahtevano          | ResourceId primerka, ki je sprožil dogodek.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Zahtevano          | Ime operacije, ki jo predstavlja ta dogodek. `{OperationType}.[WorkFlow|Task][Started|Completed]`. glej [Vrste operacij](#operation-types) za referenco. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Zahtevano          | Kategorija dnevnika dogodka. Nenehno`Operational` za dogodke poteka dela                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Zahtevano          | Status dogodka. `Running`,`Skipped`,`Successful`,`Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Dolgo      | Po izbiri          | Trajanje operacije v milisekundah.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Po izbiri          | Objekt JSON z več lastnostmi za določeno kategorijo dogodkov.                                                                                        | Glej pododdelek [Lastnosti poteka dela](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Zahtevano          | Stopnja resnosti dogodka.                                                                                                                                  | `Informational`, `Warning` ali `Error`                                                                                                                                   |

#### <a name="workflow-properties-schema"></a>Shema lastnosti delovnega toka

Dogodki poteka dela imajo naslednje lastnosti.

| Polje              | Workflow | opravilo, | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Da      | Da  | Nenehno`WorkflowEvent`, ki dogodek označi kot dogodek poteka dela.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Da      | Da  | Identifikator poteka delovnega toka. Vsi dogodki delovnega toka in opravila znotraj izvajanja delovnega toka imajo enako `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Da      | Da  | Identifikator operacije, glej [Vrste operacij](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Da      | No   | Samo potek dela. Število opravil, ki jih sproži potek dela.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Da      | No   | Izbirno. Samo dogodki poteka dela. The Azure Active Directory [objectId uporabnika](/azure/marketplace/find-tenant-object-id#find-user-object-id) kdo je sprožil potek dela, glejte tudi `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Da      | No   | `full` oz`incremental` osveži.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Da      | No   | `OnDemand` ali `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Da      | No   | `Running` oz `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Da      | Da  | Časovni žig UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Da      | Da  | Časovni žig UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Da      | Da  | Časovni žig UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Da      | Da  | Vpogledi strank`instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Da  | - Za OperationType =`Export`, je identifikator guid izvozne konfiguracije. <br> - Za OperationType =`Enrichment`, to je vodilo obogatitve <br> - Za OperationType`Measures` in`Segmentation`, identifikator je ime entitete. |
| `properties.friendlyName`                    | No       | Da  | Uporabniku prijazno ime izvoza ali subjekta, ki se obdeluje.                                                                                                                                                                                           |
| `properties.error`                           | No       | Da  | Izbirno. Sporočilo o napaki z več podrobnostmi.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Da  | Izbirno. Za OperationType`Export` samo. Določa vrsto izvoza. Za več informacij glejte [pregled izvoznih destinacij](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Da  | Izbirno. Za OperationType`Export` samo. Vsebuje seznam konfiguriranih entitet v izvozu.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Da  | Izbirno. Za OperationType`Export` samo. Podrobno sporočilo za izvoz.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Da  | Izbirno. Za OperationType`Segmentation` samo. Označuje skupno število članov, ki jih ima segment.                                                                                                                                                    |

[!INCLUDE [footer-include](includes/footer-banner.md)]
