---
title: Izvozite podatke Customer Insights v Upravitelja oglasov za Facebook
description: Naučite se, kako konfigurirati povezavo in izvažati v Upravitelja oglasov za Facebook.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e20c7b7fd3989d7621cb7765f38b85c8ab4adfcb
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305130"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="22fbe-103">Izvoz seznamov segmentov v Upravitelja oglasov za Facebook (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="22fbe-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="22fbe-104">Izvozite segmente poenotenih profilov strank v Upravitelja oglasov za Facebook za ustvarjanje oglaševalskih akcij v storitvama Facebook in Instagram.</span><span class="sxs-lookup"><span data-stu-id="22fbe-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="22fbe-105">Predpogoji za povezavo</span><span class="sxs-lookup"><span data-stu-id="22fbe-105">Prerequisites for connection</span></span>

- <span data-ttu-id="22fbe-106">Potrebujete račun [**Facebook oglaševalski račun**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), ki vključuje poslovni račun za [**Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="22fbe-106">You need to have a [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="22fbe-107">Morate biti skrbnik oglaševalskega računa [**Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="22fbe-107">You need to be an administrator on the [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="22fbe-108">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="22fbe-108">Known limitations</span></span>

- <span data-ttu-id="22fbe-109">Do 10 milijonov profilov strank na izvoz v upravitelju oglaševanja Facebook.</span><span class="sxs-lookup"><span data-stu-id="22fbe-109">Up to 10 million customer profiles per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="22fbe-110">Izvoz v Upravitelja oglasov za Facebook je omejen na segmente.</span><span class="sxs-lookup"><span data-stu-id="22fbe-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="22fbe-111">Ustvarite ali posodobite samo občinstva po meri v storitvi Facebook vrste *seznam strank*.</span><span class="sxs-lookup"><span data-stu-id="22fbe-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="22fbe-112">Izvoz segmentov s skupno 10 milijoni profilov lahko traja do 90 minut.</span><span class="sxs-lookup"><span data-stu-id="22fbe-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="22fbe-113">Nastavitev povezave z Upraviteljem oglasov za Facebook</span><span class="sxs-lookup"><span data-stu-id="22fbe-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="22fbe-114">Preden lahko uporabniki ustvarijo izvoz, mora skrbnik konfigurirati povezavo s storitvijo in dovoliti udeležencem, da uporabljajo povezavo.</span><span class="sxs-lookup"><span data-stu-id="22fbe-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="22fbe-115">Odprite razdelek **Skrbnik** > **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="22fbe-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="22fbe-116">Izberite **Dodajanje povezave** in izberite **Upravitelj oglasov za Facebook** za konfiguracijo povezave.</span><span class="sxs-lookup"><span data-stu-id="22fbe-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="22fbe-117">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="22fbe-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="22fbe-118">Ime in vrsta povezave opisujeta to povezavo.</span><span class="sxs-lookup"><span data-stu-id="22fbe-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="22fbe-119">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="22fbe-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="22fbe-120">Izberite, kdo lahko uporablja to povezavo.</span><span class="sxs-lookup"><span data-stu-id="22fbe-120">Choose who can use this connection.</span></span> <span data-ttu-id="22fbe-121">Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki.</span><span class="sxs-lookup"><span data-stu-id="22fbe-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="22fbe-122">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="22fbe-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="22fbe-123">Preverjanje pristnosti z oglasi za Facebook:</span><span class="sxs-lookup"><span data-stu-id="22fbe-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="22fbe-124">Izberite možnost **Nadaljujte s storitvijo Facebook** za prijavo v svoj oglaševalski račun Facebook.</span><span class="sxs-lookup"><span data-stu-id="22fbe-124">Select **Continue with Facebook** to sign in to your Facebook Ads account.</span></span>

   1. <span data-ttu-id="22fbe-125">Omogočite dovoljenje **ads_management** po preverjanju pristnosti s storitvijo Facebook.</span><span class="sxs-lookup"><span data-stu-id="22fbe-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="22fbe-126">Izberite **račun za oglaševanje v storitvi Facebook**, s katerim želite delati.</span><span class="sxs-lookup"><span data-stu-id="22fbe-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="22fbe-127">Na spustnem seznamu izberite možnost **Trenutno občinstvo po meri** ali ustvarite **Novo občinstvo po meri**.</span><span class="sxs-lookup"><span data-stu-id="22fbe-127">Select an **Existing custom audience** from the dropdown list or create a **New custom audience**.</span></span> <span data-ttu-id="22fbe-128">Za več informacij glejte [**Občinstvo v Upravitelju oglasov za Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="22fbe-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="22fbe-129">S tem izvozom lahko ustvarite ali posodobite samo občinstva po meri v storitvi Facebook vrste *seznam strank*.</span><span class="sxs-lookup"><span data-stu-id="22fbe-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="22fbe-130">V nekaterih primerih spustni seznam vsebuje občinstva po meri različnih vrst.</span><span class="sxs-lookup"><span data-stu-id="22fbe-130">In some cases, you see custom audiences of different types in the dropdown list.</span></span> <span data-ttu-id="22fbe-131">Če izberete drugo vrsto kot *seznam strank*, izvoz ne bo uspel.</span><span class="sxs-lookup"><span data-stu-id="22fbe-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="22fbe-132">Preglejte **Zasebnost podatkov in skladnost** in izberite **Strinjam se**.</span><span class="sxs-lookup"><span data-stu-id="22fbe-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="22fbe-133">Izberite možnost **Shrani**, da dokončate povezavo.</span><span class="sxs-lookup"><span data-stu-id="22fbe-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="22fbe-134">Konfiguriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="22fbe-134">Configure an export</span></span>

<span data-ttu-id="22fbe-135">Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave.</span><span class="sxs-lookup"><span data-stu-id="22fbe-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="22fbe-136">Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="22fbe-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="22fbe-137">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="22fbe-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="22fbe-138">Za ustvarjanje novega izvoza izberite **Dodaj cilj**.</span><span class="sxs-lookup"><span data-stu-id="22fbe-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="22fbe-139">V možnosti **Povezava za izvoz** izberite povezavo v razdelku **Upravitelj oglasov za Facebook**.</span><span class="sxs-lookup"><span data-stu-id="22fbe-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="22fbe-140">Če se vam poimenovanje tega odseka ne prikaže, to pomeni, da vam ni na voljo nobena tovrstna povezava.</span><span class="sxs-lookup"><span data-stu-id="22fbe-140">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="22fbe-141">V polju **Izberi polje identifikatorja ključa** izberite **E-poštni naslov**, **Ime in naslov** ali **Telefon** , da pošljete podatke Upravitelju oglasov za Facebook.</span><span class="sxs-lookup"><span data-stu-id="22fbe-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="22fbe-142">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="22fbe-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="22fbe-143">Preslikajte pripadajoče atribute iz poenotene entitete stranke za izbrani identifikator ključa.</span><span class="sxs-lookup"><span data-stu-id="22fbe-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > [!TIP]
   > <span data-ttu-id="22fbe-144">Največ možnosti za ujemanje boste dosegli, če za identifikator ključa izberete možnost **E-poštni naslov**.</span><span class="sxs-lookup"><span data-stu-id="22fbe-144">The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="22fbe-145">Dodajanje dodatnih identifikatorjev lahko izboljša ujemanje.</span><span class="sxs-lookup"><span data-stu-id="22fbe-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="22fbe-146">Izberite **Dodajanje atributa** za preslikavo več atributov za pošiljanje v Upravitelja oglasov za Facebook.</span><span class="sxs-lookup"><span data-stu-id="22fbe-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="22fbe-147">Atributi upravitelja oglasov za Facebook se preslikajo v naslednja uporabnikom prijazna imena: **IM** = **Ime**, **PR** = **Priimek**, **ZI** = **Začetnica imena**, **TELEFON** = **Telefon**, **SP** = **Spol**, **DR** = **Datum rojstva**, **DRŽ** = **Država**, **MST** = **Mesto**, **PŠ** = **Poštna številka**, **DRŽAVA** = **Država/regija**</span><span class="sxs-lookup"><span data-stu-id="22fbe-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / ZIP Code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="22fbe-148">Izberite segmente, ki jih želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="22fbe-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="22fbe-149">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="22fbe-149">Select **Save**.</span></span>

<span data-ttu-id="22fbe-150">S shranjevanjem izvoza se ta ne zažene takoj.</span><span class="sxs-lookup"><span data-stu-id="22fbe-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="22fbe-151">Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="22fbe-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="22fbe-152">Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="22fbe-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="22fbe-153">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="22fbe-153">Data privacy and compliance</span></span>

<span data-ttu-id="22fbe-154">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Upravitelja oglasov za Facebook, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="22fbe-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="22fbe-155">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Upravitelj oglasov za Facebook izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="22fbe-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="22fbe-156">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="22fbe-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="22fbe-157">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="22fbe-157">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
