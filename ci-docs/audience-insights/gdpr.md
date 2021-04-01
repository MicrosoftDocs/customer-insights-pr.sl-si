---
title: Zahteve posameznikov, na katere se nanašajo podatki, (DSR) v skladu z uredbo GDPR | Microsoftovo gradivo
description: Odgovorite na zahteve posameznikov, na katere se nanašajo podatki, za zmogljivost vpogledov v občinstvo Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9c453c9b416bff0e6362a8ccf7ff534f4efa1e00
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597531"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Zahteve posameznikov, na katere se nanašajo podatki, (DSR) v skladu z uredbo GDPR

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Odgovorite na zahteve posameznikov, na katere se nanašajo podatki, za izbris za zmogljivost vpogledov v občinstvo Dynamics 365 Customer Insights, v skladu z uredbo GDPR.

»Pravica do izbrisa« z odstranitvijo osebnih podatkov iz podatkov o strankah, ki jih ima organizacija, je ključna zaščita v Splošni uredbi o varstvu podatkov (GDPR). Odstranitev osebnih podatkov vključuje odstranitev vseh osebnih podatkov in sistemsko ustvarjenih dnevnikov, razen informacij iz dnevnika spremljanja sprememb.

### <a name="manage-data-subject-delete-requests"></a>Upravljanje zahtev posameznika, na katerega se nanašajo podatki, za izbris

Vpogledi v občinstvo nudijo naslednje izkušnje v izdelkih, s katerimi lahko izbrišete osebne podatke za določeno stranko ali uporabnika:

- **Upravljanje zahtev za izbris podatkov o strankah**: podatki o strankah v storitvi Customer Insights se uvozijo iz izvirnih virov podatkov zunaj storitve Customer Insights. Vse zahteve za izbris v skladu z uredbo GDPR morajo biti izvedene v izvirnem viru podatkov.
- **Upravljanje zahtev za izbris uporabniških podatkov storitve Customer Insights**: podatke za uporabnike je ustvaril Customer Insights. Vse zahteve za izbris v skladu z uredbo GDPR morajo biti izvedene v storitvi Customer Insights.

#### <a name="manage-delete-requests-for-customer-data"></a>Upravljanje zahtev za izbris podatkov o strankah

Skrbnik storitve Customer Insights lahko upošteva te korake, da odstrani podatke stranke, ki so bili izbrisani iz vira podatkov:

1. Vpis v storitev Dynamics 365 Customer Insights.
2. Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.
3. Za vsak vir podatkov na seznamu, ki vsebuje izbrisane podatke strank:
   1. Izberite možnost (...) in nato **Osveži**.
   2. Preverite stanje vira podatkov v razdelku **Stanje**. Kljukica pomeni, da je bila osvežitev uspešna. Opozorilni trikotnik pomeni, da je prišlo do napake. Če se prikaže opozorilni trikotnik, pošljite sporočilo na naslov D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Obravnava zahtev za izbris podatkov o strankah v skladu z uredbo GDPR](media/gdpr-data-sources.png "Obravnava zahtev za izbris podatkov o strankah v skladu z uredbo GDPR")

#### <a name="manage-delete-requests-for-user-data"></a>Upravljanje zahtev za izbris uporabniških podatkov

Skrbnik storitve Customer Insights lahko za izbris uporabniških podatkov storitve Customer Insights upošteva te korake:

1. Vpis v storitev Dynamics 365 Customer Insights.
2. Pri vpogledih v občinstvo izberite **Skrbnik** > **Dovoljenja**.
3. Potrdite polje za uporabnika, ki ga želite izbrisati.
4. Izberite **Odstrani**.

> [!div class="mx-imgBorder"]
> ![Upravljanje zahtev za izbris uporabniških podatkov v skladu z uredbo GDPR](media/gdpr-permissions.png "Upravljanje zahtev za izbris uporabniških podatkov v skladu z uredbo GDPR")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Odziv na zahteve posameznikov, na katere se nanašajo podatki, za izvoz v skladu z uredbo GDPR

Kot del naše zaveze za sodelovanje z vami na vaši poti do uvedbe Splošne uredbe o varstvu podatkov (GDPR) smo ustvarili dokumentacijo, ki vam bo pomagala pri pripravi. Ta dokumentacija opisuje korake, ki jih lahko danes opravite za zagotavljanje skladnosti z uredbo GDPR pri uporabi vpogledov v občinstvo.

### <a name="manage-export-and-view-requests"></a>Upravljajte izvoza in ogled zahtev

Zaradi pravice do prenosljivosti podatkov lahko posamezniki, na katere se nanašajo podatki, zahtevajo kopijo svojih osebnih podatkov v elektronski obliki (tj. »strukturirana, pogosto uporabljena, strojno berljiva in interoperabilna oblika«), ki se jo lahko pošlje drugemu upravljavcu podatkov.

#### <a name="export-customer-data-tenant-admin"></a>Izvoz podatkov o stranki (skrbnik najemnika)

Skrbnik najemnika lahko za izvoz podatkov upošteva ta navodila:

1. Pošljite e-poštno sporočilo na naslov D365CI@microsoft.com ter v zahtevi navedite e-poštni naslov stranke. Ekipa Customer Insights bo na registrirani e-poštni naslov skrbnika najemnika poslala e-poštno sporočilo s prošnjo za potrditev izvoza podatkov.
2. Potrdite potrditev izvoza podatkov za zahtevano stranko.
3. Prejmite izvožene podatke prek e-poštnega naslova skrbnika najemnika.

#### <a name="export-user-data-tenant-admin"></a>Izvoz uporabniških podatkov (skrbnik najemnika)

1. Pošljite e-poštno sporočilo na naslov D365CI@microsoft.com ter v zahtevi navedite e-poštni naslov uporabnika. Ekipa Customer Insights bo na registrirani e-poštni naslov skrbnika najemnika poslala e-poštno sporočilo s prošnjo za potrditev izvoza podatkov.
2. Potrdite potrditev izvoza podatkov za zahtevanega uporabnika.
3. Prejmite izvožene podatke prek e-poštnega naslova skrbnika najemnika.


[!INCLUDE[footer-include](../includes/footer-banner.md)]