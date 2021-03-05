---
title: Delo z API-ji
description: Uporaba API-jev in razumevanje omejitev.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 966db1a22e7dece1bcd89733880bce059151157f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267544"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="8beaf-103">Delo z API-ji za Customer Insights</span><span class="sxs-lookup"><span data-stu-id="8beaf-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="8beaf-104">Dynamics 365 Customer Insights ponuja API-je za izdelavo lastnih aplikacij, ki temeljijo na vaših podatkih v storitvi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8beaf-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8beaf-105">Podrobnosti o teh API-jih so navedene pri [sklicu za API-je za Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="8beaf-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="8beaf-106">Vključujejo dodatne informacije o postopkih, parametrih in odzivih.</span><span class="sxs-lookup"><span data-stu-id="8beaf-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="8beaf-107">Ta članek vas pomaga pri dostopu do API-jev za Customer Insights, ustvarjanju registracije aplikacije Azure in začetku uporabe razpoložljivih odjemalskih knjižnic.</span><span class="sxs-lookup"><span data-stu-id="8beaf-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="8beaf-108">Začetek uporabe API-jev za Customer Insights</span><span class="sxs-lookup"><span data-stu-id="8beaf-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="8beaf-109">[Vpišite se](https://home.ci.ai.dynamics.com) v aplikacijo Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8beaf-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="8beaf-110">Če še nimate naročnine, [se prijavite za preskusno različico aplikacije Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="8beaf-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="8beaf-111">Če želite omogočiti API-je v okolju Customer Insights, izberite **Skrbnik** > **Dovoljenja**.</span><span class="sxs-lookup"><span data-stu-id="8beaf-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="8beaf-112">Za to boste potrebovali skrbniška dovoljenja.</span><span class="sxs-lookup"><span data-stu-id="8beaf-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="8beaf-113">Izberite zavihek **API-ji** in izberite gumb **Omogoči**.</span><span class="sxs-lookup"><span data-stu-id="8beaf-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="8beaf-114">Z omogočanjem API-jev se ustvari primarni in sekundarni naročniški ključ za vaš primerek, ki se uporablja v zahtevah API-ja.</span><span class="sxs-lookup"><span data-stu-id="8beaf-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="8beaf-115">Ključe lahko znova ustvarite tako, da izberete **Znova ustvari primarnega** ali **Znova ustvari sekundarnega** v razdelku **Skrbnik** > **Dovoljenja** > **API-ji**.</span><span class="sxs-lookup"><span data-stu-id="8beaf-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Omogočite API-je za Customer Insights":::

1. <span data-ttu-id="8beaf-117">Izberite **Raziskovanje API-jev**, da preizkusite API-je.</span><span class="sxs-lookup"><span data-stu-id="8beaf-117">Select **Explore our APIs** to try out the APIs.</span></span>

