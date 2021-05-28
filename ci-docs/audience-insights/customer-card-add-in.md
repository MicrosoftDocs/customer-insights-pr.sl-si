---
title: Dodatek za kartico stranke v aplikacijah Dynamics 365
description: S tem dodatkom prikažite podatke iz vpogledov v občinstvo v aplikacijah Dynamics 365.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059608"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="ec8ca-103">Dodatek za kartico stranke (predogled)</span><span class="sxs-lookup"><span data-stu-id="ec8ca-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ec8ca-104">Pridobite 360-stopinjski pogled svojih strank neposredno v aplikacijah Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="ec8ca-105">Z dodatkom za kartico stranke, nameščenim v podprti aplikaciji Dynamics 365, lahko izberete prikaz demografskih podatkov, vpogledov in časovnic dejavnosti.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="ec8ca-106">Dodatek bo pridobil podatke iz Customer Insights, ne da bi to vplivalo na podatke v povezani aplikaciji Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="ec8ca-107">Zahteve</span><span class="sxs-lookup"><span data-stu-id="ec8ca-107">Prerequisites</span></span>

- <span data-ttu-id="ec8ca-108">Dodatek deluje samo z aplikacijami Dynamics 365, ki temeljijo na modelu, na primer Sales ali Customer Service, različice 9.0 in novejše.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="ec8ca-109">Da se bodo vaši podatki iz aplikacije Dynamics 365 preslikali v profile strank za vpoglede v občinstvo, morajo biti [uvoženi iz aplikacije Dynamics 365 s priključkom Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="ec8ca-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="ec8ca-110">Vsi uporabniki aplikacije Dynamics 365 in dodatka za kartice strank morajo biti za ogled podatkov [dodani kot uporabniki](permissions.md) v vpogledih v občinstvo.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="ec8ca-111">Za delovanje iskanja podatkov so zahtevane [konfigurirane možnosti iskanja in filtriranja](search-filter-index.md) v vpogledih v občinstvo.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="ec8ca-112">Vsak kontrolnik dodatka se zanaša na določene podatke v vpogledih v občinstvo:</span><span class="sxs-lookup"><span data-stu-id="ec8ca-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="ec8ca-113">Kontrolnik merjenja: zahteva [konfigurirane ukrepe](measures.md).</span><span class="sxs-lookup"><span data-stu-id="ec8ca-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="ec8ca-114">Kontrolnik obveščanja: zahteva podatke, ustvarjene z [napovedmi](predictions.md) ali [modeli po meri](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="ec8ca-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="ec8ca-115">Demografski kontrolnik: v poenotenem profilu strank so na voljo demografska polja (kot sta starost ali spol).</span><span class="sxs-lookup"><span data-stu-id="ec8ca-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="ec8ca-116">Kontrolnik obogatitve: zahteva, da so za profile strank uporabljene aktivne [obogatitve](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="ec8ca-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="ec8ca-117">Kontrolnik časovnice: zahteva [konfigurirane dejavnosti](activities.md).</span><span class="sxs-lookup"><span data-stu-id="ec8ca-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="ec8ca-118">Namestitev dodatka za kartice strank</span><span class="sxs-lookup"><span data-stu-id="ec8ca-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="ec8ca-119">Dodatek za kartico stranke je rešitev za aplikacije za sodelovanje s strankami v rešitvi Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="ec8ca-120">Če želite namestiti rešitev, odprite AppSource in poiščite možnost **Kartica za stranke Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="ec8ca-121">Izberite [dodatek za kartice strank v trgovini AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) in izberite **Prenesi zdaj**.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="ec8ca-122">Morda se boste morali vpisati s svojimi skrbniškimi poverilnicami za aplikacijo Dynamics 365, da boste lahko namestili rešitev.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="ec8ca-123">Namestitev rešitve v vaše okolje lahko traja nekaj časa.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="ec8ca-124">Konfiguriranje dodatka za kartico stranke</span><span class="sxs-lookup"><span data-stu-id="ec8ca-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="ec8ca-125">Kot skrbnik pojdite v razdelek **Nastavitve** v storitvi Dynamics 365 in izberite **Rešitve**.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="ec8ca-126">Izberite povezavo **Prikazno ime** za rešitev dodatka kartice za stranke za **Dynamics 365 Customer Insights (predogled)**.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ec8ca-127">![Izberite prikazano ime](media/select-display-name.png "Izberite prikazano ime")</span><span class="sxs-lookup"><span data-stu-id="ec8ca-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="ec8ca-128">Izberite **Vpis** in vnesite poverilnice za skrbniški račun, ki ga uporabljate za konfiguriranje storitve Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ec8ca-129">Preverite, ali preprečevalnik pojavnih oken v brskalniku ne blokira okna za preverjanje pristnosti, ko izberete gumb **Vpis**.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="ec8ca-130">Izberite okolje storitve Customer Insights, iz katerega želite pridobiti podatke.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="ec8ca-131">Določite preslikavo polj v zapise v aplikaciji Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="ec8ca-132">Glede na vaše podatke v rešitvi Customer Insights lahko preslikate naslednje možnosti:</span><span class="sxs-lookup"><span data-stu-id="ec8ca-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="ec8ca-133">Če želite preslikavo opraviti s stikom, izberite polje pri entiteti stranke, ki se ujema z ID-jem entitete stika.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="ec8ca-134">Če želite preslikavo opraviti s stranko, izberite polje pri entiteti stranke, ki se ujema z ID-jem entitete kupca.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ec8ca-135">![Polje ID-ja stika](media/contact-id-field.png "Polje ID-ja stika")</span><span class="sxs-lookup"><span data-stu-id="ec8ca-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="ec8ca-136">Če želite shraniti nastavitve, izberite **Shrani konfiguracijo**.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="ec8ca-137">Nato morate v storitvi Dynamics 365 dodeliti varnostne vloge, da lahko uporabniki prilagodijo in si ogledajo kartico stranke.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="ec8ca-138">V storitvi Dynamics 365 odprite **Nastavitve** > **Varnost** > **Uporabniki**.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="ec8ca-139">Izberite uporabnike za urejanje vlog in izberite možnost **Upravljanje vlog**.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="ec8ca-140">Dodelite vlogo **Prilagojevalec kartic v Customer Insights** uporabnikom, ki bodo prilagajali vsebino, prikazano na kartici, za celo organizacijo.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="ec8ca-141">Dodajanje kontrolnikov kartic strank v obrazce</span><span class="sxs-lookup"><span data-stu-id="ec8ca-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="ec8ca-142">Če želite v obrazec za stik dodati kontrolnike kartice stranke, v storitvi Dynamics 365 odprite **Nastavitve** > **Prilagoditve**.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="ec8ca-143">Izberite **Prilagajanje sistema**.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="ec8ca-144">Z brskanjem se pomaknite do entitete **Stik**, jo razširite in izberite možnost **Obrazci**.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="ec8ca-145">Izberite obrazec za stik, v katerega želite dodati kontrolnike kartice stranke.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ec8ca-146">![Izbira obrazca za stik](media/contact-active-forms.png "Izbira obrazca za stik")</span><span class="sxs-lookup"><span data-stu-id="ec8ca-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="ec8ca-147">Če želite dodati kontrolnik, povlecite poljubno polje iz možnosti **Raziskovalec polj** na želeno mesto za kontrolnik.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="ec8ca-148">Na obrazcu izberite polje, ki ste ga pravkar dodali, in izberite **Spremeni lastnosti**.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="ec8ca-149">Odprite zavihek **Kontrolniki** in izberite **Dodaj kontrolnik**.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="ec8ca-150">Izberite enega od razpoložljivih kontrolnikov po meri in izberite **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="ec8ca-151">V pogovornem oknu **Lastnosti polja** počistite potrditveno polje **Prikaži oznako na obrazcu**.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="ec8ca-152">Izberite možnost **Splet** za kontrolnik.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="ec8ca-153">Za kontrolnik obogatitve izberite vrsto obogatitve, ki jo želite prikazati, in sicer tako, da konfigurirate polje **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="ec8ca-154">Za vsako vrsto obogatitve dodajte ločen kontrolnik obogatitve.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="ec8ca-155">Izberite **Shrani** in **Objavi**, da objavite posodobljeni obrazec za stik.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="ec8ca-156">Pojdite na objavljeni obrazec za stik.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-156">Go to the published contact form.</span></span> <span data-ttu-id="ec8ca-157">Novo dodani kontrolnik bo prikazan.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-157">You'll see the newly added control.</span></span> <span data-ttu-id="ec8ca-158">Morda se boste morali prijaviti, ko ga boste prvič uporabili.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="ec8ca-159">Če želite prilagoditi prikaz na kontrolniku po meri, v zgornjem desnem kotu izberite gumb za urejanje.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="ec8ca-160">Nadgraditev dodatka za kartico stranke</span><span class="sxs-lookup"><span data-stu-id="ec8ca-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="ec8ca-161">Dodatek za kartico stranke se ne nadgradi samodejno.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="ec8ca-162">Če ga želite nadgraditi na najnovejšo različico, upoštevajte navodila v aplikaciji Dynamics 365, v kateri je nameščen dodatek.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="ec8ca-163">V aplikaciji Dynamics 365 odprite razdelek **Nastavitve** > **Prilagajanje** in izberite možnost **Rešitve**.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="ec8ca-164">V tabeli dodatkov poiščite **CustomerInsightsCustomerCard** in izberite vrstico.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="ec8ca-165">V vrstici z dejanji izberite možnost **Uporabi nadgradnjo rešitve**.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Nadgradite rešitev na območju za prilagoditev v aplikacijah Dynamics 365":::

1. <span data-ttu-id="ec8ca-167">Po začetku postopka nadgradnje je do zaključka prikazan kazalnik stanja nalaganja.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="ec8ca-168">Če novejše različice ni, se pri nadgradnji prikaže sporočilo o napaki.</span><span class="sxs-lookup"><span data-stu-id="ec8ca-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
