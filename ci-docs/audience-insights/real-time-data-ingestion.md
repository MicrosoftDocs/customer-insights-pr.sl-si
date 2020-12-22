---
title: Vnos in omejitve podatkov v realnem času
description: Splošne informacije o zmožnostih v realnem času pri vpogledih v občinstvo.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00a72e6a67e33c8e70ccc6139c5e62020f9d3e1
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689195"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="ec387-103">Uvoz podatkov v realnem času (predogled)</span><span class="sxs-lookup"><span data-stu-id="ec387-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="ec387-104">Funkcije v skoraj realnem času vam omogočajo, da si v nekaj sekundah ogledate najnovejše interakcije, ki so jih vaše stranke opravile z vašimi izdelki in storitvami.</span><span class="sxs-lookup"><span data-stu-id="ec387-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="ec387-105">[Načrtovane osvežitve](system.md#schedule-tab) vključujejo veliko število zapisov in več zapletenih postopkov.</span><span class="sxs-lookup"><span data-stu-id="ec387-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="ec387-106">Najprej se podatki izvlečejo iz vira podatkov.</span><span class="sxs-lookup"><span data-stu-id="ec387-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="ec387-107">Nato se podatki poenotijo in obogatijo z dodatnimi informacijami.</span><span class="sxs-lookup"><span data-stu-id="ec387-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="ec387-108">Vsak posamezen postopek lahko traja od nekaj minut do nekaj ur.</span><span class="sxs-lookup"><span data-stu-id="ec387-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="ec387-109">Funkcija v realnem času zagotavlja podatke takoj za porabo, dokler naslednje načrtovano osveževanje ne izvleče teh podatkov iz vira podatkov.</span><span class="sxs-lookup"><span data-stu-id="ec387-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="ec387-110">Posodobitve v realnem času imajo čas poteka, po katerem ne preglasijo vrednosti iz vira podatkov:</span><span class="sxs-lookup"><span data-stu-id="ec387-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="ec387-111">Posodobitve profilov bodo shranjene 4 ure</span><span class="sxs-lookup"><span data-stu-id="ec387-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="ec387-112">Dejavnosti bodo shranjene 30 dni</span><span class="sxs-lookup"><span data-stu-id="ec387-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="ec387-113">Te vrednosti so parametri klicev API-jev, ki jih lahko spremenite.</span><span class="sxs-lookup"><span data-stu-id="ec387-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="ec387-114">Njihov cilj je zagotoviti, da vaši izvorni podatki ostanejo vaš vir resnice.</span><span class="sxs-lookup"><span data-stu-id="ec387-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="ec387-115">Če želite, da so posodobitve v realnem času vključene dlje časa, jih morate dodati v vir podatkov, da bodo vzete med naslednjo načrtovano osvežitvijo.</span><span class="sxs-lookup"><span data-stu-id="ec387-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="ec387-116">Posodobitev polj poenotenih profilov strank v realnem času</span><span class="sxs-lookup"><span data-stu-id="ec387-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="ec387-117">Posodobljeni profili se bodo v nekaj sekundah prikazali v pogledu kartice stranke ali kateri koli drugi vizualizaciji.</span><span class="sxs-lookup"><span data-stu-id="ec387-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="ec387-118">Ker postopki v realnem času potekajo po poenotenju podatkov, veljajo le za poenotene profile strank.</span><span class="sxs-lookup"><span data-stu-id="ec387-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="ec387-119">Posledično se spremembami profilov v realnem času ne bodo posodobile mere, članstva v segmentu ali obogatitve.</span><span class="sxs-lookup"><span data-stu-id="ec387-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="ec387-120">Omejitve</span><span class="sxs-lookup"><span data-stu-id="ec387-120">Limitations</span></span>

- <span data-ttu-id="ec387-121">Profile strank lahko posodabljate, vendar jih ne morete ustvariti ali izbrisati.</span><span class="sxs-lookup"><span data-stu-id="ec387-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="ec387-122">Izvažanje posodobitev v realnem času v zunanje sisteme, kot je Power BI, trenutno ni na voljo.</span><span class="sxs-lookup"><span data-stu-id="ec387-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="ec387-123">Ustvarjanje dejavnosti v realnem času</span><span class="sxs-lookup"><span data-stu-id="ec387-123">Real-time creation of activities</span></span>