1. <span data-ttu-id="8beaf-118">Izberite postopek API-ja in izberite **Preskusi**.</span><span class="sxs-lookup"><span data-stu-id="8beaf-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="8beaf-119">V stranskem podoknu nastavite vrednost v spustnem meniju **Avtorizacija** na **implicitno**.</span><span class="sxs-lookup"><span data-stu-id="8beaf-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="8beaf-120">Pri glavi `Authorization` se doda nosilni žeton.</span><span class="sxs-lookup"><span data-stu-id="8beaf-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="8beaf-121">Vaš naročniški ključ bo samodejno izpolnjen.</span><span class="sxs-lookup"><span data-stu-id="8beaf-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="8beaf-122">Po želji dodajte vse potrebne parametre poizvedbe.</span><span class="sxs-lookup"><span data-stu-id="8beaf-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="8beaf-123">Pomaknite se na dno stranskega podokna in izberite **Pošlji**.</span><span class="sxs-lookup"><span data-stu-id="8beaf-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="8beaf-124">Odgovor HTTP se bo kmalu prikazal spodaj.</span><span class="sxs-lookup"><span data-stu-id="8beaf-124">The HTTP response will soon appear below.</span></span>

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="8beaf-125">Ustvarjanje registracije nove aplikacije v portalu Azure</span><span class="sxs-lookup"><span data-stu-id="8beaf-125">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="8beaf-126">Ti koraki vam pomagajo začeti uporabljati API-je za Customer Insights v aplikaciji Azure z uporabo dodeljenih dovoljenj.</span><span class="sxs-lookup"><span data-stu-id="8beaf-126">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="8beaf-127">Najprej se prepričajte, da ste zaključili [razdelek za začetek](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="8beaf-127">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="8beaf-128">Vpišite se v [portal Azure](https://portal.azure.com) z računom, ki lahko dostopa do podatkov Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8beaf-128">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="8beaf-129">Na levi izberite **Registracije aplikacij**.</span><span class="sxs-lookup"><span data-stu-id="8beaf-129">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="8beaf-130">Izberite **Nova registracija** ter navedite ime aplikacije in izberite vrsto računa.</span><span class="sxs-lookup"><span data-stu-id="8beaf-130">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="8beaf-131">Lahko tudi dodate URL za preusmeritev.</span><span class="sxs-lookup"><span data-stu-id="8beaf-131">Optionally, add a redirect URL.</span></span> <span data-ttu-id="8beaf-132">http://localhost zadostuje za razvoj aplikacije v vašem lokalnem računalniku.</span><span class="sxs-lookup"><span data-stu-id="8beaf-132">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="8beaf-133">V razdelku za registracijo nove aplikacije izberite **Dovoljenja za API**.</span><span class="sxs-lookup"><span data-stu-id="8beaf-133">On your new App registration, go to **API permissions**.</span></span>

1. <span data-ttu-id="8beaf-134">Izberite **Dodaj dovoljenje** in zatem **Customer Insights** v stranskem podoknu.</span><span class="sxs-lookup"><span data-stu-id="8beaf-134">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="8beaf-135">Za možnost **Vrsta dovoljenja** izberite **Dodeljena dovoljenja** in izberite dovoljenje **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="8beaf-135">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="8beaf-136">Izberite **Dodaj dovoljenja**.</span><span class="sxs-lookup"><span data-stu-id="8beaf-136">Select **Add permissions**.</span></span> <span data-ttu-id="8beaf-137">Če morate do API-ja dostopati brez vpisa uporabnika, preberite razdelek [Dovoljenja aplikacij za povezovanje med strežniki](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="8beaf-137">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="8beaf-138">Izberite **Podeli soglasje skrbnika za ...**, da dokončate registracijo aplikacije.</span><span class="sxs-lookup"><span data-stu-id="8beaf-138">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="8beaf-139">ID aplikacije/odjemalca lahko uporabite za registracijo te aplikacije v knjižnici za preverjanje pristnosti Microsoft Authentication Library (MSAL), da prejmete nosilni žeton, ki ga z vašo zahtevo pošljete v API.</span><span class="sxs-lookup"><span data-stu-id="8beaf-139">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

<span data-ttu-id="8beaf-140">Za več informacij o knjižnici MSAL glejte [Pregled knjižnice Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="8beaf-140">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="8beaf-141">Če želite več informacij o registraciji aplikacij v storitvi Azure, glejte razdelek [Nova izkušnja pri registraciji aplikacije portala Azure](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="8beaf-141">For more information about app registration in Azure, see [The new Azure portal app registration experience](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="8beaf-142">Za informacije o uporabi API-jev pri naših odjemalskih knjižnicah glejte [Odjemalske knjižnice Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="8beaf-142">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="8beaf-143">Dovoljenja aplikacij za povezovanje med strežniki</span><span class="sxs-lookup"><span data-stu-id="8beaf-143">Server-to-server application permissions</span></span>

<span data-ttu-id="8beaf-144">[Razdelek za registracijo aplikacije](#create-a-new-app-registration-in-the-azure-portal) opisuje, kako registrirati aplikacijo, ki za preverjanje pristnosti od uporabnika zahteva vpis.</span><span class="sxs-lookup"><span data-stu-id="8beaf-144">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="8beaf-145">Naučite se ustvariti registracijo aplikacije, ki ne potrebuje interakcije uporabnika in jo je mogoče zagnati v strežniku.</span><span class="sxs-lookup"><span data-stu-id="8beaf-145">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="8beaf-146">Pri registraciji aplikacije v portalu Azure izberite **Dovoljenja za API**.</span><span class="sxs-lookup"><span data-stu-id="8beaf-146">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="8beaf-147">Izberite **Dodaj dovoljenje** in zatem **Customer Insights** v stranskem podoknu.</span><span class="sxs-lookup"><span data-stu-id="8beaf-147">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="8beaf-148">Za možnost **Vrsta dovoljenja** izberite **Dovoljenja aplikacije** in izberite dovoljenje **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="8beaf-148">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="8beaf-149">Izberite **Dodaj dovoljenja**.</span><span class="sxs-lookup"><span data-stu-id="8beaf-149">Select **Add permissions**.</span></span>

1. <span data-ttu-id="8beaf-150">Če želite podati skrbniško soglasje za to dovoljenje aplikacije, morate dodati glavno ime storitve.</span><span class="sxs-lookup"><span data-stu-id="8beaf-150">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="8beaf-151">Namestite modul Azure Active Directory (AD) PowerShell: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="8beaf-151">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="8beaf-152">Povežite račun AD: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="8beaf-152">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="8beaf-153">ID najemnika lahko najdete v razdelku **Pregled** > **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="8beaf-153">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="8beaf-154">Zaženite naslednji ukaz, da dodate glavno ime storitve Azure AD: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"`. Parameter AppId se nanaša na aplikacijo API-ja za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8beaf-154">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Vzorec glavnega imena storitve":::

1. <span data-ttu-id="8beaf-156">Vrnite se v razdelek **Dovoljenja za API**, da registrirate aplikacijo.</span><span class="sxs-lookup"><span data-stu-id="8beaf-156">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="8beaf-157">Izberite **Podeli soglasje skrbnika za ...**, da dokončate registracijo aplikacije.</span><span class="sxs-lookup"><span data-stu-id="8beaf-157">Select **Grant admin consent for...** to complete the app registration.</span></span>

1. <span data-ttu-id="8beaf-158">Na koncu moramo še dodati ime registracije aplikacije kot uporabnik v storitvi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8beaf-158">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="8beaf-159">Odprite Customer Insights, izberite **Skrbnik** > **Dovoljenja** in izberite **Dodaj uporabnika**.</span><span class="sxs-lookup"><span data-stu-id="8beaf-159">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="8beaf-160">Poiščite ime registracije za svojo aplikacijo, izberite ga med rezultati iskanja in izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="8beaf-160">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="8beaf-161">Odjemalske knjižnice Customer Insights</span><span class="sxs-lookup"><span data-stu-id="8beaf-161">Customer Insights client libraries</span></span>

<span data-ttu-id="8beaf-162">Ta razdelek vam pomaga začeti uporabljati odjemalske knjižnice, ki so na voljo za API-je za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8beaf-162">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span>

### <a name="c-nuget"></a><span data-ttu-id="8beaf-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="8beaf-163">C# NuGet</span></span>

<span data-ttu-id="8beaf-164">Naučite se uporabljati odjemalske knjižnice C# storitve NuGet.org. Za več informacij o paketu NuGet glejte [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="8beaf-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="8beaf-165">Trenutno ta paket cilja na ogrodja netstandard2.0 in netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="8beaf-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="8beaf-166">Dodajanje odjemalske knjižnice C# v projekt C#</span><span class="sxs-lookup"><span data-stu-id="8beaf-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="8beaf-167">V storitvi Visual Studio odprite **upravitelja paketov NuGet** za svoj projekt.</span><span class="sxs-lookup"><span data-stu-id="8beaf-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="8beaf-168">Poiščite **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="8beaf-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="8beaf-169">Izberite **Namesti** za dodajanje paketa v projekt.</span><span class="sxs-lookup"><span data-stu-id="8beaf-169">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="8beaf-170">Ta ukaz lahko zaženete tudi v **konzoli upravitelja paketov NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="8beaf-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Dodajte paket NuGet v projekt Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="8beaf-172">Uporaba odjemalske knjižnice C#</span><span class="sxs-lookup"><span data-stu-id="8beaf-172">Use the C# client library</span></span>

1. <span data-ttu-id="8beaf-173">Uporabite knjižnico [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview), da prejmete `AccessToken` z uporabo obstoječe [registracije aplikacije Azure](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="8beaf-173">Use the [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="8beaf-174">Po uspešnem preverjanju pristnosti in pridobitvi žetona izdelajte novega oz. uporabite obstoječega odjemalca `HttpClient`, in sicer z dodatno **»avtorizacijo« DefaultRequestHeaders** nastavljeno na **Nosilec <access token>** in možnostjo **Ocp-Apim-Subscription-Key** nastavljeno na [**naročniški ključ** iz okolja Customer Insights](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="8beaf-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="8beaf-175">Ponastavite glavo **Avtorizacija**, kadar je to primerno.</span><span class="sxs-lookup"><span data-stu-id="8beaf-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="8beaf-176">Na primer, ko je žeton potekel.</span><span class="sxs-lookup"><span data-stu-id="8beaf-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="8beaf-177">Odjemalca `HttpClient` posredujte za pripravo odjemalca `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="8beaf-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Vzorec odjemalca httpclient":::

1. <span data-ttu-id="8beaf-179">Z odjemalcem prikličite »načine razširitve«, na primer `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="8beaf-179">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="8beaf-180">Če je zaželen dostop do temeljne možnosti `Microsoft.Rest.HttpOperationResponse`, uporabite »načine sporočil http«, na primer `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="8beaf-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="8beaf-181">Vrsta odziva bo verjetno `object`, ker lahko ta način vrne več vrst (na primer `IList<InstanceInfo>` in `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="8beaf-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="8beaf-182">Če želite preveriti vrsto vrnitve, lahko predmete varno pretvorite v vrste odzivov, določene na [strani s podrobnostmi o API-ju](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) za ta postopek.</span><span class="sxs-lookup"><span data-stu-id="8beaf-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="8beaf-183">Če potrebujete več informacij o zahtevi, uporabite **načine sporočil http** za dostop do predmeta neobdelanega odziva.</span><span class="sxs-lookup"><span data-stu-id="8beaf-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]