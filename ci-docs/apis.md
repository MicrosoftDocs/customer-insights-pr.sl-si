---
title: Delo z API-ji za Customer Insights
description: Uporaba API-jev in razumevanje omejitev.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387360"
---
# <a name="work-with-customer-insights-apis"></a>Delo z API-ji za Customer Insights

Dynamics 365 Customer Insights vam zagotavlja API-je za izgradnjo lastnih aplikacij, in sicer na podlagi vaših podatkov v storitvi Customer Insights.

> [!IMPORTANT]
> Podrobnosti o API-jih najdete v [sklicu na API-je v storitvi Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Vključujejo dodatne informacije o postopkih, parametrih in odzivih.

Preizkusite API-je Customer Insights, ustvarite registracijo aplikacije Azure in začnite uporabljati odjemalske knjižnice.

## <a name="get-started-trying-the-customer-insights-apis"></a>Začetek uporabe API-jev za Customer Insights

Omogočite API-je Customer Insights in jih preizkusite. Skrbnik Customer Insights mora omogočiti dostop API-ja do Customer Insights. Ko je dostop omogočen, lahko kateri koli uporabnik uporablja API z naročniškim ključem.

1. [Vpišite se](https://home.ci.ai.dynamics.com) v aplikacijo Customer Insights. Če še nimate naročnine, [se prijavite za preskusno različico aplikacije Customer Insights](https://aka.ms/tryci).

1. Pojdi do **skrbnik** > **Varnost** in izberite **API-ji** zavihek.

1. Če API dostop do okolja ni nastavljen, izberite **Omogoči** .

   Z omogočanjem API-jev se ustvari primarni in sekundarni naročniški ključ za vaš primerek, ki se uporablja v zahtevah API-ja. Za regeneracijo ključev izberite **Regeneriraj primarno** oz **Regeneriraj sekundarno** na **API-ji** zavihek.

1. Izberite [**Raziščite naše API-je**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) da preizkusite API-je.

1. Poiščite in izberite operacijo API in izberite **Poskusi**.

   :::image type="content" source="media/try-api.png" alt-text="Navodila za preizkušanje API-jev.":::

1. Vrednost v stranskem podoknu, in sicer v spustnem meniju **Pooblastilo**, označite z **implicitno**. Glava `Authorization` je dodana z nosilnim žetonom. Vaš naročniški ključ se samodejno izpolni.
  
1. Po želji dodajte vse potrebne parametre poizvedbe.

1. Pomaknite se na dno stranskega podokna in izberite **Pošlji**.

   Odgovor HTTP se prikaže na dnu podokna.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Ustvarjanje registracije nove aplikacije v portalu Azure

Ustvari novo [registracija aplikacije](/graph/auth-register-app-v2) za uporabo API-jev Customer Insights v aplikaciji Azure z uporabo delegiranih dovoljenj.

1. Dokončaj [Oddelek za začetek](#get-started-trying-the-customer-insights-apis).

1. Vpišite se v [portal Azure](https://portal.azure.com) z računom, ki lahko dostopa do podatkov Customer Insights.

1. Poiščite in nato izberite **Registracije aplikacij**.

1. Izberite možnost **Nova registracija**, navedite ime aplikacije in izberite vrsto računa.

   Lahko tudi dodate URL za preusmeritev. http://localhost zadostuje za razvoj aplikacije v vašem lokalnem računalniku.

1. Izberite **Registriraj**.

1. V razdelku za registracijo nove aplikacije izberite **Dovoljenja za API**.

1. Izberite **Dodajte dovoljenje** in izberite **Dynamics 365 AI for Customer Insights** v stranskem podoknu.

1. Za **Vrsto dovoljenja** izberite **Dodeljena dovoljenja**, nato pa dovoljenje **poosebljanje_uporabnika**.

1. Izberite **Dodaj dovoljenja**.

1. Izberite **Podeli soglasje skrbnika za ...**, da dokončate registracijo aplikacije.

1. Za dostop do API-ja, ne da bi se uporabnik prijavil, pojdite na [Dovoljenja aplikacij med strežniki](#server-to-server-application-permissions).

Za registracijo te aplikacije lahko uporabite ID aplikacije/odjemalca pri [Microsoftova knjižnica za preverjanje pristnosti (MSAL)](/azure/active-directory/develop/msal-overview) za pridobitev nosilnega žetona, ki ga boste skupaj z zahtevo poslali API-ju.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Za informacije o uporabi API-jev v naših odjemalskih knjižnicah si oglejte [odjemalske knjižnice Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Dovoljenja aplikacij za povezovanje med strežniki

Ustvarite registracijo aplikacije, ki ne potrebuje interakcije uporabnika in jo je mogoče izvajati na strežniku.

1. Pri registraciji aplikacije v portalu Azure izberite **Dovoljenja za API**.

1. Izberite **Dodajanje dovoljenja**.

1. Izberite zavihek **API-ji, ki jih uporablja organizacija** in s seznama izberite **Dynamics 365 AI za Customer Insights**.

1. Za **Vrsto dovoljenja** izberite **Dodeljena dovoljenja**, nato pa dovoljenje **poosebljanje_uporabnika**.

1. Izberite **Dodaj dovoljenja**.

1. Vrnite se v razdelek **Dovoljenja za API**, da registrirate aplikacijo.

1. Izberite **Podeli soglasje skrbnika za ...**, da dokončate registracijo aplikacije.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Dodajte ime registracije aplikacije kot uporabnika v Customer Insights.

   1. Odprite Customer Insights, pojdite na **skrbnik** > **Varnost** in izberite **Dodajte uporabnike**.

   1. Poiščite ime registracije za svojo aplikacijo, izberite ga med rezultati iskanja in izberite **Shrani**.

## <a name="sample-queries"></a>Vzorčne poizvedbe

Za kratek seznam vzorčnih poizvedb OData za delo z API-ji glejte [Primeri poizvedb OData](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Odjemalske knjižnice Customer Insights

Začnite uporabljati odjemalske knjižnice, ki so na voljo za API-je Customer Insights. Vse izvorne kode knjižnice in vzorčne aplikacije najdete na [strani Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).

### <a name="c-nuget"></a>C# NuGet

Uporabite odjemalske knjižnice C# iz NuGet .org. Trenutno je paket namenjen okviroma netstandard2.0 in netcoreapp2.0. Za več informacij o NuGet paket, glej [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

#### <a name="add-the-c-client-library-to-a-c-project"></a>Dodajanje odjemalske knjižnice C# v projekt C#

1. V storitvi Visual Studio odprite **upravitelja paketov NuGet** za svoj projekt.

1. Poiščite **Microsoft.Dynamics.CustomerInsights.Api**.

1. Izberite **Namesti** za dodajanje paketa v projekt.

   Ta ukaz lahko zaženete tudi v **konzoli upravitelja paketov NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Uporaba odjemalske knjižnice C#

1. Uporabite knjižnico [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview), da prejmete `AccessToken` z uporabo obstoječe [registracije aplikacije Azure](#create-a-new-app-registration-in-the-azure-portal).

1. Po uspešnem preverjanju pristnosti in pridobitvi žetona sestavite novega ali uporabite obstoječega`HttpClient` z **DefaultRequestHeaders "Avtorizacija"** nastavljena **Nosilec "žeton za dostop"** in **Ocp-Apim-Subscription-Key** nastavite na [**naročniški ključ** iz vašega okolja Customer Insights](#get-started-trying-the-customer-insights-apis).   

   Ponastavite glavo **Avtorizacija**, kadar je to primerno. Na primer, ko je žeton potekel.

1. Odjemalca `HttpClient` posredujte za pripravo odjemalca `CustomerInsights`.

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Z odjemalcem prikličite »načine razširitve«, na primer `GetAllInstancesAsync`. Če dostop do osnovnega`Microsoft.Rest.HttpOperationResponse` je zaželeno, uporabite na primer "metode sporočil http",`GetAllInstancesWithHttpMessagesAsync`.

1. Odziv je verjeten`object` vrsta, ker lahko metoda vrne več vrst (npr.`IList<InstanceInfo>` in`ApiErrorResult`). Če želite preveriti vrnjeno vrsto, uporabite objekte v vrstah odgovorov, navedenih na [Stran s podrobnostmi API-ja](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) za to operacijo.

   Če potrebujete več informacij o zahtevi, uporabite **načine sporočil http** za dostop do predmeta neobdelanega odziva.

### <a name="nodejs-package"></a>Paket NodeJS

Uporabite odjemalske knjižnice NodeJS, ki so na voljo v programski opremi NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Paket Python

Uporabite odjemalske knjižnice Python, ki so na voljo v programski opremi PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
