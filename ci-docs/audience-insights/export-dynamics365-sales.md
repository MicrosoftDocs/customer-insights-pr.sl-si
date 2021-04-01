---
title: Izvozite podatke Customer Insights v Dynamics 365 Sales
description: Naučite se konfigurirati povezavo s storitvijo Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598129"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="0b043-103">Povezovalnik za Dynamics 365 Sales (predogled)</span><span class="sxs-lookup"><span data-stu-id="0b043-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="0b043-104">Na podlagi podatkov o strankah z aplikacijo Dynamics 365 Sales ustvarjajte sezname za trženje in postopke za nadaljnje delo ter pošiljajte promocijske vsebine.</span><span class="sxs-lookup"><span data-stu-id="0b043-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="0b043-105">Predpogoj</span><span class="sxs-lookup"><span data-stu-id="0b043-105">Prerequisite</span></span>

1. <span data-ttu-id="0b043-106">Zapisi o stikih morajo biti prisotni v storitvi Dynamics 365 Sales, preden lahko izvozite segment iz rešitve Customer Insights v Sales.</span><span class="sxs-lookup"><span data-stu-id="0b043-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="0b043-107">Preberite več o vključevanju stikov v storitvi [Dynamics 365 Sales z uporabo rešitve Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="0b043-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="0b043-108">Z izvozom segmentov iz vpogledov v občinstvo v rešitev Sales ne bodo ustvarjeni novi zapisi stikov v primerkih aplikacije Sales.</span><span class="sxs-lookup"><span data-stu-id="0b043-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="0b043-109">Zapise o stikih iz rešitve Sales je treba vključiti v vpoglede v občinstvo in jih uporabiti kot vir podatkov.</span><span class="sxs-lookup"><span data-stu-id="0b043-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="0b043-110">Prav tako jih je treba vključiti v enotno entiteto stranke, da se ID-ji strank preslikajo v ID-je stikov, preden je segmente mogoče izvoziti.</span><span class="sxs-lookup"><span data-stu-id="0b043-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="0b043-111">Konfiguracija povezovalnika za Sales</span><span class="sxs-lookup"><span data-stu-id="0b043-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="0b043-112">Pri vpogledih v občinstvo izberite **Skrbnik** > **Cilji izvoza**.</span><span class="sxs-lookup"><span data-stu-id="0b043-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0b043-113">Pod možnostjo **Dynamics 365 Sales** izberite **Nastavitev**.</span><span class="sxs-lookup"><span data-stu-id="0b043-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="0b043-114">Dajte svojemu cilju izvoza prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="0b043-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="0b043-115">Vnesite URL za Sales vaše organizacije v polje **Naslov strežnika**.</span><span class="sxs-lookup"><span data-stu-id="0b043-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="0b043-116">V razdelku **Skrbniški račun strežnika** izberite **Vpis** in izberite račun Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="0b043-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="0b043-117">Polje za ID stranke preslikajte v ID stika za Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="0b043-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="0b043-118">Izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="0b043-118">Select **Next**.</span></span>

1. <span data-ttu-id="0b043-119">Izberite enega ali več segmentov.</span><span class="sxs-lookup"><span data-stu-id="0b043-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="0b043-120">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="0b043-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="0b043-121">Izvoz podatkov</span><span class="sxs-lookup"><span data-stu-id="0b043-121">Export the data</span></span>

<span data-ttu-id="0b043-122">Lahko [izvozite podatke na zahtevo](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="0b043-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="0b043-123">Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0b043-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]