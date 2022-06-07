---
title: Zahteve posameznikov, na katere se nanašajo podatki, (DSR) v skladu z uredbo GDPR | Microsoftovo gradivo
description: Odzovite se na zahteve posameznikov, na katere se nanašajo podatki, za Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: af2583295627f98e980adbca4f216b9c34c3cad8
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808587"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Zahteve posameznikov, na katere se nanašajo podatki, (DSR) v skladu z uredbo GDPR

Splošna uredba Evropske unije o varstvu podatkov (GDPR) velja od 25. maja 2018. Posameznikom daje pomembne pravice glede njihovih podatkov. Pri GDPR gre za zaščito in omogočanje pravic posameznikov do zasebnosti. Več informacij o Microsoftovi zavezanosti do varnosti in skladnosti lahko preberete v [Microsoftovem središču zaupanja](https://www.microsoft.com/trust-center).

Prizadevamo si, da svojim strankam pomagamo izpolniti zahteve uredbe GDPR. Vključuje pravico do brisanja in izvoza podatkov, kar vključuje osebne podatke, kot so ID-ji uporabnikov, telefonske številke in e-poštni naslovi. Skrbniki lahko izvajajo zahteve uporabnikov za brisanje ali izvoz osebnih podatkov.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Odziv na zahteve posameznikov, na katere se nanašajo podatki, za izbris v skladu z uredbo GDPR za Dynamics 365 Customer Insights

»Pravica do izbrisa« z odstranitvijo osebnih podatkov iz podatkov o strankah, ki jih ima organizacija, je ključna zaščita v Splošni uredbi o varstvu podatkov (GDPR). Odstranitev osebnih podatkov vključuje odstranitev vseh osebnih podatkov in sistemsko ustvarjenih dnevnikov, razen informacij iz dnevnika spremljanja sprememb.

#### <a name="manage-data-subject-delete-requests"></a>Upravljanje zahtev posameznika, na katerega se nanašajo podatki, za izbris

Customer Insights ponuja naslednje izkušnje v izdelku za brisanje osebnih podatkov za določeno stranko ali uporabnika:

- **Upravljanje zahtev za izbris podatkov o strankah**: podatki o strankah v storitvi Customer Insights se uvozijo iz izvirnih virov podatkov zunaj storitve Customer Insights. Vse zahteve za izbris v skladu z uredbo GDPR morajo biti izvedene v izvirnem viru podatkov.
- **Upravljanje zahtev za izbris uporabniških podatkov storitve Customer Insights**: podatke za uporabnike je ustvaril Customer Insights. Vse zahteve za izbris v skladu z uredbo GDPR morajo biti izvedene v storitvi Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Upravljanje zahtev za izbris podatkov o strankah

Skrbnik storitve Customer Insights lahko upošteva te korake, da odstrani podatke stranke, ki so bili izbrisani iz vira podatkov:

1. Vpis v storitev Dynamics 365 Customer Insights.
2. Pojdi do **Podatki** > **Viri podatkov**
3. Za vsak vir podatkov na seznamu, ki vsebuje izbrisane podatke strank:
   1. Izberite navpično elipso (&vellip;) in nato izberite **Osveži**.
   2. Preverite stanje vira podatkov v razdelku **Stanje**. Kljukica pomeni, da je bila osvežitev uspešna. Opozorilni trikotnik pomeni, da je prišlo do napake. Če se prikaže opozorilni trikotnik, pošljite sporočilo na naslov D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Obravnava zahtev za izbris podatkov o strankah v skladu z uredbo GDPR.](media/gdpr-data-sources.png "Obravnava zahtev za izbris podatkov o strankah v skladu z uredbo GDPR")

##### <a name="manage-delete-requests-for-user-data"></a>Upravljanje zahtev za izbris uporabniških podatkov

Skrbnik storitve Customer Insights lahko za izbris uporabniških podatkov storitve Customer Insights upošteva te korake:

1. Vpis v storitev Dynamics 365 Customer Insights.
2. Pojdi do **Admin** > **Varnost** > **Dovoljenja**.
3. Potrdite polje za uporabnika, ki ga želite izbrisati.
4. Izberite **Odstrani**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Odziv na zahteve posameznikov, na katere se nanašajo podatki, za izvoz v skladu z uredbo GDPR

Kot del naše zaveze, da bomo z vami sodelovali na vaši poti do Splošne uredbe o varstvu podatkov (GDPR), smo razvili dokumentacijo, ki vam bo v pomoč pri odgovarjanju na zahteve posameznikov, na katere se nanašajo osebni podatki.

#### <a name="manage-export-and-view-requests"></a>Upravljajte izvoza in ogled zahtev

Zaradi pravice do prenosljivosti podatkov lahko posamezniki, na katere se nanašajo podatki, zahtevajo kopijo svojih osebnih podatkov v elektronski obliki (tj. »strukturirana, pogosto uporabljena, strojno berljiva in interoperabilna oblika«), ki se jo lahko pošlje drugemu upravljavcu podatkov.

##### <a name="export-customer-data-tenant-admin"></a>Izvoz podatkov o stranki (skrbnik najemnika)

Skrbnik najemnika lahko za izvoz podatkov upošteva ta navodila:

1. Pošljite e-poštno sporočilo na naslov D365CI@microsoft.com ter v zahtevi navedite e-poštni naslov stranke. Ekipa Customer Insights bo na registrirani e-poštni naslov skrbnika najemnika poslala e-poštno sporočilo s prošnjo za potrditev izvoza podatkov.
2. Potrdite potrditev izvoza podatkov za zahtevano stranko.
3. Prejmite izvožene podatke prek e-poštnega naslova skrbnika najemnika.

##### <a name="export-user-data-tenant-admin"></a>Izvoz uporabniških podatkov (skrbnik najemnika)

1. Pošljite e-poštno sporočilo na naslov D365CI@microsoft.com ter v zahtevi navedite e-poštni naslov uporabnika. Ekipa Customer Insights bo na registrirani e-poštni naslov skrbnika najemnika poslala e-poštno sporočilo s prošnjo za potrditev izvoza podatkov.
2. Potrdite potrditev izvoza podatkov za zahtevanega uporabnika.
3. Prejmite izvožene podatke prek e-poštnega naslova skrbnika najemnika.

## <a name="consent-management-preview"></a>Upravljanje privolitve (predogled)

Zmožnost upravljanja privolitve ne zbira uporabniških podatkov neposredno. Uvaža in obdeluje samo podatke o privolitvi, ki jih zagotovijo uporabniki v drugih aplikacijah.

Če želite odstraniti podatke o soglasju o določenih uporabnikih, jih odstranite v virih podatkov, ki jih prevzame zmožnost upravljanja privolitve. Po osvežitvi vir podatkov bodo odstranjeni podatki izbrisani tudi v središču za soglasje. Aplikacije, ki uporabljajo entiteto za soglasje, bodo izbrisale tudi podatke, ki so bili odstranjeni iz vira po a [osveži](system.md#refresh-processes). Priporočamo, da po odzivu na zahtevo posameznika, na katerega se osebni podatki nanašajo, hitro osvežite vire podatkov za odstranitev uporabnikovih podatkov iz vseh drugih procesov in aplikacij.

[!INCLUDE [footer-include](includes/footer-banner.md)]