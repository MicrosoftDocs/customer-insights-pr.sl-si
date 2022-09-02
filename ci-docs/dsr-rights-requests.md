---
title: Zahteve posameznikov, na katere se nanašajo podatki, (DSR) v skladu z uredbo GDPR | Microsoftovo gradivo
description: Odzovite se na zahteve posameznikov, na katere se nanašajo podatki, za Dynamics 365 Customer Insights.
ms.date: 08/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 49251fb46957c4d7ec205b93c9547a3cd380eb11
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387131"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Zahteve posameznikov, na katere se nanašajo podatki, (DSR) v skladu z uredbo GDPR

Splošna uredba Evropske unije o varstvu podatkov (GDPR) velja od 25. maja 2018. Posameznikom daje pomembne pravice glede njihovih podatkov. Pri GDPR gre za zaščito in omogočanje pravic posameznikov do zasebnosti. Preberite več o Microsoftovi zavezanosti varnosti in skladnosti na [Microsoftovo središče zaupanja](https://www.microsoft.com/trust-center).

Prizadevamo si, da svojim strankam pomagamo izpolniti zahteve uredbe GDPR. Vključuje pravico do izbrisa ali izvoza podatkov, ki vključujejo osebne podatke, kot so ID-ji uporabnikov, telefonske številke in e-poštni naslovi. Skrbniki lahko izvajajo zahteve uporabnikov za brisanje ali izvoz osebnih podatkov.

## <a name="responding-to-gdpr-data-subject-delete-requests-for-customer-insights"></a>Odgovarjanje na zahteve za izbris posameznika, na katerega se nanašajo osebni podatki GDPR, za Customer Insights

»Pravica do izbrisa« z odstranitvijo osebnih podatkov iz podatkov o strankah, ki jih ima organizacija, je ključna zaščita v Splošni uredbi o varstvu podatkov (GDPR). Odstranitev osebnih podatkov vključuje odstranitev vseh osebnih podatkov in sistemsko ustvarjenih dnevnikov, razen informacij iz dnevnika spremljanja sprememb.

### <a name="manage-data-subject-delete-requests"></a>Upravljanje zahtev posameznika, na katerega se nanašajo podatki, za izbris

Customer Insights ponuja naslednje izkušnje v izdelku za brisanje osebnih podatkov za določeno stranko ali uporabnika:

- **Upravljanje zahtev za izbris podatkov o strankah**: podatki o strankah v storitvi Customer Insights se uvozijo iz izvirnih virov podatkov zunaj storitve Customer Insights. Najprej izvedite zahteve za brisanje GDPR v izvirniku vir podatkov.
- **Upravljanje zahtev za izbris uporabniških podatkov storitve Customer Insights**: podatke za uporabnike je ustvaril Customer Insights. Izvedite vse zahteve za izbris GDPR v Customer Insights.

#### <a name="manage-requests-to-delete-customer-data"></a>Upravljanje zahtev za izbris podatkov o strankah

Kot skrbnik Customer Insights odstranite podatke o strankah Customer Insights, ki so bili izbrisani v vir podatkov. Preverite, ali so bile zahteve za brisanje GDPR izvedene v izvirniku vir podatkov.

1. Vpis v storitev Dynamics 365 Customer Insights.

1. Pojdite na **Podatki** > **Viri podatkov**.

1. Za vsak vir podatkov na seznamu, ki vsebuje izbrisane podatke strank:
   1. Izberite vir podatkov in nato izberite **Osveži**.
   1. Preverite stanje vira podatkov v razdelku **Stanje**. Kljukica pomeni, da je bila osvežitev uspešna. Opozorilni trikotnik pomeni, da je prišlo do napake. Če se prikaže opozorilni trikotnik, pošljite sporočilo na naslov D365CI@microsoft.com.

   :::image type="content" source="media/gdpr-data-sources.png" alt-text="Obravnava zahtev za izbris podatkov o strankah v skladu z uredbo GDPR.":::

1. Po uspešni osvežitvi podatkovnih virov zaženite tudi spodnje osvežitve. Še posebej, če nimate načrtovane ponavljajoče se popolne osvežitve Customer Insights.

   > [!IMPORTANT]
   > Statični segmenti niso vključeni v popolno osvežitev ali tekoče osvežitve po zahtevi za brisanje. Če želite zagotoviti, da so podatki o strankah odstranjeni tudi iz statičnih segmentov, znova ustvarite statične segmente z osveženimi izvornimi podatki.

#### <a name="manage-delete-requests-for-user-data"></a>Upravljanje zahtev za izbris uporabniških podatkov

Kot skrbnik Customer Insights izbrišite uporabniške podatke Customer Insights.

1. Vpis v storitev Dynamics 365 Customer Insights.

1. Pojdi do **skrbnik** > **Varnost** > in izberite **Uporabniki** zavihek.

1. Izberite potrditvena polja za uporabnike, ki jih želite izbrisati.

1. Izberite **Odstrani**.

1. Potrdite brisanje.

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Odziv na zahteve posameznikov, na katere se nanašajo podatki, za izvoz v skladu z uredbo GDPR

Zaradi pravice do prenosljivosti podatkov lahko posamezniki, na katere se nanašajo podatki, zahtevajo kopijo svojih osebnih podatkov v elektronski obliki (tj. »strukturirana, pogosto uporabljena, strojno berljiva in interoperabilna oblika«), ki se jo lahko pošlje drugemu upravljavcu podatkov.

### <a name="manage-export-and-view-requests"></a>Upravljajte izvoza in ogled zahtev

Upravljajte zahteve za izvoz podatkov o strankah ali uporabnikih.

#### <a name="export-customer-data-tenant-admin"></a>Izvoz podatkov o stranki (skrbnik najemnika)

Kot skrbnik najemnika izvozite podatke o strankah.

1. Pošljite e-poštno sporočilo na naslov D365CI@microsoft.com ter v zahtevi navedite e-poštni naslov stranke. Ekipa Customer Insights bo na registrirani e-poštni naslov skrbnika najemnika poslala e-poštno sporočilo s prošnjo za potrditev izvoza podatkov.
2. Potrdite potrditev izvoza podatkov za zahtevano stranko.
3. Prejmite izvožene podatke prek e-poštnega naslova skrbnika najemnika.

#### <a name="export-user-data-tenant-admin"></a>Izvoz uporabniških podatkov (skrbnik najemnika)

Kot skrbnik najemnika izvozite uporabniške podatke.

1. Pošljite e-poštno sporočilo na naslov D365CI@microsoft.com ter v zahtevi navedite e-poštni naslov uporabnika. Ekipa Customer Insights pošlje e-poštno sporočilo na registrirani e-poštni naslov skrbnika najemnika in zahteva potrditev izvoza podatkov.
1. Potrdite potrditev izvoza podatkov za zahtevanega uporabnika.
1. Prejmite izvožene podatke prek e-poštnega naslova skrbnika najemnika.

## <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Obravnava izbrisa podatkov v Dynamics 365 Customer Insights

Podatki se izbrišejo (podatkovne particije in posnetki podatkov), če so particije podatkov in posnetki podatkov neaktivni več kot 30 dni, kar pomeni, da so bili zamenjani z novo particijo podatkov in posnetki z osvežitvijo podatkovnih virov.

Ne izbrišejo se vsi podatki in posnetki. Najnovejša podatkovna particija in posnetek podatkov sta aktivna, ker se uporabljata v Customer Insights. Za najnovejše podatke ni pomembno, ali viri podatkov niso bili osveženi v zadnjih 30 dneh.

[!INCLUDE [footer-include](includes/footer-banner.md)]
