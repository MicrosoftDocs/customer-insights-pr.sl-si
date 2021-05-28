---
title: Delo z API-ji
description: Uporaba API-jev in razumevanje omejitev.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 4d41d7d328dfa6699b5f5e992d3a5bf3179490d8
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016640"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="9f512-103">Delo z API-ji za Customer Insights</span><span class="sxs-lookup"><span data-stu-id="9f512-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="9f512-104">Dynamics 365 Customer Insights ponuja API-je za izdelavo lastnih aplikacij, ki temeljijo na vaših podatkih v storitvi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9f512-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9f512-105">Podrobnosti o teh API-jih so navedene pri [sklicu za API-je za Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="9f512-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="9f512-106">Vključujejo dodatne informacije o postopkih, parametrih in odzivih.</span><span class="sxs-lookup"><span data-stu-id="9f512-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="9f512-107">Ta članek vas pomaga pri dostopu do API-jev za Customer Insights, ustvarjanju registracije aplikacije Azure in začetku uporabe razpoložljivih odjemalskih knjižnic.</span><span class="sxs-lookup"><span data-stu-id="9f512-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="9f512-108">Začetek uporabe API-jev za Customer Insights</span><span class="sxs-lookup"><span data-stu-id="9f512-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="9f512-109">[Vpišite se](https://home.ci.ai.dynamics.com) v aplikacijo Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9f512-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="9f512-110">Če še nimate naročnine, [se prijavite za preskusno različico aplikacije Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="9f512-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="9f512-111">Če želite omogočiti API-je v okolju Customer Insights, izberite **Skrbnik** > **Dovoljenja**.</span><span class="sxs-lookup"><span data-stu-id="9f512-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="9f512-112">Za to boste potrebovali skrbniška dovoljenja.</span><span class="sxs-lookup"><span data-stu-id="9f512-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="9f512-113">Izberite zavihek **API-ji** in izberite gumb **Omogoči**.</span><span class="sxs-lookup"><span data-stu-id="9f512-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="9f512-114">Z omogočanjem API-jev se ustvari primarni in sekundarni naročniški ključ za vaš primerek, ki se uporablja v zahtevah API-ja.</span><span class="sxs-lookup"><span data-stu-id="9f512-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="9f512-115">Ključe lahko znova ustvarite tako, da izberete **Znova ustvari primarnega** ali **Znova ustvari sekundarnega** v razdelku **Skrbnik** > **Dovoljenja** > **API-ji**.</span><span class="sxs-lookup"><span data-stu-id="9f512-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Omogočite API-je za Customer Insights":::

