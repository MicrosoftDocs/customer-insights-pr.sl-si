---
title: Izvozite podatke Customer Insights v Upravitelja oglasov za Facebook
description: Preberite, kako konfigurirati povezavo z Upraviteljem oglasov za Facebook.
ms.date: 06/05/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3e2b52fe743563e4bf61d870cbf1718e6c752a67
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596703"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="0d9cc-103">Povezovalnik za Upravitelja oglasov za Facebook (predogled)</span><span class="sxs-lookup"><span data-stu-id="0d9cc-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="0d9cc-104">Izvozite segmente poenotenih profilov strank v Upravitelja oglasov za Facebook za ustvarjanje oglaševalskih akcij v storitvama Facebook in Instagram.</span><span class="sxs-lookup"><span data-stu-id="0d9cc-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0d9cc-105">Zahteve</span><span class="sxs-lookup"><span data-stu-id="0d9cc-105">Prerequisites</span></span>

- <span data-ttu-id="0d9cc-106">Imeti morate [**račun za oglaševanje v storitvi Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), ki vključuje [**poslovni račun Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="0d9cc-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="0d9cc-107">Biti morate skrbnik [**računa za oglaševanje v storitvi Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="0d9cc-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="0d9cc-108">Poveži z Upraviteljem oglasov za Facebook</span><span class="sxs-lookup"><span data-stu-id="0d9cc-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="0d9cc-109">Izberite **Skrbnik** > **Cilji za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="0d9cc-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0d9cc-110">V razdelku **Upravitelj oglasov za Facebook** izberite **Nastavi**.</span><span class="sxs-lookup"><span data-stu-id="0d9cc-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="0d9cc-111">Dajte svojemu cilju izvoza prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="0d9cc-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="0d9cc-112">Izberite **Nadaljujte z računom Facebook**, da se prijavite v račun za oglaševanje v storitvi Facebook.</span><span class="sxs-lookup"><span data-stu-id="0d9cc-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="0d9cc-113">Omogočite dovoljenje **ads_management** po preverjanju pristnosti s storitvijo Facebook.</span><span class="sxs-lookup"><span data-stu-id="0d9cc-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="0d9cc-114">Izberite **račun za oglaševanje v storitvi Facebook**, s katerim želite delati.</span><span class="sxs-lookup"><span data-stu-id="0d9cc-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="0d9cc-115">Izberite **Obstoječe občinstvo po meri** s spustnega seznama ali ustvarite **Novo občinstvo po meri**.</span><span class="sxs-lookup"><span data-stu-id="0d9cc-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="0d9cc-116">Za več informacij glejte [**Občinstvo v Upravitelju oglasov za Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="0d9cc-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="0d9cc-117">Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.</span><span class="sxs-lookup"><span data-stu-id="0d9cc-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0d9cc-118">Izberite **Naslednji** za nastavitev izvoza.</span><span class="sxs-lookup"><span data-stu-id="0d9cc-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="0d9cc-119">Konfiguracija povezovalnika</span><span class="sxs-lookup"><span data-stu-id="0d9cc-119">Configure the connector</span></span>

1. <span data-ttu-id="0d9cc-120">V polju **Izberi polje identifikatorja ključa** izberite **E-poštni naslov**, **Ime in naslov** ali **Telefon** , da pošljete podatke Upravitelju oglasov za Facebook.</span><span class="sxs-lookup"><span data-stu-id="0d9cc-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="0d9cc-121">Preslikajte pripadajoče atribute iz poenotene entitete stranke za izbrani identifikator ključa.</span><span class="sxs-lookup"><span data-stu-id="0d9cc-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="0d9cc-122">[TIP] Če izberete **E-poštni naslov** kot identifikator ključa, imate največ možnosti za ujemanje.</span><span class="sxs-lookup"><span data-stu-id="0d9cc-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="0d9cc-123">Dodajanje dodatnih identifikatorjev lahko izboljša ujemanje.</span><span class="sxs-lookup"><span data-stu-id="0d9cc-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="0d9cc-124">Izberite **Dodaj atribut** za preslikavo dodatnih atributov, ki jih želite poslati Upravitelju oglasov za Facebook.</span><span class="sxs-lookup"><span data-stu-id="0d9cc-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="0d9cc-125">Atributi Upravitelja oglasov za Facebook se preslikajo na naslednja uporabnikom prijazna imena: **FN** = **Ime**, **LN** = **Priimek**, **FI** = **Prva začetnica**, **TELEFON** = **Telefon**, **GEN** = **Spol**, **DOB** = **Datum rojstva**, **ST** = **Zvezna država**, **CT** = **Mesto**, **ZIP** = **Poštna številka**, **DRŽAVA** = **Država/regija**</span><span class="sxs-lookup"><span data-stu-id="0d9cc-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="0d9cc-126">Izberite segmente, ki jih želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="0d9cc-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="0d9cc-127">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="0d9cc-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="0d9cc-128">Izvoz podatkov</span><span class="sxs-lookup"><span data-stu-id="0d9cc-128">Export the data</span></span>

<span data-ttu-id="0d9cc-129">Lahko [izvozite podatke na zahtevo](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="0d9cc-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="0d9cc-130">Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0d9cc-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0d9cc-131">Znane omejitve</span><span class="sxs-lookup"><span data-stu-id="0d9cc-131">Known limitations</span></span>

- <span data-ttu-id="0d9cc-132">Do 10 milijonov profilov strank na posamezen izvoz v upravitelja oglasov za Facebook</span><span class="sxs-lookup"><span data-stu-id="0d9cc-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="0d9cc-133">Izvoz v upravitelja oglasov za Facebook je omejen na segmente</span><span class="sxs-lookup"><span data-stu-id="0d9cc-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="0d9cc-134">Izvoz segmentov s skupno 10 milijonom profilov lahko traja do 90 minut</span><span class="sxs-lookup"><span data-stu-id="0d9cc-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0d9cc-135">Zasebnost podatkov in skladnost</span><span class="sxs-lookup"><span data-stu-id="0d9cc-135">Data privacy and compliance</span></span>

<span data-ttu-id="0d9cc-136">Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Upravitelja oglasov za Facebook, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki.</span><span class="sxs-lookup"><span data-stu-id="0d9cc-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0d9cc-137">Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Upravitelj oglasov za Facebook izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti.</span><span class="sxs-lookup"><span data-stu-id="0d9cc-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="0d9cc-138">Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0d9cc-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0d9cc-139">Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.</span><span class="sxs-lookup"><span data-stu-id="0d9cc-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]