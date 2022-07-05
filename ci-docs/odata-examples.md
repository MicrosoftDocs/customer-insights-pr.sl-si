---
title: Primeri poizvedb OData za API-je Customer Insights
description: Pogosto uporabljeni primeri za Open Data Protocol (OData) za poizvedbo v API-jih Customer Insights za pregled podatkov.
ms.date: 05/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54ba9f4e9baeb4b7021bb8c20a706bbb6eb1529f
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083173"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>Primeri poizvedb OData za API-je Customer Insights

Open Data Protocol (OData) je protokol za dostop do podatkov, zgrajen na osnovnih protokolih, kot je HTTP. Uporablja splošno sprejete metodologije, kot je REST za splet. Obstajajo različne vrste knjižnic in orodij, ki jih je mogoče uporabiti za uporabo storitev OData.

Ta članek navaja nekaj pogosto zahtevanih primerov poizvedb, ki vam bodo v pomoč pri gradnji lastnih izvedb na podlagi [API-ji Customer Insights](apis.md).

Vzorce poizvedb morate spremeniti, da bodo delovali v ciljnih okoljih: 

- {serviceRoot}:`https://api.ci.ai.dynamics.com/v1/instances/{instanceId}` kje{instanceId} je GUID okolja Customer Insights, po katerem želite poizvedovati. The [Operacija ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) vam omogoča, da najdete{InstanceId} imate dostop do.
- {CID}: GUID enotnega zapisa strank. Primer: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Identifikator primarnega ključa zapisa stranke v vir podatkov. Primer: `CNTID_1002`
- {DSname}: Niz z imenom entitete vir podatkov, ki se vnese v Customer Insights. Primer: `Website_contacts`.
- {SegmentName}: Niz z imenom izhodne entitete segmenta v Customer Insights. Primer: `Male_under_40`.

## <a name="customer"></a>stranka

Naslednja tabela vsebuje niz vzorčnih poizvedb za *Stranka* entiteta.

|Vrsta poizvedbe |Primer  | opomba,  |
|---------|---------|---------|
|ID posamezne stranke     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Nadomestni ključ    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Nadomestni ključi so še vedno v enotni enoti stranke       |
|Izberi   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|v    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Nadomestni ključ + In   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Poišči  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Vrne 10 najboljših rezultatov za iskalni niz      |
|Članstvo v segmentu  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Vrne prednastavljeno število vrstic iz entitete segmentacije.      |

## <a name="unified-activity"></a>Enotna dejavnost

Naslednja tabela vsebuje niz vzorčnih poizvedb za *UnifiedActivity* entiteta.

|Vrsta poizvedbe |Primer  | opomba,  |
|---------|---------|---------|
|Dejavnost CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Navaja dejavnosti določenega profila stranke |
|Dejavnost časovni okvir    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Dejavnosti profila stranke v časovni okvir       |
|Vrsta dejavnosti    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Dejavnost prikazno ime     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Razvrščanje dejavnosti    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Razvrstite dejavnosti naraščajoče ali padajoče       |
|Dejavnost se je razširila iz članstva v segmentu  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Drugi primeri

Naslednja tabela vsebuje niz vzorčnih poizvedb za druge entitete.

|Vrsta poizvedbe |Primer  | opomba,  |
|---------|---------|---------|
|Ukrepi CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Obogatene blagovne znamke CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Obogateni interesi CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|V stavku + razširitev     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Poizvedbe OData niso podprte

Customer Insights ne podpira naslednjih poizvedb:

- `$filter` na zaužitih izvornih entitetah. Poizvedbe $filter lahko izvajate samo na sistemskih entitetah, ki jih ustvari Customer Insights.
- `$expand` od`$search` poizvedba. Primer: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` od`$select` če je izbrana samo podmnožica atributov. Primer: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` obogatene blagovne znamke ali interesne afinitete za dano stranko. Primer: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Poizvedba o izhodnih entitetah modela predvidevanje prek nadomestni ključ. Primer: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
