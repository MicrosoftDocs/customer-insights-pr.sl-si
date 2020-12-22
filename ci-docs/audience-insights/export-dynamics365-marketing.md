---
title: Izvozite podatke Customer Insights v Dynamics 365 Marketing
description: Naučite se konfigurirati povezavo s storitvijo Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643793"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="a4476-103">Povezovalnik za Dynamics 365 Marketing (predogled)</span><span class="sxs-lookup"><span data-stu-id="a4476-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a4476-104">S [segmenti](segments.md) ustvarite akcije in stopite v stik z določenimi skupinami strank s storitvijo Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="a4476-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="a4476-105">Za več informacij glejte razdelek [Uporaba segmentov iz storitve Dynamics 365 Customer Insights s storitvijo Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="a4476-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="a4476-106">Predpogoj</span><span class="sxs-lookup"><span data-stu-id="a4476-106">Prerequisite</span></span>

<span data-ttu-id="a4476-107">Zapisi stikov [iz storitve Dynamics 365 Marketing, uvoženi prek storitve Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="a4476-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="a4476-108">Konfiguracija povezovalnika za Marketing</span><span class="sxs-lookup"><span data-stu-id="a4476-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="a4476-109">Pri vpogledih v občinstvo izberite **Skrbnik** > **Cilji izvoza**.</span><span class="sxs-lookup"><span data-stu-id="a4476-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a4476-110">Pod možnostjo **Dynamics 365 Marketing** izberite **Nastavitev**.</span><span class="sxs-lookup"><span data-stu-id="a4476-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="a4476-111">Dajte svojemu cilju izvoza prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="a4476-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="a4476-112">Vnesite URL za Marketing vaše organizacije v polje **Naslov strežnika**.</span><span class="sxs-lookup"><span data-stu-id="a4476-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="a4476-113">V razdelku **Skrbniški račun strežnika** izberite **Vpis** in izberite račun Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="a4476-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="a4476-114">Polje za ID stranke preslikajte v ID stika za Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a4476-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="a4476-115">Izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="a4476-115">Select **Next**.</span></span>

1. <span data-ttu-id="a4476-116">Izberite enega ali več segmentov.</span><span class="sxs-lookup"><span data-stu-id="a4476-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="a4476-117">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="a4476-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a4476-118">Izvoz podatkov</span><span class="sxs-lookup"><span data-stu-id="a4476-118">Export the data</span></span>

<span data-ttu-id="a4476-119">Lahko [izvozite podatke na zahtevo](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a4476-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a4476-120">Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a4476-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
