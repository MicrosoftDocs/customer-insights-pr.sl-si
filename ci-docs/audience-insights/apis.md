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
ms.openlocfilehash: 7201ed9e5315d73e6b9c25b4bc4c4e4ed839a215
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732284"
---
# <a name="work-with-customer-insights-apis"></a>Delo z API-ji za Customer Insights

Dynamics 365 Customer Insights ponuja API-je za izdelavo lastnih aplikacij na podlagi vaših podatkov v storitvi Customer Insights.

> [!IMPORTANT]
> Podrobnosti o API-jih najdete v [sklicu na API-je v storitvi Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Vključujejo dodatne informacije o postopkih, parametrih in odzivih.

V tem članku je opisano, kako dostopati do API-jev storitve Customer Insights, se registrirati v aplikaciji Azure in začeti z razpoložljivimi odjemalskimi knjižnicami.

## <a name="get-started-trying-the-customer-insights-apis"></a>Začetek uporabe API-jev za Customer Insights

1. [Vpišite se](https://home.ci.ai.dynamics.com) v aplikacijo Customer Insights. Če še nimate naročnine, [se prijavite za preskusno različico aplikacije Customer Insights](https://aka.ms/tryci).

1. Če želite omogočiti API-je v okolju Customer Insights, izberite **Skrbnik** > **Dovoljenja**. Za to boste potrebovali skrbniška dovoljenja.

1. Izberite zavihek **API-ji** in izberite gumb **Omogoči**.    
 
   Z omogočanjem API-jev se ustvari primarni in sekundarni naročniški ključ za vaš primerek, ki se uporablja v zahtevah API-ja. Ključe lahko znova ustvarite tako, da izberete **Znova ustvari primarnega** ali **Znova ustvari sekundarnega** v razdelku **Skrbnik** > **Dovoljenja** > **API-ji**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Omogočite storitev Customer Insights za API-je.":::

1. Izberite **Raziskovanje API-jev**, da [preizkusite API-je](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Izberite postopek API-ja in izberite **Preskusi**.

1. Vrednost v stranskem podoknu, in sicer v spustnem meniju **Pooblastilo**, označite z **implicitno**. Glava `Authorization` je dodana z nosilnim žetonom. Vaš naročniški ključ bo samodejno izpolnjen.
  
1. Po želji dodajte vse potrebne parametre poizvedbe.

1. Pomaknite se na dno stranskega podokna in izberite **Pošlji**.

Odgovor HTTP se bo kmalu prikazal spodaj.

   :::image type="content" source="media/try-apis.gif" alt-text="Navodila za preizkušanje API-jev.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Ustvarjanje registracije nove aplikacije v portalu Azure

Ti koraki vam bodo omogočili enostavnejšo prvo uporabo API-jev storitve Customer Insights v aplikaciji Azure z dodeljenimi dovoljenji. Najprej zaključite [razdelek Začetek](#get-started-trying-the-customer-insights-apis).

1. Vpišite se v [portal Azure](https://portal.azure.com) z računom, ki lahko dostopa do podatkov Customer Insights.

1. Na levi izberite **Registracije aplikacij**.

1. Izberite možnost **Nova registracija**, navedite ime aplikacije in izberite vrsto računa.
 
   Lahko tudi dodate URL za preusmeritev. http://localhost zadostuje za razvoj aplikacije v vašem lokalnem računalniku.

1. V razdelku za registracijo nove aplikacije izberite **Dovoljenja za API**.

   :::image type="content" source="media/app-registration-1.gif" alt-text="Kako ob registraciji programa nastaviti dovoljenja za API.":::

1. Izberite **Dodaj dovoljenje** in zatem **Customer Insights** v stranskem podoknu.

1. Za **Vrsto dovoljenja** izberite **Dodeljena dovoljenja**, nato pa dovoljenje **poosebljanje_uporabnika**.

1. Izberite **Dodaj dovoljenja**. Če morate do API-ja dostopati brez vpisa uporabnika, preberite razdelek [Dovoljenja aplikacij za povezovanje med strežniki](#server-to-server-application-permissions).

1. Izberite **Podeli soglasje skrbnika za ...**, da dokončate registracijo aplikacije.

ID aplikacije/odjemalca lahko uporabite za registracijo te aplikacije v knjižnici za preverjanje pristnosti Microsoft Authentication Library (MSAL), da prejmete nosilni žeton, ki ga z vašo zahtevo pošljete v API.

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Kako izdati soglasje skrbnika.":::

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

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Kako izdati soglasje skrbnika.":::

1. Na koncu moramo še dodati ime registracije aplikacije kot uporabnik v storitvi Customer Insights.  
   
   Odprite Customer Insights, izberite **Skrbnik** > **Dovoljenja** in izberite **Dodaj uporabnika**.

1. Poiščite ime registracije za svojo aplikacijo, izberite ga med rezultati iskanja in izberite **Shrani**.

## <a name="customer-insights-client-libraries"></a>Odjemalske knjižnice Customer Insights

Ta razdelek vam pomaga začeti uporabljati odjemalske knjižnice, ki so na voljo za API-je za Customer Insights. Vse izvorne kode knjižnice in vzorčne aplikacije najdete na [strani Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Naučite se, kako začeti uporabljati odjemalske knjižnice C# iz NuGet.org. Za več informacij o paketu NuGet glejte [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Trenutno ta paket cilja na ogrodja netstandard2.0 in netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Dodajanje odjemalske knjižnice C# v projekt C#

1. V Visual Studio odprite **NuGet Upravitelj paketov** za vaš projekt.

1. Poiščite **Microsoft.Dynamics.CustomerInsights.Api**.

1. Izberite **Namesti** za dodajanje paketa v projekt.
 
   Druga možnost je, da zaženete ta ukaz v **NuGet Konzola upravitelja paketov** :`Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Dodajte paket NuGet v projekt Visual Studio.":::

#### <a name="use-the-c-client-library"></a>Uporaba odjemalske knjižnice C#

1. Uporabite knjižnico [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview), da prejmete `AccessToken` z uporabo obstoječe [registracije aplikacije Azure](#create-a-new-app-registration-in-the-azure-portal).

1. Po uspešni avtentikaciji in pridobitvi žetona sestavite nov ali uporabite obstoječega`HttpClient` z dodatnim **DefaultRequestHeaders "Avtorizacija"** nastavljena **Nosilec "žeton za dostop"** in **Ocp-Apim-Naročniški ključ** nastavljeno na [**naročniški ključ** iz vašega okolja Customer Insights](#get-started-trying-the-customer-insights-apis).   
 
   Ponastavite glavo **Avtorizacija**, kadar je to primerno. Na primer, ko je žeton potekel.

1. Odjemalca `HttpClient` posredujte za pripravo odjemalca `CustomerInsights`.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Vzorec odjemalca http.":::

1. Z odjemalcem prikličite »načine razširitve« – na primer `GetAllInstancesAsync`. Če je zaželen dostop do temeljne možnosti `Microsoft.Rest.HttpOperationResponse`, uporabite »načine sporočil http« — na primer `GetAllInstancesWithHttpMessagesAsync`.

1. Vrsta odziva bo verjetno `object`, ker lahko ta način vrne več vrst (na primer `IList<InstanceInfo>` in `ApiErrorResult`). Če želite preveriti vrsto vrnitve, lahko predmete varno pretvorite v vrste odzivov, določene na [strani s podrobnostmi o API-ju](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) za ta postopek.    
   
   Če potrebujete več informacij o zahtevi, uporabite **načine sporočil http** za dostop do predmeta neobdelanega odziva.

### <a name="nodejs-package"></a>Paket NodeJS

Uporabite odjemalske knjižnice NodeJS, ki so na voljo v programski opremi NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Paket Python

Uporabite odjemalske knjižnice Python, ki so na voljo v programski opremi PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE[footer-include](../includes/footer-banner.md)]
