---
title: Delo z API-ji
description: Uporaba API-jev in razumevanje omejitev.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: ecc8bb3dbec1d4583c4bf2a58058145343945299
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643267"
---
# <a name="work-with-customer-insights-apis"></a>Delo z API-ji za Customer Insights

Dynamics 365 Customer Insights vam zagotavlja API-je za izgradnjo lastnih aplikacij, in sicer na podlagi vaših podatkov v storitvi Customer Insights.

> [!IMPORTANT]
> Podrobnosti o API-jih najdete v [sklicu na API-je v storitvi Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Vključujejo dodatne informacije o postopkih, parametrih in odzivih.

V tem članku je opisano, kako dostopati do API-jev storitve Customer Insights, se registrirati v aplikaciji Azure in začeti z razpoložljivimi odjemalskimi knjižnicami.

## <a name="get-started-trying-the-customer-insights-apis"></a>Začetek uporabe API-jev za Customer Insights

1. [Vpišite se](https://home.ci.ai.dynamics.com) v aplikacijo Customer Insights. Če še nimate naročnine, [se prijavite za preskusno različico aplikacije Customer Insights](https://aka.ms/tryci).

1. Če želite omogočiti API-je v okolju Customer Insights, izberite **Skrbnik** > **Dovoljenja**. Za to boste potrebovali skrbniška dovoljenja.

1. Izberite zavihek **API-ji** in izberite gumb **Omogoči**.    
 
   Z omogočanjem API-jev se ustvari primarni in sekundarni naročniški ključ za vaš primerek, ki se uporablja v zahtevah API-ja. Ključe lahko znova ustvarite tako, da izberete **Znova ustvari primarnega** ali **Znova ustvari sekundarnega** v razdelku **Skrbnik** > **Dovoljenja** > **API-ji**.

<!--  :::image type="content" source="media/enable-apis.gif" alt-text="Enable Customer Insights APIs."::: -->

1. Izberite **Raziskovanje API-jev**, da [preizkusite API-je](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Izberite postopek API-ja in izberite **Preskusi**.

1. Vrednost v stranskem podoknu, in sicer v spustnem meniju **Pooblastilo**, označite z **implicitno**. Glava `Authorization` je dodana z nosilnim žetonom. Vaš naročniški ključ bo samodejno izpolnjen.
  
1. Po želji dodajte vse potrebne parametre poizvedbe.

1. Pomaknite se na dno stranskega podokna in izberite **Pošlji**.

Odgovor HTTP se bo kmalu prikazal spodaj.

<!--   :::image type="content" source="media/try-apis.gif" alt-text="How to test the APIs."::: -->

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Ustvarjanje registracije nove aplikacije v portalu Azure

Ti koraki vam bodo omogočili enostavnejšo prvo uporabo API-jev storitve Customer Insights v aplikaciji Azure z dodeljenimi dovoljenji. Najprej zaključite [razdelek Začetek](#get-started-trying-the-customer-insights-apis).

1. Vpišite se v [portal Azure](https://portal.azure.com) z računom, ki lahko dostopa do podatkov Customer Insights.

1. Na levi izberite **Registracije aplikacij**.

1. Izberite možnost **Nova registracija**, navedite ime aplikacije in izberite vrsto računa.
 
   Lahko tudi dodate URL za preusmeritev. http://localhost zadostuje za razvoj aplikacije v vašem lokalnem računalniku.

1. V razdelku za registracijo nove aplikacije izberite **Dovoljenja za API**.

<!--   :::image type="content" source="media/app-registration-1.gif" alt-text="How to set API permissions in App registration."::: -->

1. Izberite **Dodaj dovoljenje** in zatem **Customer Insights** v stranskem podoknu.

1. Za **Vrsto dovoljenja** izberite **Dodeljena dovoljenja**, nato pa dovoljenje **poosebljanje_uporabnika**.

1. Izberite **Dodaj dovoljenja**. Če morate do API-ja dostopati brez vpisa uporabnika, preberite razdelek [Dovoljenja aplikacij za povezovanje med strežniki](#server-to-server-application-permissions).

1. Izberite **Podeli soglasje skrbnika za ...**, da dokončate registracijo aplikacije.

ID aplikacije/odjemalca lahko uporabite za registracijo te aplikacije v knjižnici za preverjanje pristnosti Microsoft Authentication Library (MSAL), da prejmete nosilni žeton, ki ga z vašo zahtevo pošljete v API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Za več informacij o knjižnici MSAL glejte [Pregled knjižnice Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).

Za več informacij o registraciji programa v storitvi Azure si oglejte možnost [Registracija programa](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).

Za informacije o uporabi API-jev v naših odjemalskih knjižnicah si oglejte [odjemalske knjižnice Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Dovoljenja aplikacij za povezovanje med strežniki

[Razdelek za registracijo aplikacije](#create-a-new-app-registration-in-the-azure-portal) opisuje, kako registrirati aplikacijo, ki za preverjanje pristnosti od uporabnika zahteva vpis. Naučite se ustvariti registracijo aplikacije, ki ne potrebuje interakcije uporabnika in jo je mogoče zagnati v strežniku.

1. Pri registraciji aplikacije v portalu Azure izberite **Dovoljenja za API**.

1. Izberite **Dodajanje dovoljenja**. 

1. Izberite zavihek **API-ji, ki jih uporablja organizacija** in s seznama izberite **Dynamics 365 AI za Customer Insights**. 

1. Za **Vrsto dovoljenja** izberite **Dodeljena dovoljenja**, nato pa dovoljenje **poosebljanje_uporabnika**.

1. Izberite **Dodaj dovoljenja**.

1. Vrnite se v razdelek **Dovoljenja za API**, da registrirate aplikacijo.

1. Izberite **Podeli soglasje skrbnika za ...**, da dokončate registracijo aplikacije.

 <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

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

 <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Uporaba odjemalske knjižnice C#

1. Uporabite knjižnico [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview), da prejmete `AccessToken` z uporabo obstoječe [registracije aplikacije Azure](#create-a-new-app-registration-in-the-azure-portal).

1. Po uspešni avtentikaciji in pridobitvi žetona sestavite nov ali uporabite obstoječega`HttpClient` z dodatnim **DefaultRequestHeaders "Avtorizacija"** nastavljena **Nosilec "žeton za dostop"** in **Ocp-Apim-Naročniški ključ** nastavljeno na [**naročniški ključ** iz vašega okolja Customer Insights](#get-started-trying-the-customer-insights-apis).   
 
   Ponastavite glavo **Avtorizacija**, kadar je to primerno. Na primer, ko je žeton potekel.

1. Odjemalca `HttpClient` posredujte za pripravo odjemalca `CustomerInsights`.

<!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Z odjemalcem prikličite »načine razširitve« – na primer `GetAllInstancesAsync`. Če je zaželen dostop do temeljne možnosti `Microsoft.Rest.HttpOperationResponse`, uporabite »načine sporočil http« — na primer `GetAllInstancesWithHttpMessagesAsync`.

1. Vrsta odziva bo verjetno `object`, ker lahko ta način vrne več vrst (na primer `IList<InstanceInfo>` in `ApiErrorResult`). Če želite preveriti vrsto vrnitve, lahko predmete varno pretvorite v vrste odzivov, določene na [strani s podrobnostmi o API-ju](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) za ta postopek.    
   
   Če potrebujete več informacij o zahtevi, uporabite **načine sporočil http** za dostop do predmeta neobdelanega odziva.

### <a name="nodejs-package"></a>Paket NodeJS

Uporabite odjemalske knjižnice NodeJS, ki so na voljo v programski opremi NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Paket Python

Uporabite odjemalske knjižnice Python, ki so na voljo v programski opremi PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
