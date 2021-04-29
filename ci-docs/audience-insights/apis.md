---
title: Delo z API-ji
description: Uporaba API-jev in razumevanje omejitev.
ms.date: 03/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 59161456914df84d7e72402ed1f5faf70a5119ba
ms.sourcegitcommit: a39e00a50ad3eda820fd756c5611081f0ca04662
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/09/2021
ms.locfileid: "5873682"
---
# <a name="work-with-customer-insights-apis"></a>Delo z API-ji za Customer Insights

Dynamics 365 Customer Insights ponuja API-je za izdelavo lastnih aplikacij, ki temeljijo na vaših podatkih v storitvi Customer Insights.

> [!IMPORTANT]
> Podrobnosti o teh API-jih so navedene pri [sklicu za API-je za Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Vključujejo dodatne informacije o postopkih, parametrih in odzivih.

Ta članek vas pomaga pri dostopu do API-jev za Customer Insights, ustvarjanju registracije aplikacije Azure in začetku uporabe razpoložljivih odjemalskih knjižnic.

## <a name="get-started-trying-the-customer-insights-apis"></a>Začetek uporabe API-jev za Customer Insights

1. [Vpišite se](https://home.ci.ai.dynamics.com) v aplikacijo Customer Insights. Če še nimate naročnine, [se prijavite za preskusno različico aplikacije Customer Insights](https://aka.ms/tryci).

1. Če želite omogočiti API-je v okolju Customer Insights, izberite **Skrbnik** > **Dovoljenja**. Za to boste potrebovali skrbniška dovoljenja.

1. Izberite zavihek **API-ji** in izberite gumb **Omogoči**.    
   Z omogočanjem API-jev se ustvari primarni in sekundarni naročniški ključ za vaš primerek, ki se uporablja v zahtevah API-ja. Ključe lahko znova ustvarite tako, da izberete **Znova ustvari primarnega** ali **Znova ustvari sekundarnega** v razdelku **Skrbnik** > **Dovoljenja** > **API-ji**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Omogočite API-je za Customer Insights":::

1. Izberite **Raziskovanje API-jev**, da [preizkusite API-je](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Izberite postopek API-ja in izberite **Preskusi**.

1. V stranskem podoknu nastavite vrednost v spustnem meniju **Avtorizacija** na **implicitno**. Pri glavi `Authorization` se doda nosilni žeton. Vaš naročniški ključ bo samodejno izpolnjen.
  
1. Po želji dodajte vse potrebne parametre poizvedbe.

1. Pomaknite se na dno stranskega podokna in izberite **Pošlji**.

Odgovor HTTP se bo kmalu prikazal spodaj.


   :::image type="content" source="media/try-apis.gif" alt-text="Animirani gif, ki prikazuje, kako izbrati test API-jev.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Ustvarjanje registracije nove aplikacije v portalu Azure

Ti koraki vam pomagajo začeti uporabljati API-je za Customer Insights v aplikaciji Azure z uporabo dodeljenih dovoljenj. Najprej se prepričajte, da ste zaključili [razdelek za začetek](#get-started-trying-the-customer-insights-apis).

1. Vpišite se v [portal Azure](https://portal.azure.com) z računom, ki lahko dostopa do podatkov Customer Insights.

1. Na levi izberite **Registracije aplikacij**.

1. Izberite **Nova registracija** ter navedite ime aplikacije in izberite vrsto računa.
   Lahko tudi dodate URL za preusmeritev. http://localhost zadostuje za razvoj aplikacije v vašem lokalnem računalniku.

1. V razdelku za registracijo nove aplikacije izberite **Dovoljenja za API**.

   :::image type="content" source="media/app-registration-1.gif" alt-text="Animirani gif za nastavitev dovoljenja za API pri registraciji aplikacije.":::

1. Izberite **Dodaj dovoljenje** in zatem **Customer Insights** v stranskem podoknu.

1. Za možnost **Vrsta dovoljenja** izberite **Dodeljena dovoljenja** in izberite dovoljenje **user_impersonation**.

1. Izberite **Dodaj dovoljenja**. Če morate do API-ja dostopati brez vpisa uporabnika, preberite razdelek [Dovoljenja aplikacij za povezovanje med strežniki](#server-to-server-application-permissions).

1. Izberite **Podeli soglasje skrbnika za ...**, da dokončate registracijo aplikacije.

ID aplikacije/odjemalca lahko uporabite za registracijo te aplikacije v knjižnici za preverjanje pristnosti Microsoft Authentication Library (MSAL), da prejmete nosilni žeton, ki ga z vašo zahtevo pošljete v API.

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Animirani gif za odobritev soglasja skrbnika.":::

Za več informacij o knjižnici MSAL glejte [Pregled knjižnice Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).

Če želite več informacij o registraciji aplikacij v storitvi Azure, glejte razdelek [Nova izkušnja pri registraciji aplikacije portala Azure](/azure/active-directory/develop/app-registration-portal-training-guide).

Za informacije o uporabi API-jev pri naših odjemalskih knjižnicah glejte [Odjemalske knjižnice Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Dovoljenja aplikacij za povezovanje med strežniki

[Razdelek za registracijo aplikacije](#create-a-new-app-registration-in-the-azure-portal) opisuje, kako registrirati aplikacijo, ki za preverjanje pristnosti od uporabnika zahteva vpis. Naučite se ustvariti registracijo aplikacije, ki ne potrebuje interakcije uporabnika in jo je mogoče zagnati v strežniku.

1. Pri registraciji aplikacije v portalu Azure izberite **Dovoljenja za API**.

1. Izberite **Dodaj dovoljenje** in zatem **Customer Insights** v stranskem podoknu.

1. Za možnost **Vrsta dovoljenja** izberite **Dovoljenja aplikacije** in izberite dovoljenje **CustomerInsights.Api.All**.

1. Izberite **Dodaj dovoljenja**.

1. Če želite podati skrbniško soglasje za to dovoljenje aplikacije, morate dodati glavno ime storitve.

   1. Namestite modul Azure Active Directory (AD) PowerShell: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. Povežite račun AD: `Connect-AzureAD -TenantId <your tenant id>`. ID najemnika lahko najdete v razdelku **Pregled** > **Azure Active Directory**.
   1. Zaženite naslednji ukaz, da dodate glavno ime storitve Azure AD: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"`. Parameter AppId se nanaša na aplikacijo API-ja za Customer Insights.

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Vzorec glavnega imena storitve":::

1. Vrnite se v razdelek **Dovoljenja za API**, da registrirate aplikacijo.

1. Izberite **Podeli soglasje skrbnika za ...**, da dokončate registracijo aplikacije.

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Animirani gif za odobritev soglasja skrbnika.":::

1. Na koncu moramo še dodati ime registracije aplikacije kot uporabnik v storitvi Customer Insights.    
   Odprite Customer Insights, izberite **Skrbnik** > **Dovoljenja** in izberite **Dodaj uporabnika**.

1. Poiščite ime registracije za svojo aplikacijo, izberite ga med rezultati iskanja in izberite **Shrani**.

## <a name="customer-insights-client-libraries"></a>Odjemalske knjižnice Customer Insights

Ta razdelek vam pomaga začeti uporabljati odjemalske knjižnice, ki so na voljo za API-je za Customer Insights. Vse izvorne kode knjižnice in vzorčne aplikacije najdete na [strani Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Naučite se uporabljati odjemalske knjižnice C# storitve NuGet.org. Za več informacij o paketu NuGet glejte [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Trenutno ta paket cilja na ogrodja netstandard2.0 in netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Dodajanje odjemalske knjižnice C# v projekt C#

1. V storitvi Visual Studio odprite **upravitelja paketov NuGet** za svoj projekt.

1. Poiščite **Microsoft.Dynamics.CustomerInsights.Api**.

1. Izberite **Namesti** za dodajanje paketa v projekt.
   Ta ukaz lahko zaženete tudi v **konzoli upravitelja paketov NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Dodajte paket NuGet v projekt Visual Studio":::

#### <a name="use-the-c-client-library"></a>Uporaba odjemalske knjižnice C#

1. Uporabite knjižnico [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview), da prejmete `AccessToken` z uporabo obstoječe [registracije aplikacije Azure](#create-a-new-app-registration-in-the-azure-portal).

1. Po uspešnem preverjanju pristnosti in pridobitvi žetona izdelajte novega oz. uporabite obstoječega odjemalca `HttpClient`, in sicer z dodatno **»avtorizacijo« DefaultRequestHeaders** nastavljeno na **Nosilec <access token>** in možnostjo **Ocp-Apim-Subscription-Key** nastavljeno na [**naročniški ključ** iz okolja Customer Insights](#get-started-trying-the-customer-insights-apis).    
   Ponastavite glavo **Avtorizacija**, kadar je to primerno. Na primer, ko je žeton potekel.

1. Odjemalca `HttpClient` posredujte za pripravo odjemalca `CustomerInsights`.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Vzorec odjemalca httpclient":::

1. Z odjemalcem prikličite »načine razširitve«, na primer `GetAllInstancesAsync`. Če je zaželen dostop do temeljne možnosti `Microsoft.Rest.HttpOperationResponse`, uporabite »načine sporočil http«, na primer `GetAllInstancesWithHttpMessagesAsync`.

1. Vrsta odziva bo verjetno `object`, ker lahko ta način vrne več vrst (na primer `IList<InstanceInfo>` in `ApiErrorResult`). Če želite preveriti vrsto vrnitve, lahko predmete varno pretvorite v vrste odzivov, določene na [strani s podrobnostmi o API-ju](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) za ta postopek.    
   Če potrebujete več informacij o zahtevi, uporabite **načine sporočil http** za dostop do predmeta neobdelanega odziva.

### <a name="nodejs-package"></a>Paket NodeJS

Uporabite odjemalske knjižnice NodeJS, ki so na voljo v programski opremi NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Paket Python

Uporabite odjemalske knjižnice Python, ki so na voljo v programski opremi PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE[footer-include](../includes/footer-banner.md)]
