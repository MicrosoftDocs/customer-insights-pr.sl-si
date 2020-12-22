---
title: Izvozite podatke Customer Insights v Dynamics 365 Sales
description: Naučite se konfigurirati povezavo s storitvijo Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643838"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="62117-103">Povezovalnik za Dynamics 365 Sales (predogled)</span><span class="sxs-lookup"><span data-stu-id="62117-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="62117-104">Na podlagi podatkov o strankah z aplikacijo Dynamics 365 Sales ustvarjajte sezname za trženje in postopke za nadaljnje delo ter pošiljajte promocijske vsebine.</span><span class="sxs-lookup"><span data-stu-id="62117-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="62117-105">Predpogoj</span><span class="sxs-lookup"><span data-stu-id="62117-105">Prerequisite</span></span>

<span data-ttu-id="62117-106">Zapisi stikov [iz storitve Dynamics 365 Sales, uvožene prek storitve Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="62117-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="62117-107">Konfiguracija povezovalnika za Sales</span><span class="sxs-lookup"><span data-stu-id="62117-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="62117-108">Pri vpogledih v občinstvo izberite **Skrbnik** > **Cilji izvoza**.</span><span class="sxs-lookup"><span data-stu-id="62117-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="62117-109">Pod možnostjo **Dynamics 365 Sales** izberite **Nastavitev**.</span><span class="sxs-lookup"><span data-stu-id="62117-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="62117-110">Dajte svojemu cilju izvoza prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="62117-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="62117-111">Vnesite URL za Sales vaše organizacije v polje **Naslov strežnika**.</span><span class="sxs-lookup"><span data-stu-id="62117-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="62117-112">V razdelku **Skrbniški račun strežnika** izberite **Vpis** in izberite račun Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="62117-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="62117-113">Polje za ID stranke preslikajte v ID stika za Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="62117-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="62117-114">Izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="62117-114">Select **Next**.</span></span>

1. <span data-ttu-id="62117-115">Izberite enega ali več segmentov.</span><span class="sxs-lookup"><span data-stu-id="62117-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="62117-116">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="62117-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="62117-117">Izvoz podatkov</span><span class="sxs-lookup"><span data-stu-id="62117-117">Export the data</span></span>

<span data-ttu-id="62117-118">Lahko [izvozite podatke na zahtevo](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="62117-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="62117-119">Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="62117-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
