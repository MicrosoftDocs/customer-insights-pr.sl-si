---
title: Izvozite podatke Customer Insights v Dynamics 365 Marketing
description: Naučite se konfigurirati povezavo s storitvijo Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597623"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="9294d-103">Povezovalnik za Dynamics 365 Marketing (predogled)</span><span class="sxs-lookup"><span data-stu-id="9294d-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="9294d-104">S [segmenti](segments.md) ustvarite akcije in stopite v stik z določenimi skupinami strank s storitvijo Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="9294d-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="9294d-105">Za več informacij glejte razdelek [Uporaba segmentov iz storitve Dynamics 365 Customer Insights s storitvijo Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="9294d-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="9294d-106">Predpogoj</span><span class="sxs-lookup"><span data-stu-id="9294d-106">Prerequisite</span></span>

- <span data-ttu-id="9294d-107">Zapisi o stikih morajo biti prisotni v storitvi Dynamics 365 Marketing, preden lahko izvozite segment iz rešitve Customer Insights v Marketing.</span><span class="sxs-lookup"><span data-stu-id="9294d-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="9294d-108">Preberite več o vključevanju stikov v storitvi [Dynamics 365 Marketing z uporabo rešitve Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="9294d-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="9294d-109">Z izvozom segmentov iz vpogledov v občinstvo v rešitev Marketing ne bodo ustvarjeni novi zapisi stikov v primerkih aplikacije Marketing.</span><span class="sxs-lookup"><span data-stu-id="9294d-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="9294d-110">Zapise o stikih iz rešitve Marketing je treba vključiti v vpoglede v občinstvo in jih uporabiti kot vir podatkov.</span><span class="sxs-lookup"><span data-stu-id="9294d-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="9294d-111">Prav tako jih je treba vključiti v enotno entiteto stranke, da se ID-ji strank preslikajo v ID-je stikov, preden je segmente mogoče izvoziti.</span><span class="sxs-lookup"><span data-stu-id="9294d-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="9294d-112">Konfiguracija povezovalnika za Marketing</span><span class="sxs-lookup"><span data-stu-id="9294d-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="9294d-113">Pri vpogledih v občinstvo izberite **Skrbnik** > **Cilji izvoza**.</span><span class="sxs-lookup"><span data-stu-id="9294d-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="9294d-114">Pod možnostjo **Dynamics 365 Marketing** izberite **Nastavitev**.</span><span class="sxs-lookup"><span data-stu-id="9294d-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="9294d-115">Dajte svojemu cilju izvoza prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="9294d-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="9294d-116">Vnesite URL za Marketing vaše organizacije v polje **Naslov strežnika**.</span><span class="sxs-lookup"><span data-stu-id="9294d-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="9294d-117">V razdelku **Skrbniški račun strežnika** izberite **Vpis** in izberite račun Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="9294d-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="9294d-118">Polje za ID stranke preslikajte v ID stika za Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="9294d-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="9294d-119">Izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="9294d-119">Select **Next**.</span></span>

1. <span data-ttu-id="9294d-120">Izberite enega ali več segmentov.</span><span class="sxs-lookup"><span data-stu-id="9294d-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="9294d-121">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="9294d-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="9294d-122">Izvoz podatkov</span><span class="sxs-lookup"><span data-stu-id="9294d-122">Export the data</span></span>

<span data-ttu-id="9294d-123">Lahko [izvozite podatke na zahtevo](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="9294d-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="9294d-124">Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9294d-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]