1. <span data-ttu-id="9f512-117">Izberite **Raziskovanje API-jev**, da [preizkusite API-je](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="9f512-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="9f512-118">Izberite postopek API-ja in izberite **Preskusi**.</span><span class="sxs-lookup"><span data-stu-id="9f512-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="9f512-119">V stranskem podoknu nastavite vrednost v spustnem meniju **Avtorizacija** na **implicitno**.</span><span class="sxs-lookup"><span data-stu-id="9f512-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="9f512-120">Pri glavi `Authorization` se doda nosilni žeton.</span><span class="sxs-lookup"><span data-stu-id="9f512-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="9f512-121">Vaš naročniški ključ bo samodejno izpolnjen.</span><span class="sxs-lookup"><span data-stu-id="9f512-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="9f512-122">Po želji dodajte vse potrebne parametre poizvedbe.</span><span class="sxs-lookup"><span data-stu-id="9f512-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="9f512-123">Pomaknite se na dno stranskega podokna in izberite **Pošlji**.</span><span class="sxs-lookup"><span data-stu-id="9f512-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="9f512-124">Odgovor HTTP se bo kmalu prikazal spodaj.</span><span class="sxs-lookup"><span data-stu-id="9f512-124">The HTTP response will soon appear below.</span></span>


   :::image type="content" source="media/try-apis.gif" alt-text="Animirani gif, ki prikazuje, kako izbrati test API-jev.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="9f512-126">Ustvarjanje registracije nove aplikacije v portalu Azure</span><span class="sxs-lookup"><span data-stu-id="9f512-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="9f512-127">Ti koraki vam pomagajo začeti uporabljati API-je za Customer Insights v aplikaciji Azure z uporabo dodeljenih dovoljenj.</span><span class="sxs-lookup"><span data-stu-id="9f512-127">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="9f512-128">Najprej se prepričajte, da ste zaključili [razdelek za začetek](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="9f512-128">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="9f512-129">Vpišite se v [portal Azure](https://portal.azure.com) z računom, ki lahko dostopa do podatkov Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9f512-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="9f512-130">Na levi izberite **Registracije aplikacij**.</span><span class="sxs-lookup"><span data-stu-id="9f512-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="9f512-131">Izberite **Nova registracija** ter navedite ime aplikacije in izberite vrsto računa.</span><span class="sxs-lookup"><span data-stu-id="9f512-131">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="9f512-132">Lahko tudi dodate URL za preusmeritev.</span><span class="sxs-lookup"><span data-stu-id="9f512-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="9f512-133">http://localhost zadostuje za razvoj aplikacije v vašem lokalnem računalniku.</span><span class="sxs-lookup"><span data-stu-id="9f512-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="9f512-134">V razdelku za registracijo nove aplikacije izberite **Dovoljenja za API**.</span><span class="sxs-lookup"><span data-stu-id="9f512-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Animirani gif za nastavitev dovoljenja za API pri registraciji aplikacije.":::

1. <span data-ttu-id="9f512-136">Izberite **Dodaj dovoljenje** in zatem **Customer Insights** v stranskem podoknu.</span><span class="sxs-lookup"><span data-stu-id="9f512-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="9f512-137">Za možnost **Vrsta dovoljenja** izberite **Dodeljena dovoljenja** in izberite dovoljenje **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="9f512-137">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="9f512-138">Izberite **Dodaj dovoljenja**.</span><span class="sxs-lookup"><span data-stu-id="9f512-138">Select **Add permissions**.</span></span> <span data-ttu-id="9f512-139">Če morate do API-ja dostopati brez vpisa uporabnika, preberite razdelek [Dovoljenja aplikacij za povezovanje med strežniki](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="9f512-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="9f512-140">Izberite **Podeli soglasje skrbnika za ...**, da dokončate registracijo aplikacije.</span><span class="sxs-lookup"><span data-stu-id="9f512-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="9f512-141">ID aplikacije/odjemalca lahko uporabite za registracijo te aplikacije v knjižnici za preverjanje pristnosti Microsoft Authentication Library (MSAL), da prejmete nosilni žeton, ki ga z vašo zahtevo pošljete v API.</span><span class="sxs-lookup"><span data-stu-id="9f512-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Animirani gif za odobritev soglasja skrbnika.":::

<span data-ttu-id="9f512-143">Za več informacij o knjižnici MSAL glejte [Pregled knjižnice Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="9f512-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="9f512-144">Če želite več informacij o registraciji aplikacij v storitvi Azure, glejte razdelek [Nova izkušnja pri registraciji aplikacije portala Azure](/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="9f512-144">For more information about app registration in Azure, see [The new Azure portal app registration experience](/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="9f512-145">Za informacije o uporabi API-jev pri naših odjemalskih knjižnicah glejte [Odjemalske knjižnice Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="9f512-145">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="9f512-146">Dovoljenja aplikacij za povezovanje med strežniki</span><span class="sxs-lookup"><span data-stu-id="9f512-146">Server-to-server application permissions</span></span>

<span data-ttu-id="9f512-147">[Razdelek za registracijo aplikacije](#create-a-new-app-registration-in-the-azure-portal) opisuje, kako registrirati aplikacijo, ki za preverjanje pristnosti od uporabnika zahteva vpis.</span><span class="sxs-lookup"><span data-stu-id="9f512-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="9f512-148">Naučite se ustvariti registracijo aplikacije, ki ne potrebuje interakcije uporabnika in jo je mogoče zagnati v strežniku.</span><span class="sxs-lookup"><span data-stu-id="9f512-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="9f512-149">Pri registraciji aplikacije v portalu Azure izberite **Dovoljenja za API**.</span><span class="sxs-lookup"><span data-stu-id="9f512-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="9f512-150">Izberite **Dodajanje dovoljenja**.</span><span class="sxs-lookup"><span data-stu-id="9f512-150">Select **Add a permission**.</span></span> 

1. <span data-ttu-id="9f512-151">Izberite zavihek **API-ji, ki jih uporablja organizacija** in s seznama izberite **Dynamics 365 AI za Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="9f512-151">Select the **APIs my organization uses** tab and choose **Dynamics 365 AI for Customer Insights** from the list.</span></span> 

1. <span data-ttu-id="9f512-152">Za možnost **Vrsta dovoljenja** izberite **Dovoljenja aplikacije** in izberite dovoljenje **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="9f512-152">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="9f512-153">Izberite **Dodaj dovoljenja**.</span><span class="sxs-lookup"><span data-stu-id="9f512-153">Select **Add permissions**.</span></span>

1. <span data-ttu-id="9f512-154">Vrnite se v razdelek **Dovoljenja za API**, da registrirate aplikacijo.</span><span class="sxs-lookup"><span data-stu-id="9f512-154">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="9f512-155">Izberite **Podeli soglasje skrbnika za ...**, da dokončate registracijo aplikacije.</span><span class="sxs-lookup"><span data-stu-id="9f512-155">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Animirani gif za odobritev soglasja skrbnika.":::

1. <span data-ttu-id="9f512-157">Na koncu moramo še dodati ime registracije aplikacije kot uporabnik v storitvi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9f512-157">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="9f512-158">Odprite Customer Insights, izberite **Skrbnik** > **Dovoljenja** in izberite **Dodaj uporabnika**.</span><span class="sxs-lookup"><span data-stu-id="9f512-158">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="9f512-159">Poiščite ime registracije za svojo aplikacijo, izberite ga med rezultati iskanja in izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="9f512-159">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="9f512-160">Odjemalske knjižnice Customer Insights</span><span class="sxs-lookup"><span data-stu-id="9f512-160">Customer Insights client libraries</span></span>

<span data-ttu-id="9f512-161">Ta razdelek vam pomaga začeti uporabljati odjemalske knjižnice, ki so na voljo za API-je za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9f512-161">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="9f512-162">Vse izvorne kode knjižnice in vzorčne aplikacije najdete na [strani Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="9f512-162">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="9f512-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="9f512-163">C# NuGet</span></span>

<span data-ttu-id="9f512-164">Naučite se uporabljati odjemalske knjižnice C# storitve NuGet.org. Za več informacij o paketu NuGet glejte [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="9f512-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="9f512-165">Trenutno ta paket cilja na ogrodja netstandard2.0 in netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="9f512-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="9f512-166">Dodajanje odjemalske knjižnice C# v projekt C#</span><span class="sxs-lookup"><span data-stu-id="9f512-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="9f512-167">V storitvi Visual Studio odprite **upravitelja paketov NuGet** za svoj projekt.</span><span class="sxs-lookup"><span data-stu-id="9f512-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="9f512-168">Poiščite **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="9f512-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="9f512-169">Izberite **Namesti** za dodajanje paketa v projekt.</span><span class="sxs-lookup"><span data-stu-id="9f512-169">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="9f512-170">Ta ukaz lahko zaženete tudi v **konzoli upravitelja paketov NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="9f512-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Dodajte paket NuGet v projekt Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="9f512-172">Uporaba odjemalske knjižnice C#</span><span class="sxs-lookup"><span data-stu-id="9f512-172">Use the C# client library</span></span>

1. <span data-ttu-id="9f512-173">Uporabite knjižnico [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview), da prejmete `AccessToken` z uporabo obstoječe [registracije aplikacije Azure](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="9f512-173">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="9f512-174">Po uspešnem preverjanju pristnosti in pridobitvi žetona izdelajte novega oz. uporabite obstoječega odjemalca `HttpClient`, in sicer z dodatno **»avtorizacijo« DefaultRequestHeaders** nastavljeno na **Nosilec <access token>** in možnostjo **Ocp-Apim-Subscription-Key** nastavljeno na [**naročniški ključ** iz okolja Customer Insights](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="9f512-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="9f512-175">Ponastavite glavo **Avtorizacija**, kadar je to primerno.</span><span class="sxs-lookup"><span data-stu-id="9f512-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="9f512-176">Na primer, ko je žeton potekel.</span><span class="sxs-lookup"><span data-stu-id="9f512-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="9f512-177">Odjemalca `HttpClient` posredujte za pripravo odjemalca `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="9f512-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Vzorec odjemalca httpclient":::

1. <span data-ttu-id="9f512-179">Z odjemalcem prikličite »načine razširitve«, na primer `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="9f512-179">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="9f512-180">Če je zaželen dostop do temeljne možnosti `Microsoft.Rest.HttpOperationResponse`, uporabite »načine sporočil http«, na primer `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="9f512-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="9f512-181">Vrsta odziva bo verjetno `object`, ker lahko ta način vrne več vrst (na primer `IList<InstanceInfo>` in `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="9f512-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="9f512-182">Če želite preveriti vrsto vrnitve, lahko predmete varno pretvorite v vrste odzivov, določene na [strani s podrobnostmi o API-ju](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) za ta postopek.</span><span class="sxs-lookup"><span data-stu-id="9f512-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="9f512-183">Če potrebujete več informacij o zahtevi, uporabite **načine sporočil http** za dostop do predmeta neobdelanega odziva.</span><span class="sxs-lookup"><span data-stu-id="9f512-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="9f512-184">Paket NodeJS</span><span class="sxs-lookup"><span data-stu-id="9f512-184">NodeJS package</span></span>

<span data-ttu-id="9f512-185">Uporabite odjemalske knjižnice NodeJS, ki so na voljo v programski opremi NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="9f512-185">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="9f512-186">Paket Python</span><span class="sxs-lookup"><span data-stu-id="9f512-186">Python package</span></span>

<span data-ttu-id="9f512-187">Uporabite odjemalske knjižnice Python, ki so na voljo v programski opremi PyPi: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="9f512-187">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