<span data-ttu-id="ec387-124">API v realnem času vam omogoča objavo nove dejavnosti iz vašega izvornega sistema (posamezen izvorni zapis) v poenotenem profilu stranke.</span><span class="sxs-lookup"><span data-stu-id="ec387-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="ec387-125">Nova dejavnost bo v nekaj sekundah na voljo kot poenotena dejavnost na časovnici poenotenega profila stranke.</span><span class="sxs-lookup"><span data-stu-id="ec387-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="ec387-126">Časovnico lahko vidite v pogledu kartice stranke ali kateri koli drugi integraciji časovne osi, ki ste jo konfigurirali.</span><span class="sxs-lookup"><span data-stu-id="ec387-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="ec387-127">Dejavnosti so nespremenljive.</span><span class="sxs-lookup"><span data-stu-id="ec387-127">Activities are immutable.</span></span> <span data-ttu-id="ec387-128">Ko so ustvarjene, se ne spremenijo.</span><span class="sxs-lookup"><span data-stu-id="ec387-128">They don't change once created.</span></span>
> - <span data-ttu-id="ec387-129">Trenutno segmenti in mere ne bodo posodobljeni glede na novo dejavnost.</span><span class="sxs-lookup"><span data-stu-id="ec387-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="ec387-130">Dejavnosti, dodane samo prek API-ja v realnem času, se ne izvozijo in ne bodo prikazane v storitvi PowerBI.</span><span class="sxs-lookup"><span data-stu-id="ec387-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="ec387-131">Obstajata dva načina za povezavo z API-jem v realnem času:</span><span class="sxs-lookup"><span data-stu-id="ec387-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="ec387-132">[posredni](#connect-via-the-dynamics-365-customer-insights-connector), pri čemer se uporabi [povezovalnik storitve Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="ec387-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span></span>
- <span data-ttu-id="ec387-133">[neposredni](#connect-directly-to-the-real-time-api), pri čemer se uporabi koda</span><span class="sxs-lookup"><span data-stu-id="ec387-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="ec387-134">Za oba načina veljajo naslednje zahteve:</span><span class="sxs-lookup"><span data-stu-id="ec387-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="ec387-135">Okolje Customer Insights</span><span class="sxs-lookup"><span data-stu-id="ec387-135">A Customer Insights environment</span></span>
- <span data-ttu-id="ec387-136">Poenoteni profili strank</span><span class="sxs-lookup"><span data-stu-id="ec387-136">Unified customer profiles</span></span>
- <span data-ttu-id="ec387-137">Konfigurirane in izvedene dejavnosti</span><span class="sxs-lookup"><span data-stu-id="ec387-137">Activities configured and run</span></span>
- <span data-ttu-id="ec387-138">Dovoljenja sodelavcev in skrbnikov za preverjanje pristnosti vašega računa</span><span class="sxs-lookup"><span data-stu-id="ec387-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="ec387-139">Povezovanje prek povezovalnika storitve Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="ec387-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="ec387-140">API v realnem času lahko uvozi podatke iz namenskega povezovalnika Power Platform, [povezovalnika storitve Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/), brez potrebe po pisanju in uvajanju kakršne koli kode.</span><span class="sxs-lookup"><span data-stu-id="ec387-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="ec387-141">Povezovalnik lahko izvaja enaka dejanja v realnem času kot API.</span><span class="sxs-lookup"><span data-stu-id="ec387-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="ec387-142">Za izboljšane povezovalnika potrebujete veljavno licenco.</span><span class="sxs-lookup"><span data-stu-id="ec387-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="ec387-143">Za več informacij glejte razdelek [Pogosta vprašanja o licenciranju za Power Apps in Power Automate](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="ec387-143">For more information, see [Power Apps and Power Automate licensing FAQs](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="ec387-144">Power Platform [Power Apps in/ali Power Automate](https://docs.microsoft.com/connectors/)</span><span class="sxs-lookup"><span data-stu-id="ec387-144">Power Platform [Power Apps and/or Power Automate](https://docs.microsoft.com/connectors/)</span></span>
- <span data-ttu-id="ec387-145">[Logične aplikacije storitve](https://docs.microsoft.com/azure/connectors/apis-list) Azure</span><span class="sxs-lookup"><span data-stu-id="ec387-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span></span>

<span data-ttu-id="ec387-146">Za podrobnosti o ustvarjanju tokov glejte [dokumentacijo za Power Automate](https://docs.microsoft.com/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="ec387-146">For details about creating flows, see the [Power Automate documentation](https://docs.microsoft.com/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="ec387-147">Povezovanje neposredno z API-jem v realnem času</span><span class="sxs-lookup"><span data-stu-id="ec387-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="ec387-148">Zmožnosti v realnem času lahko uporabite tako, da sestavite svoj prodajni lijak in se neposredno povežete z API-jem v realnem času.</span><span class="sxs-lookup"><span data-stu-id="ec387-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="ec387-149">Dejavnost lahko objavite v obliki svojega izvornega sistema ali v obliki zapisa UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="ec387-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="ec387-150">Obliko zapisa lahko pridobite tako, da z API-jem pokličete /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="ec387-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="ec387-151">Podrobnosti tega API-ja, vključno s parametri in odzivi, najdete v razdelku **EntityData** pri [sklicu za API-je za Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="ec387-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="ec387-152">Če želite več informacij, glejte razdelek [Delo z API-ji za Customer Insights](apis.md).</span><span class="sxs-lookup"><span data-stu-id="ec387-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="ec387-153">Razumevanje uporabe v realnem času s telemetrijo</span><span class="sxs-lookup"><span data-stu-id="ec387-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="ec387-154">Pridobite pregled obsega zahtev za API v realnem času in informacije o težavah, s katerimi se sistem lahko srečuje.</span><span class="sxs-lookup"><span data-stu-id="ec387-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="ec387-155">[Dostopate lahko do telemetrije v realnem času](system.md#api-usage-tab) tako, da se pomaknete v razdelek **Skrbnik** > **Sistem** > **Uporaba API-ja**.</span><span class="sxs-lookup"><span data-stu-id="ec387-155">You can [access the real-time telemetry](system.md#api-usage-tab) by going to **Admin** > **System** > **API usage**.</span></span> <span data-ttu-id="ec387-156">V tabeli **Postopki** vrstice za postopke API, ki uporabljajo metode v realnem času, vsebujejo gumb za ogled uporabe API-ja v realnem času.</span><span class="sxs-lookup"><span data-stu-id="ec387-156">In the **Operations** table, rows for API operations which use the real-time methods contain a button to view real-time API usage.</span></span> <span data-ttu-id="ec387-157">Gumb je vizualiziran s simbolom daljnogleda.</span><span class="sxs-lookup"><span data-stu-id="ec387-157">The button is visualized with a binocular symbol.</span></span> <span data-ttu-id="ec387-158">Izberite gumb, da odprete stransko podokno s podrobnostmi o uporabi za sprotno uporabo API-ja v trenutnem okolju.</span><span class="sxs-lookup"><span data-stu-id="ec387-158">Select the button to open a side pane containing usage details for the real-time API usage in the current environment.</span></span>

<span data-ttu-id="ec387-159">Uporabite izbirnik **Združi po**, da izberete, kako najbolje predstaviti interakcije v realnem času na časovnici z obsegom od zadnjih 24 ur do zadnjih 30 dni.</span><span class="sxs-lookup"><span data-stu-id="ec387-159">Use the **Group by** selector to choose how to best present your real-time interactions on a timeline ranging from the last 24 hours to the last 30 days.</span></span> <span data-ttu-id="ec387-160">Podatke lahko združite po metodi API-ja, določenem imenu entitete (uvožena entiteta), avtorju ustvarjanja (vir dogodka), rezultatu (uspeh ali neuspeh) ali kodah napak.</span><span class="sxs-lookup"><span data-stu-id="ec387-160">You can group the data by API method, entity qualified name (ingested entity), created by (source of the event), result (success or failure) or error codes.</span></span> <span data-ttu-id="ec387-161">Podatki so na voljo kot grafikon zgodovine in kot tabela.</span><span class="sxs-lookup"><span data-stu-id="ec387-161">The data is available as a history chart and as a table.</span></span>