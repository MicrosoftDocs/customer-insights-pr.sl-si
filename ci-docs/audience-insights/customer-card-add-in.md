---
title: Namestitev in konfiguracija dodatka za kartice strank
description: Namestite in konfigurirajte dodatek za kartico stranke za Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268064"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="70a73-103">Dodatek za kartico stranke (predogled)</span><span class="sxs-lookup"><span data-stu-id="70a73-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="70a73-104">Pridobite 360-stopinjski pogled svojih strank neposredno v aplikacijah Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="70a73-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="70a73-105">Z dodatkom za kartico stranke si oglejte demografske podatke, vpoglede in časovnice z dejavnostmi.</span><span class="sxs-lookup"><span data-stu-id="70a73-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="70a73-106">Zahteve</span><span class="sxs-lookup"><span data-stu-id="70a73-106">Prerequisites</span></span>

- <span data-ttu-id="70a73-107">Aplikacija Dynamics 365 (kot je Središče za prodajo ali Središče storitev za stranke), različica 9.0 in novejše z omogočenim poenotenim vmesnikom.</span><span class="sxs-lookup"><span data-stu-id="70a73-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="70a73-108">Profili strank, [vključeni iz aplikacije Dynamics 365 prek storitve Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="70a73-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="70a73-109">Uporabniki dodatka za kartice stranke morajo biti [dodani kot uporabniki](permissions.md) pri vpogledih v občinstvo.</span><span class="sxs-lookup"><span data-stu-id="70a73-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="70a73-110">[Konfigurirane možnosti iskanja in filtriranja](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="70a73-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="70a73-111">Demografski kontrolnik: v poenotenem profilu strank so na voljo demografska polja (kot sta starost ali spol).</span><span class="sxs-lookup"><span data-stu-id="70a73-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="70a73-112">Kontrolnik obogatitve: zahteva, da so za profile strank uporabljene aktivne [obogatitve](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="70a73-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="70a73-113">Kontrolnik za obveščanje: zahteva podatke, ustvarjene s strojnim učenjem Azure ([modeli predvidevanja](predictions.md) ali [modeli po meri](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="70a73-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="70a73-114">Kontrolnik merjenja: zahteva [konfigurirane ukrepe](measures.md).</span><span class="sxs-lookup"><span data-stu-id="70a73-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="70a73-115">Kontrolnik časovnice: zahteva [konfigurirane dejavnosti](activities.md).</span><span class="sxs-lookup"><span data-stu-id="70a73-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="70a73-116">Namestitev dodatka za kartice strank</span><span class="sxs-lookup"><span data-stu-id="70a73-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="70a73-117">Dodatek za kartico stranke je rešitev za aplikacije za sodelovanje s strankami v rešitvi Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="70a73-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="70a73-118">Če želite namestiti rešitev, odprite AppSource in poiščite možnost **Kartica za stranke Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="70a73-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="70a73-119">Izberite [dodatek za kartice strank v trgovini AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) in izberite **Prenesi zdaj**.</span><span class="sxs-lookup"><span data-stu-id="70a73-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="70a73-120">Morda se boste morali vpisati s svojimi skrbniškimi poverilnicami za aplikacijo Dynamics 365, da boste lahko namestili rešitev.</span><span class="sxs-lookup"><span data-stu-id="70a73-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="70a73-121">Namestitev rešitve v vaše okolje lahko traja nekaj časa.</span><span class="sxs-lookup"><span data-stu-id="70a73-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="70a73-122">Konfiguriranje dodatka za kartico stranke</span><span class="sxs-lookup"><span data-stu-id="70a73-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="70a73-123">Kot skrbnik pojdite v razdelek **Nastavitve** v storitvi Dynamics 365 in izberite **Rešitve**.</span><span class="sxs-lookup"><span data-stu-id="70a73-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="70a73-124">Izberite povezavo **Prikazno ime** za rešitev dodatka kartice za stranke za **Dynamics 365 Customer Insights (predogled)**.</span><span class="sxs-lookup"><span data-stu-id="70a73-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="70a73-125">![Izberite prikazano ime](media/select-display-name.png "Izberite prikazano ime")</span><span class="sxs-lookup"><span data-stu-id="70a73-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="70a73-126">Izberite **Vpis** in vnesite poverilnice za skrbniški račun, ki ga uporabljate za konfiguriranje storitve Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="70a73-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="70a73-127">Preverite, ali preprečevalnik pojavnih oken v brskalniku ne blokira okna za preverjanje pristnosti, ko izberete gumb **Vpis**.</span><span class="sxs-lookup"><span data-stu-id="70a73-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="70a73-128">Izberite okolje, iz katerega želite pridobiti podatke.</span><span class="sxs-lookup"><span data-stu-id="70a73-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="70a73-129">Določite, katera preslikava polja se zabeleži v aplikaciji Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="70a73-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="70a73-130">Če želite preslikavo opraviti s stikom, izberite polje pri entiteti stranke, ki se ujema z ID-jem entitete stika.</span><span class="sxs-lookup"><span data-stu-id="70a73-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="70a73-131">Če želite preslikavo opraviti s stranko, izberite polje pri entiteti stranke, ki se ujema z ID-jem entitete kupca.</span><span class="sxs-lookup"><span data-stu-id="70a73-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="70a73-132">![Polje ID-ja stika](media/contact-id-field.png "Polje ID-ja stika")</span><span class="sxs-lookup"><span data-stu-id="70a73-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="70a73-133">Če želite shraniti nastavitve, izberite **Shrani konfiguracijo**.</span><span class="sxs-lookup"><span data-stu-id="70a73-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="70a73-134">Nato morate v storitvi Dynamics 365 dodeliti varnostne vloge, da lahko uporabniki prilagodijo in si ogledajo kartico stranke.</span><span class="sxs-lookup"><span data-stu-id="70a73-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="70a73-135">V storitvi Dynamics 365 odprite **Nastavitve** > **Varnost** > **Uporabniki**.</span><span class="sxs-lookup"><span data-stu-id="70a73-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="70a73-136">Izberite uporabnike za urejanje vlog in izberite možnost **Upravljanje vlog**.</span><span class="sxs-lookup"><span data-stu-id="70a73-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="70a73-137">Dodelite vlogo **Prilagojevalec kartic v Customer Insights** uporabnikom, ki bodo prilagajali vsebino, prikazano na kartici, za celo organizacijo.</span><span class="sxs-lookup"><span data-stu-id="70a73-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="70a73-138">Dodajanje kontrolnikov kartic strank v obrazce</span><span class="sxs-lookup"><span data-stu-id="70a73-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="70a73-139">Če želite v obrazec za stik dodati kontrolnike kartice stranke, v storitvi Dynamics 365 odprite **Nastavitve** > **Prilagoditve**.</span><span class="sxs-lookup"><span data-stu-id="70a73-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="70a73-140">Izberite **Prilagajanje sistema**.</span><span class="sxs-lookup"><span data-stu-id="70a73-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="70a73-141">Z brskanjem se pomaknite do entitete **Stik**, jo razširite in izberite možnost **Obrazci**.</span><span class="sxs-lookup"><span data-stu-id="70a73-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="70a73-142">Izberite obrazec za stik, v katerega želite dodati kontrolnike kartice stranke.</span><span class="sxs-lookup"><span data-stu-id="70a73-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="70a73-143">![Izbira obrazca za stik](media/contact-active-forms.png "Izbira obrazca za stik")</span><span class="sxs-lookup"><span data-stu-id="70a73-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="70a73-144">Če želite dodati kontrolnik, povlecite poljubno polje iz možnosti **Raziskovalec polj** na želeno mesto za kontrolnik.</span><span class="sxs-lookup"><span data-stu-id="70a73-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="70a73-145">Na obrazcu izberite polje, ki ste ga pravkar dodali, in izberite **Spremeni lastnosti**.</span><span class="sxs-lookup"><span data-stu-id="70a73-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="70a73-146">Odprite zavihek **Kontrolniki** in izberite **Dodaj kontrolnik**.</span><span class="sxs-lookup"><span data-stu-id="70a73-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="70a73-147">Izberite enega od razpoložljivih kontrolnikov po meri in izberite **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="70a73-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="70a73-148">V pogovornem oknu **Lastnosti polja** počistite potrditveno polje **Prikaži oznako na obrazcu**.</span><span class="sxs-lookup"><span data-stu-id="70a73-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="70a73-149">Izberite možnost **Splet** za kontrolnik.</span><span class="sxs-lookup"><span data-stu-id="70a73-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="70a73-150">Za kontrolnik obogatitve izberite vrsto obogatitve, ki jo želite prikazati, in sicer tako, da konfigurirate polje **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="70a73-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="70a73-151">Za vsako vrsto obogatitve dodajte ločen kontrolnik obogatitve.</span><span class="sxs-lookup"><span data-stu-id="70a73-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="70a73-152">Izberite **Shrani** in **Objavi**, da objavite posodobljeni obrazec za stik.</span><span class="sxs-lookup"><span data-stu-id="70a73-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="70a73-153">Pojdite na objavljeni obrazec za stik.</span><span class="sxs-lookup"><span data-stu-id="70a73-153">Go to the published contact form.</span></span> <span data-ttu-id="70a73-154">Novo dodani kontrolnik bo prikazan.</span><span class="sxs-lookup"><span data-stu-id="70a73-154">You'll see the newly added control.</span></span> <span data-ttu-id="70a73-155">Morda se boste morali prijaviti, ko ga boste prvič uporabili.</span><span class="sxs-lookup"><span data-stu-id="70a73-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="70a73-156">Če želite prilagoditi prikaz na kontrolniku po meri, v zgornjem desnem kotu izberite gumb za urejanje.</span><span class="sxs-lookup"><span data-stu-id="70a73-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="70a73-157">Nadgraditev dodatka za kartico stranke</span><span class="sxs-lookup"><span data-stu-id="70a73-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="70a73-158">Dodatek za kartico stranke se ne nadgradi samodejno.</span><span class="sxs-lookup"><span data-stu-id="70a73-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="70a73-159">Če ga želite nadgraditi na najnovejšo različico, upoštevajte navodila v aplikaciji Dynamics 365, v kateri je nameščen dodatek.</span><span class="sxs-lookup"><span data-stu-id="70a73-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="70a73-160">V aplikaciji Dynamics 365 odprite razdelek **Nastavitve** > **Prilagajanje** in izberite možnost **Rešitve**.</span><span class="sxs-lookup"><span data-stu-id="70a73-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="70a73-161">V tabeli dodatkov poiščite **CustomerInsightsCustomerCard** in izberite vrstico.</span><span class="sxs-lookup"><span data-stu-id="70a73-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="70a73-162">V vrstici z dejanji izberite možnost **Uporabi nadgradnjo rešitve**.</span><span class="sxs-lookup"><span data-stu-id="70a73-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Nadgradite rešitev na območju za prilagoditev v aplikacijah Dynamics 365":::

1. <span data-ttu-id="70a73-164">Po začetku postopka nadgradnje je do zaključka prikazan kazalnik stanja nalaganja.</span><span class="sxs-lookup"><span data-stu-id="70a73-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="70a73-165">Če novejše različice ni, se pri nadgradnji prikaže sporočilo o napaki.</span><span class="sxs-lookup"><span data-stu-id="70a73-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]