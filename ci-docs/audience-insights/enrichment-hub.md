---
title: Obogatitev poenotenih profilov strank
description: Uporabite zmogljivosti za obogatitev podatkov o strankah.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667114"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="d72d1-103">Obogatitev profilov strank (predogled)</span><span class="sxs-lookup"><span data-stu-id="d72d1-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="d72d1-104">Za obogatitev podatkov o strankah uporabite podatke iz virov, kot so Microsoft in drugi partnerji.</span><span class="sxs-lookup"><span data-stu-id="d72d1-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stran zvezdišča za obogatitev":::

<span data-ttu-id="d72d1-106">V razdelku vpogledov v občinstvo odprite **Podatki** > **Obogatitev** za delo z možnostmi obogatitve.</span><span class="sxs-lookup"><span data-stu-id="d72d1-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="d72d1-107">Za ustvarjanje ali urejanje obogatitev morate imeti dovoljenje »Sodelavec« ali »Skrbnik«.</span><span class="sxs-lookup"><span data-stu-id="d72d1-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="d72d1-108">Za več informacij glejte razdelek [Dovoljenja](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="d72d1-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="d72d1-109">Na zavihku **Odkrivanje** so na voljo te obogatitve:</span><span class="sxs-lookup"><span data-stu-id="d72d1-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="d72d1-110">[Blagovne znamke](enrichment-microsoft-graph.md) zagotavlja Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="d72d1-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="d72d1-111">[Zanimanja](enrichment-microsoft-graph.md) zagotavlja Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="d72d1-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="d72d1-112">[Podatki o podjetju](enrichment-leadspace.md), ki jih zagotavlja Leadspace</span><span class="sxs-lookup"><span data-stu-id="d72d1-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="d72d1-113">[Demografski podatki](enrichment-experian.md), ki jih zagotavlja Experian</span><span class="sxs-lookup"><span data-stu-id="d72d1-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="d72d1-114">[Podatki o lokaciji](enrichment-here.md), ki jih zagotavlja HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="d72d1-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="d72d1-115">[Podatki po meri](enrichment-SFTP-custom-import.md) s protokolom za varen prenos datotek (SFTP)</span><span class="sxs-lookup"><span data-stu-id="d72d1-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="d72d1-116">Na zavihku **Moje obogatitve** si lahko ogledate obogatitve, ki ste jih konfigurirali, in uredite njihove lastnosti.</span><span class="sxs-lookup"><span data-stu-id="d72d1-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="d72d1-117">Upravljanje obstoječih obogatitev</span><span class="sxs-lookup"><span data-stu-id="d72d1-117">Manage existing enrichments</span></span>

<span data-ttu-id="d72d1-118">Pojdite na razdelek **Moje obogatitve** za ogled vseh konfiguriranih obogatitev.</span><span class="sxs-lookup"><span data-stu-id="d72d1-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="d72d1-119">Vsaka obogatitev je predstavljena kot vrstica, ki vključuje dodatne informacije o obogatitvi.</span><span class="sxs-lookup"><span data-stu-id="d72d1-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="d72d1-120">Izberite obogatitev in si oglejte razpoložljive možnosti.</span><span class="sxs-lookup"><span data-stu-id="d72d1-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="d72d1-121">Lahko pa izberete elipso (...) na elementu s seznama in si tako ogledate možnosti.</span><span class="sxs-lookup"><span data-stu-id="d72d1-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Možnosti upravljanja obogatitev na seznamu obogatitev":::

- <span data-ttu-id="d72d1-123">**Pogled** podrobnosti o obogatitvi s številom obogatenih profilov kupcev.</span><span class="sxs-lookup"><span data-stu-id="d72d1-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="d72d1-124">**Urejanje** konfiguracije obogatitve.</span><span class="sxs-lookup"><span data-stu-id="d72d1-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="d72d1-125">**Zaženite** obogatitev za posodobitev profilov strank z najnovejšimi podatki.</span><span class="sxs-lookup"><span data-stu-id="d72d1-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="d72d1-126">**Deaktiviranje** obstoječe obogatitve za preprečitev samodejnega osveževanja z vsako načrtovano osvežitvijo.</span><span class="sxs-lookup"><span data-stu-id="d72d1-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="d72d1-127">Podatki iz zadnje uspešne osvežitve bodo še naprej na voljo.</span><span class="sxs-lookup"><span data-stu-id="d72d1-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="d72d1-128">**Aktivacija** neaktivne obogatitve za ponovni zagon samodejnega osveževanja z vsako načrtovano osvežitvijo.</span><span class="sxs-lookup"><span data-stu-id="d72d1-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="d72d1-129">**Brisanje** obogatitve.</span><span class="sxs-lookup"><span data-stu-id="d72d1-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="d72d1-130">Več obogatitev lahko zaženete ali deaktivirate hkrati, tako da jih izberete na seznamu.</span><span class="sxs-lookup"><span data-stu-id="d72d1-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="d72d1-131">Možnosti pogleda in urejanja niso na voljo kot množično dejanje in delujejo le za eno obogatitev na enkrat.</span><span class="sxs-lookup"><span data-stu-id="d72d1-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>