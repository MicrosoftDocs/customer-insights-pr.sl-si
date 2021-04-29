---
title: Obogatitev poenotenih profilov strank
description: Uporabite zmogljivosti za obogatitev podatkov o strankah.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896025"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="7d7fa-103">Obogatitev profilov strank (predogled)</span><span class="sxs-lookup"><span data-stu-id="7d7fa-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="7d7fa-104">Za obogatitev podatkov o strankah uporabite podatke iz virov, kot so Microsoft in drugi partnerji.</span><span class="sxs-lookup"><span data-stu-id="7d7fa-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stran zvezdišča za obogatitev":::

<span data-ttu-id="7d7fa-106">V razdelku vpogledov v občinstvo odprite **Podatki** > **Obogatitev** za delo z možnostmi obogatitve.</span><span class="sxs-lookup"><span data-stu-id="7d7fa-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="7d7fa-107">Za ustvarjanje ali urejanje obogatitev morate imeti dovoljenje »Sodelavec« ali »Skrbnik«.</span><span class="sxs-lookup"><span data-stu-id="7d7fa-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="7d7fa-108">Za več informacij glejte razdelek [Dovoljenja](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="7d7fa-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="7d7fa-109">Na zavihku **Odkrivanje** so na voljo te obogatitve:</span><span class="sxs-lookup"><span data-stu-id="7d7fa-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="7d7fa-110">[Znamke](enrichment-microsoft.md), ki jih zagotavlja Microsoft</span><span class="sxs-lookup"><span data-stu-id="7d7fa-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="7d7fa-111">[Zanimanja](enrichment-microsoft.md), ki jih zagotavlja Microsoft</span><span class="sxs-lookup"><span data-stu-id="7d7fa-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="7d7fa-112">[Podatki o podjetju](enrichment-leadspace.md), ki jih zagotavlja Leadspace</span><span class="sxs-lookup"><span data-stu-id="7d7fa-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="7d7fa-113">[Demografski podatki](enrichment-experian.md), ki jih zagotavlja Experian</span><span class="sxs-lookup"><span data-stu-id="7d7fa-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="7d7fa-114">[Podatki o lokaciji](enrichment-here.md), ki jih zagotavlja HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="7d7fa-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="7d7fa-115">[Podatki po meri](enrichment-SFTP-custom-import.md) s protokolom za varen prenos datotek (SFTP)</span><span class="sxs-lookup"><span data-stu-id="7d7fa-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="7d7fa-116">Na zavihku **Moje obogatitve** si lahko ogledate obogatitve, ki ste jih konfigurirali, in uredite njihove lastnosti.</span><span class="sxs-lookup"><span data-stu-id="7d7fa-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="7d7fa-117">Upravljanje obstoječih obogatitev</span><span class="sxs-lookup"><span data-stu-id="7d7fa-117">Manage existing enrichments</span></span>

<span data-ttu-id="7d7fa-118">Pojdite na razdelek **Moje obogatitve** za ogled vseh konfiguriranih obogatitev.</span><span class="sxs-lookup"><span data-stu-id="7d7fa-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="7d7fa-119">Vsaka obogatitev je predstavljena kot vrstica, ki vključuje dodatne informacije o obogatitvi.</span><span class="sxs-lookup"><span data-stu-id="7d7fa-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="7d7fa-120">Izberite obogatitev in si oglejte razpoložljive možnosti.</span><span class="sxs-lookup"><span data-stu-id="7d7fa-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="7d7fa-121">Za ogled možnosti lahko izberete tudi treh pik (...) na elementu seznama.</span><span class="sxs-lookup"><span data-stu-id="7d7fa-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Možnosti upravljanja obogatitev na seznamu obogatitev":::

- <span data-ttu-id="7d7fa-123">**Pogled** podrobnosti o obogatitvi s številom obogatenih profilov kupcev.</span><span class="sxs-lookup"><span data-stu-id="7d7fa-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="7d7fa-124">**Urejanje** konfiguracije obogatitve.</span><span class="sxs-lookup"><span data-stu-id="7d7fa-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="7d7fa-125">**Zaženite** obogatitev za posodobitev profilov strank z najnovejšimi podatki.</span><span class="sxs-lookup"><span data-stu-id="7d7fa-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="7d7fa-126">**Deaktiviranje** obstoječe obogatitve za preprečitev samodejnega osveževanja z vsako načrtovano osvežitvijo.</span><span class="sxs-lookup"><span data-stu-id="7d7fa-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="7d7fa-127">Podatki iz zadnje uspešne osvežitve bodo še naprej na voljo.</span><span class="sxs-lookup"><span data-stu-id="7d7fa-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="7d7fa-128">**Aktivacija** neaktivne obogatitve za ponovni zagon samodejnega osveževanja z vsako načrtovano osvežitvijo.</span><span class="sxs-lookup"><span data-stu-id="7d7fa-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="7d7fa-129">**Brisanje** obogatitve.</span><span class="sxs-lookup"><span data-stu-id="7d7fa-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="7d7fa-130">Več obogatitev lahko zaženete ali deaktivirate hkrati, tako da jih izberete na seznamu.</span><span class="sxs-lookup"><span data-stu-id="7d7fa-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="7d7fa-131">Možnosti pogleda in urejanja niso na voljo kot množično dejanje in delujejo le za eno obogatitev na enkrat.</span><span class="sxs-lookup"><span data-stu-id="7d7fa-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="7d7fa-132">Obogatitve in povezave</span><span class="sxs-lookup"><span data-stu-id="7d7fa-132">Enrichments and connections</span></span>

<span data-ttu-id="7d7fa-133">Obogatitve neodvisnih ponudnikov so konfigurirane z uporabo [povezav](connections.md), za katere skrbnik nastavi poverilnice in poda soglasje za prenose podatkov.</span><span class="sxs-lookup"><span data-stu-id="7d7fa-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="7d7fa-134">Za konfiguriranje obogatitev lahko povezavo uporabijo skrbniki in sodelavci.</span><span class="sxs-lookup"><span data-stu-id="7d7fa-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="7d7fa-135">Več obogatitev iste vrste</span><span class="sxs-lookup"><span data-stu-id="7d7fa-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="7d7fa-136">Entiteta, ki jo je treba obogatiti, je določena med konfiguriranjem obogatitve, ki omogoča obogatiti samo podmnožico vseh profilov.</span><span class="sxs-lookup"><span data-stu-id="7d7fa-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="7d7fa-137">Obogatite podatke na primer samo za določen segment.</span><span class="sxs-lookup"><span data-stu-id="7d7fa-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="7d7fa-138">Konfigurirate lahko več obogatitev iste vrste in znova uporabite isto povezavo.</span><span class="sxs-lookup"><span data-stu-id="7d7fa-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="7d7fa-139">Nekatere obogatitve imajo omejitev števila obogatitev iste vrste, ki jih je mogoče ustvariti.</span><span class="sxs-lookup"><span data-stu-id="7d7fa-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="7d7fa-140">Omejitve in trenutno uporabo si lahko ogledate na strani **Obogatitev**.</span><span class="sxs-lookup"><span data-stu-id="7d7fa-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
