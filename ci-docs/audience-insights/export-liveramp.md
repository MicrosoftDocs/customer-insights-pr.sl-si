---
title: 'Povezovalnik LiveRamp '
description: Naučite se izvoziti podatke v rešitev LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 86aa8c66a47ee61741082c95f05d2e5ce3f06f35
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667204"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="ef12e-103">Povezovalnik za LiveRamp&reg; (predogled)</span><span class="sxs-lookup"><span data-stu-id="ef12e-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="ef12e-104">Aktivirajte svoje podatke v rešitvi LiveRamp, da povežete več kot 500 platform po digitalnih, družabnih in televizijskih ekosistemih.</span><span class="sxs-lookup"><span data-stu-id="ef12e-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="ef12e-105">Delajte s podatki v rešitvi LiveRamp, da ciljate, ukinete in prilagodite oglaševalske akcije.</span><span class="sxs-lookup"><span data-stu-id="ef12e-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ef12e-106">Zahteve</span><span class="sxs-lookup"><span data-stu-id="ef12e-106">Prerequisites</span></span>

- <span data-ttu-id="ef12e-107">Za uporabo tega povezovalnika potrebujete naročnino za LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="ef12e-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="ef12e-108">Če želite pridobiti naročnino, neposredno [kontaktirajte LiveRamp](https://liveramp.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="ef12e-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="ef12e-109">[Preberite več o LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="ef12e-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="ef12e-110">Povezovanje v LiveRamp</span><span class="sxs-lookup"><span data-stu-id="ef12e-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="ef12e-111">Pri vpogledih v občinstvo izberite **Skrbnik** > **Cilji izvoza**.</span><span class="sxs-lookup"><span data-stu-id="ef12e-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ef12e-112">Pri ploščici **LiveRamp** izberite **Nastavi**.</span><span class="sxs-lookup"><span data-stu-id="ef12e-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="ef12e-113">Dajte svojemu cilju prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="ef12e-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="ef12e-114">Navedite **Uporabniško ime** in **Geslo** za svoj račun LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="ef12e-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="ef12e-115">Te poverilnice se lahko razlikujejo od vaših poverilnic za LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="ef12e-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="ef12e-116">Izberite **Preveri**, da preskusite povezavo z LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="ef12e-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="ef12e-117">Po uspešnem preverjanju podajte soglasje za **Zasebnost podatkov in skladnost**, tako da izberete potrditveno polje **Strinjam se**.</span><span class="sxs-lookup"><span data-stu-id="ef12e-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="ef12e-118">Izberite **Naprej**, da nastavite povezovalnik LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="ef12e-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="ef12e-119">Konfiguracija povezovalnika</span><span class="sxs-lookup"><span data-stu-id="ef12e-119">Configure the connector</span></span>

1. <span data-ttu-id="ef12e-120">V polju **Izbira identifikatorja ključa** izberite **E-pošta**, **Ime in naslov** ali **Telefon** za pošiljanje v LiveRamp za reševanje identitete.</span><span class="sxs-lookup"><span data-stu-id="ef12e-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="ef12e-121">Preslikajte pripadajoče atribute iz poenotene entitete stranke za izbrani identifikator ključa.</span><span class="sxs-lookup"><span data-stu-id="ef12e-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="ef12e-122">Izberite **Dodaj atribut**, da preslikate dodatne atribute za pošiljanje v LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="ef12e-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="ef12e-123">Če v LiveRamp pošljete več atributov identifikatorja ključa, boste verjetno dobili višjo stopnjo ujemanja.</span><span class="sxs-lookup"><span data-stu-id="ef12e-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="ef12e-124">Izberite segmente, ki jih želite izvoziti v LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="ef12e-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="ef12e-125">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="ef12e-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ef12e-126">![Povezovalnik LiveRamp s preslikavo atributov](media/export-liveramp-segments.png "Povezovalnik LiveRamp s preslikavo atributov")</span><span class="sxs-lookup"><span data-stu-id="ef12e-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ef12e-127">Izvoz podatkov</span><span class="sxs-lookup"><span data-stu-id="ef12e-127">Export the data</span></span>

<span data-ttu-id="ef12e-128">Izvoz se bo kmalu začel, če so bile izpolnjene zahteve za izvoz.</span><span class="sxs-lookup"><span data-stu-id="ef12e-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="ef12e-129">Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ef12e-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="ef12e-130">Ko je izvoz uspešno dokončan, se lahko vpišete v LiveRamp Onboarding, da aktivirate in distribuirate svoje podatke.</span><span class="sxs-lookup"><span data-stu-id="ef12e-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ef12e-131">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="ef12e-131">Data privacy and compliance</span></span>

<span data-ttu-id="ef12e-132">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Liveramp, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="ef12e-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ef12e-133">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Liveramp izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="ef12e-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ef12e-134">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ef12e-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ef12e-135">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="ef12e-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>