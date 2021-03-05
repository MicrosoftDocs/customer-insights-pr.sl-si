---
title: Bot za Microsoft Teams
description: Poiščite poenotene profile strank v storitvi Microsoft Teams s pomočjo bota.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 03299610fd41a7e142e3c9723fad56ce7f90e083
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267972"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="1cbbb-103">Bot Teams za Dynamics 365 Customer Insights (predogled)</span><span class="sxs-lookup"><span data-stu-id="1cbbb-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="1cbbb-104">Povežite se s storitvijo Microsoft Teams, da bot dovoli iskanje poenotenih profilov strank v kanalih Teams.</span><span class="sxs-lookup"><span data-stu-id="1cbbb-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1cbbb-105">![Bot za Teams, ki prikazuje zapis stranke](media/teams-bot.png "Bot za Teams, ki prikazuje zapis stranke")</span><span class="sxs-lookup"><span data-stu-id="1cbbb-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1cbbb-106">Zahteve</span><span class="sxs-lookup"><span data-stu-id="1cbbb-106">Prerequisites</span></span>

<span data-ttu-id="1cbbb-107">Za nastavitev in konfiguracijo bota morajo biti izpolnjeni ti pogoji:</span><span class="sxs-lookup"><span data-stu-id="1cbbb-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="1cbbb-108">Dodan je najmanj en [vir podatkov](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="1cbbb-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="1cbbb-109">[Postopek poenotenja](data-unification.md) je dokončan.</span><span class="sxs-lookup"><span data-stu-id="1cbbb-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="1cbbb-110">Polja so dodana v [kazalo za iskanje in filtriranje](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="1cbbb-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="1cbbb-111">Aplikaciji Customer Insights in Teams sta v isti organizaciji.</span><span class="sxs-lookup"><span data-stu-id="1cbbb-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="1cbbb-112">Konfiguracija bota</span><span class="sxs-lookup"><span data-stu-id="1cbbb-112">Configure the bot</span></span>

1. <span data-ttu-id="1cbbb-113">Pri vpogledih v občinstvo izberite **Skrbnik** > **Cilji za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="1cbbb-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="1cbbb-114">Na ploščici Microsoft Teams izberite **Nastavitev**.</span><span class="sxs-lookup"><span data-stu-id="1cbbb-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="1cbbb-115">Preusmerjeni ste v območje **Aplikacije** v aplikaciji Teams.</span><span class="sxs-lookup"><span data-stu-id="1cbbb-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="1cbbb-116">Lahko tudi odprete aplikacijo Teams in izberete **Aplikacije** v spodnjem levem kotu oz. [jo prenesete neposredno iz trgovine AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).</span><span class="sxs-lookup"><span data-stu-id="1cbbb-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="1cbbb-117">Poiščite **Customer Insights** in izberite aplikacijo.</span><span class="sxs-lookup"><span data-stu-id="1cbbb-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="1cbbb-118">Izberite **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="1cbbb-118">Select **Add**.</span></span>
1. <span data-ttu-id="1cbbb-119">Ko se vpišete v Customer Insights v aplikaciji Teams, vidite pozdravno sporočilo in lahko začnete.</span><span class="sxs-lookup"><span data-stu-id="1cbbb-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="1cbbb-120">Stvari, ki jih omogoča bot</span><span class="sxs-lookup"><span data-stu-id="1cbbb-120">Things you can do with the bot</span></span>

<span data-ttu-id="1cbbb-121">Bot ponuja možnosti iskanja za poenotene profile strank.</span><span class="sxs-lookup"><span data-stu-id="1cbbb-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="1cbbb-122">Vnesite **iskanje** in nato ime, e-poštni naslov ali katero koli drugo polje v poenotenem profilu stranke, ki je dodano kazalu za iskanje in filtriranje.</span><span class="sxs-lookup"><span data-stu-id="1cbbb-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="1cbbb-123">Prikaže se kartica z največ 15 polji iz pridobljenega profila stranke.</span><span class="sxs-lookup"><span data-stu-id="1cbbb-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="1cbbb-124">Več ujemanj vrne seznam rezultatov, kjer lahko izberete profil.</span><span class="sxs-lookup"><span data-stu-id="1cbbb-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="1cbbb-125">Iskalni izraz lahko dodate v dvojne narekovaje, da poiščete natančno ujemanje.</span><span class="sxs-lookup"><span data-stu-id="1cbbb-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="1cbbb-126">Če vaša organizacija ohranja več okolij Customer Insights v isti organizaciji, lahko vnesete **switchinstance**, da izberete, v katero okolje želite povezati bot.</span><span class="sxs-lookup"><span data-stu-id="1cbbb-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="1cbbb-127">Če si želite ogledati seznam ukazov, ki so na voljo za bot, vnesite **pomoč**.</span><span class="sxs-lookup"><span data-stu-id="1cbbb-127">Enter **help** to see a list of available commands for the bot.</span></span>  


[!INCLUDE[footer-include](../includes/footer-banner.md)]