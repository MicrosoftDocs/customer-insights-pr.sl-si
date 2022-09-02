---
title: Primeri poizvedb OData za API-je Customer Insights
description: Pogosto uporabljeni primeri za protokol odprtih podatkov (OData) za poizvedovanje API-jev Customer Insights za pregled podatkov.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 26e56a3bab01ba55284a52e72efbcbfbaadaad6f
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387222"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>Primeri poizvedb OData za API-je Customer Insights

Protokol odprtih podatkov (OData) je protokol za dostop do podatkov, ki temelji na osnovnih protokolih, kot je HTTP. Uporablja splošno sprejete metodologije, kot je REST za splet. Obstajajo različne vrste knjižnic in orodij, ki jih je mogoče uporabiti za uporabo storitev OData.

Za pomoč pri izdelavi lastnih implementacij na podlagi [API-ji Customer Insights](apis.md) , preglejte nekaj pogosto zahtevanih primerov poizvedb.

Spremenite vzorce poizvedb, da bodo delovali v ciljnih okoljih:

- {serviceRoot}:`https://api.ci.ai.dynamics.com/v1/instances/{instanceId}/data` kje{instanceId} je GUID okolja Customer Insights, po katerem želite poizvedovati. The [Operacija ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) vam omogoča, da najdete{InstanceId} imate dostop do.
- {CID}: GUID poenotenega zapisa stranke. Primer: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Identifikator primarnega ključa zapisa stranke v vir podatkov. Primer: `CNTID_1002`
- {DSname}: Niz z imenom entitete vir podatkov, ki se vnese v Customer Insights. Primer: `Website_contacts`.
- {SegmentName}: Niz z imenom izhodne entitete segmenta v Customer Insights. Primer: `Male_under_40`.

## <a name="customer"></a>stranka

Vzorčne poizvedbe za *Stranka* entiteta.

|Vrsta poizvedbe |Primer  | opomba,  |
|---------|---------|---------|
|ID posamezne stranke     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|nadomestni ključ    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Nadomestni ključi ostajajo v enotni entiteti stranke       |
|Izberi   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|v    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|nadomestni ključ + In   | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Poišči  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Vrne 10 najboljših rezultatov za iskalni niz      |
|Članstvo v segmentu  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Vrne prednastavljeno število vrstic iz entitete segmentacije.      |
|Članstvo v segmentu za stranko | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'&IsMemberOfSegment('{SegmentName}')`     | Vrne profil stranke, če je član danega segmenta     |

## <a name="unified-activity"></a>Enotna dejavnost

Vzorčne poizvedbe za *UnifiedActivity* entiteta.

|Vrsta poizvedbe |Primer  | opomba,  |
|---------|---------|---------|
|Dejavnost CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Navaja dejavnosti določenega profila stranke |
|Dejavnost časovni okvir    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Aktivnosti profila stranke v časovni okvir       |
|Vrsta dejavnosti    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Dejavnost avtorja prikazno ime     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Razvrščanje dejavnosti    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Razvrsti dejavnosti naraščajoče ali padajoče       |
|Dejavnost je razširjena s članstva v segmentu  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Drugi primeri

Vzorčne poizvedbe za druge entitete.

|Vrsta poizvedbe |Primer  | opomba,  |
|---------|---------|---------|
|Mere CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Obogatene blagovne znamke CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Obogateni interesi CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|In-Clause + Expand     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Nepodprte poizvedbe OData

Customer Insights ne podpira naslednjih poizvedb:

- `$filter` na zaužitih izvornih entitetah. Poizvedbe $filter lahko izvajate samo na sistemskih entitetah, ki jih ustvari Customer Insights.
- `$expand` od`$search` poizvedbo. Primer: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` od`$select` če je izbrana le podnabor atributov. Primer: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` obogatena blagovna znamka ali interesne afinitete za dano stranko. Primer: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Poizvedite predvidevanje izhodne entitete modela prek nadomestni ključ. Primer: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
