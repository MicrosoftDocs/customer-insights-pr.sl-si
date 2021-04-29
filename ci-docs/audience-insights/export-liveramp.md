---
title: 'Povezovalnik LiveRamp '
description: Naučite se, kako konfigurirati povezavo in izvažati v LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760347"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="b54a6-103">Izvoz segmentov v LiveRamp&reg; (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="b54a6-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="b54a6-104">Vklopite svoje podatke na platformi LiveRamp za povezovanje z več kot 500 platformami v digitalni, družbeni in televizijski sferi.</span><span class="sxs-lookup"><span data-stu-id="b54a6-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="b54a6-105">Delajte s podatki v rešitvi LiveRamp, da ciljate, ukinete in prilagodite oglaševalske akcije.</span><span class="sxs-lookup"><span data-stu-id="b54a6-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="b54a6-106">Predpogoji za povezavo</span><span class="sxs-lookup"><span data-stu-id="b54a6-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="b54a6-107">Za uporabo tega povezovalnika potrebujete naročnino za LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="b54a6-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="b54a6-108">Če želite pridobiti naročnino, neposredno [kontaktirajte LiveRamp](https://liveramp.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="b54a6-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="b54a6-109">[Preberite več o LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="b54a6-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="b54a6-110">Nastavitev povezave s storitvijo LiveRamp</span><span class="sxs-lookup"><span data-stu-id="b54a6-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="b54a6-111">Odprite razdelek **Skrbnik** > **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="b54a6-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b54a6-112">Izberite **Dodajanje povezave** in izberite **LiveRamp** za konfiguracijo povezave.</span><span class="sxs-lookup"><span data-stu-id="b54a6-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="b54a6-113">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="b54a6-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b54a6-114">Ime in vrsta povezave opisujeta to povezavo.</span><span class="sxs-lookup"><span data-stu-id="b54a6-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b54a6-115">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="b54a6-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b54a6-116">Izberite, kdo lahko uporablja to povezavo.</span><span class="sxs-lookup"><span data-stu-id="b54a6-116">Choose who can use this connection.</span></span> <span data-ttu-id="b54a6-117">Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki.</span><span class="sxs-lookup"><span data-stu-id="b54a6-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b54a6-118">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b54a6-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b54a6-119">Navedite **Uporabniško ime** in **Geslo** za svoj račun LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="b54a6-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="b54a6-120">Te poverilnice se lahko razlikujejo od vaših poverilnic za LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="b54a6-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="b54a6-121">Izberite **Preveri**, da preskusite povezavo z LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="b54a6-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="b54a6-122">Po uspešnem preverjanju podajte soglasje za **Zasebnost podatkov in skladnost**, tako da izberete potrditveno polje **Strinjam se**.</span><span class="sxs-lookup"><span data-stu-id="b54a6-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="b54a6-123">Izberite možnost **Shrani**, da dokončate povezavo.</span><span class="sxs-lookup"><span data-stu-id="b54a6-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="b54a6-124">Konfiguriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="b54a6-124">Configure an export</span></span>

<span data-ttu-id="b54a6-125">Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave.</span><span class="sxs-lookup"><span data-stu-id="b54a6-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b54a6-126">Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b54a6-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b54a6-127">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="b54a6-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b54a6-128">Za ustvarjanje novega izvoza izberite **Dodaj cilj**.</span><span class="sxs-lookup"><span data-stu-id="b54a6-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b54a6-129">V polju **Povezava za izvoz** izberite povezavo v razdelku LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="b54a6-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="b54a6-130">Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.</span><span class="sxs-lookup"><span data-stu-id="b54a6-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b54a6-131">V polju **Izbira identifikatorja ključa** izberite **E-pošta**, **Ime in naslov** ali **Telefon** za pošiljanje v LiveRamp za reševanje identitete.</span><span class="sxs-lookup"><span data-stu-id="b54a6-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b54a6-132">![Povezovalnik LiveRamp s preslikavo atributov](media/export-liveramp-segments.png "Povezovalnik LiveRamp s preslikavo atributov")</span><span class="sxs-lookup"><span data-stu-id="b54a6-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="b54a6-133">Preslikajte pripadajoče atribute iz poenotene entitete stranke za izbrani identifikator ključa.</span><span class="sxs-lookup"><span data-stu-id="b54a6-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="b54a6-134">Izberite **Dodajanje atributa** za preslikavo več atributov za pošiljanje v LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="b54a6-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="b54a6-135">Če v LiveRamp pošljete več atributov identifikatorja ključa, boste verjetno dobili višjo stopnjo ujemanja.</span><span class="sxs-lookup"><span data-stu-id="b54a6-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="b54a6-136">Izberite segmente, ki jih želite izvoziti v LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="b54a6-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="b54a6-137">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="b54a6-137">Select **Save**.</span></span>

<span data-ttu-id="b54a6-138">S shranjevanjem izvoza se ta ne zažene takoj.</span><span class="sxs-lookup"><span data-stu-id="b54a6-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b54a6-139">Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b54a6-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b54a6-140">Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b54a6-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b54a6-141">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="b54a6-141">Data privacy and compliance</span></span>

<span data-ttu-id="b54a6-142">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Liveramp, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="b54a6-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b54a6-143">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Liveramp izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="b54a6-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b54a6-144">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b54a6-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b54a6-145">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="b54a6-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
