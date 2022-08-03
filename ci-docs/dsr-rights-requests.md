---
title: Zahteve posameznikov, na katere se nanašajo podatki, (DSR) v skladu z uredbo GDPR | Microsoftovo gradivo
description: Odzovite se na zahteve posameznikov, na katere se nanašajo podatki, za Dynamics 365 Customer Insights.
ms.date: 05/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6c6ce49c18de3a09d28138316d893e6842919042
ms.sourcegitcommit: ff0f4b5664d995870c91adb87c7d3780a582efca
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/13/2022
ms.locfileid: "9146715"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Zahteve posameznikov, na katere se nanašajo podatki, (DSR) v skladu z uredbo GDPR

Splošna uredba Evropske unije o varstvu podatkov (GDPR) velja od 25. maja 2018. Posameznikom daje pomembne pravice glede njihovih podatkov. Pri GDPR gre za zaščito in omogočanje pravic posameznikov do zasebnosti. Več informacij o Microsoftovi zavezanosti do varnosti in skladnosti lahko preberete v [Microsoftovem središču zaupanja](https://www.microsoft.com/trust-center).

Prizadevamo si, da svojim strankam pomagamo izpolniti zahteve uredbe GDPR. Vključuje pravico do brisanja in izvoza podatkov, kar vključuje osebne podatke, kot so ID-ji uporabnikov, telefonske številke in e-poštni naslovi. Skrbniki lahko izvajajo zahteve uporabnikov za brisanje ali izvoz osebnih podatkov.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Odziv na zahteve posameznikov, na katere se nanašajo podatki, za izbris v skladu z uredbo GDPR za Dynamics 365 Customer Insights

»Pravica do izbrisa« z odstranitvijo osebnih podatkov iz podatkov o strankah, ki jih ima organizacija, je ključna zaščita v Splošni uredbi o varstvu podatkov (GDPR). Odstranitev osebnih podatkov vključuje odstranitev vseh osebnih podatkov in sistemsko ustvarjenih dnevnikov, razen informacij iz dnevnika spremljanja sprememb.

#### <a name="manage-data-subject-delete-requests"></a>Upravljanje zahtev posameznika, na katerega se nanašajo podatki, za izbris

Customer Insights ponuja naslednje izkušnje v izdelku za brisanje osebnih podatkov za določeno stranko ali uporabnika:

- **Upravljanje zahtev za izbris podatkov o strankah**: podatki o strankah v storitvi Customer Insights se uvozijo iz izvirnih virov podatkov zunaj storitve Customer Insights. Najprej izvedite zahteve za brisanje GDPR v izvirniku vir podatkov.
- **Upravljanje zahtev za izbris uporabniških podatkov storitve Customer Insights**: podatke za uporabnike je ustvaril Customer Insights. Vse zahteve za izbris v skladu z uredbo GDPR morajo biti izvedene v storitvi Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Upravljanje zahtev za izbris podatkov o strankah

Skrbnik Customer Insights lahko sledi tem korakom, da odstrani podatke o strankah, ki so bili izbrisani v vir podatkov. Prepričajte se, da je bila zahteva za brisanje izvedena v vašem vir podatkov, preden nadaljujete s spodaj navedenimi koraki. 

1. Vpis v storitev Dynamics 365 Customer Insights.
1. Pojdi do **podatki** > **Viri podatkov**
1. Za vsak vir podatkov na seznamu, ki vsebuje izbrisane podatke strank:
   1. Izberite navpično elipso (&vellip;) in nato izberite **Osveži**.
   1. Preverite stanje vira podatkov v razdelku **Stanje**. Kljukica pomeni, da je bila osvežitev uspešna. Opozorilni trikotnik pomeni, da je prišlo do napake. Če se prikaže opozorilni trikotnik, pošljite sporočilo na naslov D365CI@microsoft.com.
1. Po uspešni osvežitvi podatkovnih virov zaženite tudi spodnje osvežitve. Še posebej, če nimate načrtovane ponavljajoče se popolne osvežitve Customer Insights. 

> [!IMPORTANT]
> Statični segmenti niso vključeni v popolno osvežitev ali tekoče osvežitve po zahtevi za brisanje. Če želite zagotoviti, da so podatki o strankah odstranjeni tudi iz statičnih segmentov, znova ustvarite statične segmente z osveženimi izvornimi podatki.

> [!div class="mx-imgBorder"]
> ![Obravnava zahtev za izbris podatkov o strankah v skladu z uredbo GDPR.](media/gdpr-data-sources.png "Obravnava zahtev za izbris podatkov o strankah v skladu z uredbo GDPR")

##### <a name="manage-delete-requests-for-user-data"></a>Upravljanje zahtev za izbris uporabniških podatkov

Skrbnik storitve Customer Insights lahko za izbris uporabniških podatkov storitve Customer Insights upošteva te korake:

1. Vpis v storitev Dynamics 365 Customer Insights.
2. Pojdi do **skrbnik** > **Varnost** > **Dovoljenja**.
3. Potrdite polje za uporabnika, ki ga želite izbrisati.
4. Izberite **Odstrani**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Odziv na zahteve posameznikov, na katere se nanašajo podatki, za izvoz v skladu z uredbo GDPR

Kot del naše zaveze k sodelovanju z vami na vaši poti do Splošne uredbe o varstvu podatkov (GDPR) smo razvili dokumentacijo, ki vam bo pomagala odgovoriti na zahteve posameznikov, na katere se nanašajo osebni podatki.

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

### <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Obravnava izbrisa podatkov v Dynamics 365 Customer Insights

1. Podatki bodo izbrisani (podatkovne particije in posnetki podatkov), če so particije podatkov in posnetki podatkov neaktivni več kot 30 dni, kar pomeni, da so bili zamenjani z novo particijo podatkov in posnetki z osvežitvijo podatkovnih virov.
2. Ne izbrišejo se vsi podatki in posnetki. Najnovejša podatkovna particija in posnetek podatkov sta po definiciji aktivna, ker se uporabljata v Customer Insights. Za najnovejše podatke ni pomembno, ali viri podatkov niso bili osveženi v zadnjih 30 dneh.

[!INCLUDE [footer-include](includes/footer-banner.md)]
