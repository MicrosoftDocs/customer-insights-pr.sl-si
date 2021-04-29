---
title: Izvozite podatke Customer Insights v Upravitelja oglasov za Facebook
description: Naučite se, kako konfigurirati povezavo in izvažati v Upravitelja oglasov za Facebook.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ca32906a98bc734639fb369d6f5a92e8888fd850
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906830"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="ef9e5-103">Izvoz seznamov segmentov v Upravitelja oglasov za Facebook (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="ef9e5-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="ef9e5-104">Izvozite segmente poenotenih profilov strank v Upravitelja oglasov za Facebook za ustvarjanje oglaševalskih akcij v storitvama Facebook in Instagram.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="ef9e5-105">Predpogoji za povezavo</span><span class="sxs-lookup"><span data-stu-id="ef9e5-105">Prerequisites for connection</span></span>

- <span data-ttu-id="ef9e5-106">Potrebujete [**račun za oglase Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), ki vključuje [**poslovni račun Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="ef9e5-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="ef9e5-107">Biti morate skrbnik [**računa za oglaševanje v storitvi Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="ef9e5-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ef9e5-108">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="ef9e5-108">Known limitations</span></span>

- <span data-ttu-id="ef9e5-109">Do 10 milijonov profilov strank na posamezen izvoz v Upravitelja oglasov za Facebook.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-109">Up to 10 million customer profile per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="ef9e5-110">Izvoz v Upravitelja oglasov za Facebook je omejen na segmente.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="ef9e5-111">Ustvarite ali posodobite samo občinstva po meri v storitvi Facebook vrste *seznam strank*.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="ef9e5-112">Izvoz segmentov s skupno 10 milijoni profilov lahko traja do 90 minut.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="ef9e5-113">Nastavitev povezave z Upraviteljem oglasov za Facebook</span><span class="sxs-lookup"><span data-stu-id="ef9e5-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="ef9e5-114">Preden lahko uporabniki ustvarijo izvoz, mora skrbnik konfigurirati povezavo s storitvijo in dovoliti udeležencem, da uporabljajo povezavo.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="ef9e5-115">Odprite razdelek **Skrbnik** > **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ef9e5-116">Izberite **Dodajanje povezave** in izberite **Upravitelj oglasov za Facebook** za konfiguracijo povezave.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="ef9e5-117">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ef9e5-118">Ime in vrsta povezave opisujeta to povezavo.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ef9e5-119">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ef9e5-120">Izberite, kdo lahko uporablja to povezavo.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-120">Choose who can use this connection.</span></span> <span data-ttu-id="ef9e5-121">Če ne izvedete nobenih dejanj, je privzeto **Skrbniki**.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-121">If you take no action, the default will be **Administrators**.</span></span> <span data-ttu-id="ef9e5-122">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ef9e5-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ef9e5-123">Preverjanje pristnosti z oglasi za Facebook:</span><span class="sxs-lookup"><span data-stu-id="ef9e5-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="ef9e5-124">Izberite **Nadaljujte z računom Facebook**, da se prijavite v račun za oglaševanje v storitvi Facebook.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-124">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

   1. <span data-ttu-id="ef9e5-125">Omogočite dovoljenje **ads_management** po preverjanju pristnosti s storitvijo Facebook.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="ef9e5-126">Izberite **račun za oglaševanje v storitvi Facebook**, s katerim želite delati.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="ef9e5-127">Izberite **Obstoječe občinstvo po meri** s spustnega seznama ali ustvarite **Novo občinstvo po meri**.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-127">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="ef9e5-128">Za več informacij glejte [**Občinstvo v Upravitelju oglasov za Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="ef9e5-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="ef9e5-129">S tem izvozom lahko ustvarite ali posodobite samo občinstva po meri v storitvi Facebook vrste *seznam strank*.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="ef9e5-130">V nekaterih primerih v spustnem seznamu vidite občinstva po meri drugih vrst.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-130">In some cases, you see custom audiences of different types in the drop-down list.</span></span> <span data-ttu-id="ef9e5-131">Če izberete drugo vrsto kot *seznam strank*, izvoz ne bo uspel.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="ef9e5-132">Preglejte **Zasebnost podatkov in skladnost** in izberite **Strinjam se**.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="ef9e5-133">Izberite možnost **Shrani**, da dokončate povezavo.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ef9e5-134">Konfiguriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="ef9e5-134">Configure an export</span></span>

<span data-ttu-id="ef9e5-135">Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ef9e5-136">Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ef9e5-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ef9e5-137">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ef9e5-138">Za ustvarjanje novega izvoza izberite **Dodaj cilj**.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="ef9e5-139">V možnosti **Povezava za izvoz** izberite povezavo v razdelku **Upravitelj oglasov za Facebook**.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="ef9e5-140">Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ef9e5-141">V polju **Izberi polje identifikatorja ključa** izberite **E-poštni naslov**, **Ime in naslov** ali **Telefon** , da pošljete podatke Upravitelju oglasov za Facebook.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="ef9e5-142">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="ef9e5-143">Preslikajte pripadajoče atribute iz poenotene entitete stranke za izbrani identifikator ključa.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="ef9e5-144">[TIP] Če izberete **E-poštni naslov** kot identifikator ključa, imate največ možnosti za ujemanje.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-144">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="ef9e5-145">Dodajanje dodatnih identifikatorjev lahko izboljša ujemanje.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="ef9e5-146">Izberite **Dodajanje atributa** za preslikavo več atributov za pošiljanje v Upravitelja oglasov za Facebook.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="ef9e5-147">Atributi Upravitelja oglasov za Facebook se preslikajo na naslednja uporabnikom prijazna imena: **FN** = **Ime**, **LN** = **Priimek**, **FI** = **Prva začetnica**, **TELEFON** = **Telefon**, **GEN** = **Spol**, **DOB** = **Datum rojstva**, **ST** = **Zvezna država**, **CT** = **Mesto**, **ZIP** = **Poštna številka**, **DRŽAVA** = **Država/regija**</span><span class="sxs-lookup"><span data-stu-id="ef9e5-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="ef9e5-148">Izberite segmente, ki jih želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="ef9e5-149">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-149">Select **Save**.</span></span>

<span data-ttu-id="ef9e5-150">S shranjevanjem izvoza se ta ne zažene takoj.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ef9e5-151">Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ef9e5-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ef9e5-152">Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ef9e5-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ef9e5-153">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="ef9e5-153">Data privacy and compliance</span></span>

<span data-ttu-id="ef9e5-154">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Upravitelja oglasov za Facebook, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ef9e5-155">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Upravitelj oglasov za Facebook izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ef9e5-156">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ef9e5-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ef9e5-157">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="ef9e5-157">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
