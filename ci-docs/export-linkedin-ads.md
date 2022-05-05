---
title: Izvoz podatkov Customer Insights v LinkedIn Ads
description: Naučite se, kako konfigurirati povezavo in izvažati v LinkedIn Ads.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bf1d12ffbd7a4cfd7d268fea8a1f90cc37589e00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643921"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Izvoz segmentov v LinkedIn Ads (predogledna različica)

Izvozite segmente poenotenih profilov strank v LinkedIn Ads, da ustvarite ujemajoče se ciljne skupine. Uporabite ujemajoče se ciljne skupine za ciljanje podjetij in stikov.

## <a name="prerequisites"></a>Zahteve

-   Imate račun za [LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) in pripadajoče skrbniške poverilnice.
-   Imaš [konfigurirani segmenti](segments.md) v Customer Insights.
-   Profili strank v izvoženih segmentih vsebujejo polje z e-poštnim naslovom.

## <a name="known-limitations"></a>Znane omejitve

- Vaš segment v storitvi Customer Insights mora vsebovati vsaj 300 edinstvenih profilov. 
- V storitev LinkedIn Ads lahko izvozite do 100.000 profilov strank na izvoz.
- Izvoz v LinkedIn Ads je omejen na segmente.
- Izvoz do 100.000 profilov strank v storitev LinkedIn Ads lahko traja do 10 minut. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Nastavitev povezave z LinkedIn Ads

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajanje povezave** in izberite **LinkedIn Ads** za konfiguracijo povezave.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Navedite svoj [ID računa LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).

1. Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.

1. Izberite **Poveži** za inicializiranje povezave s storitvijo Campaign Monitor.

1. Izberite **Preverjanje pristnosti z aplikacijo LinkedIn** in vnesite svoje skrbniške poverilnice za LinkedIn Campaign Manager.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

Izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Za ustvarjanje novega izvoza izberite **Dodaj cilj**.

1. V polju **Povezava za izvoz** izberite povezavo iz razdelka LinkedIn Ads. Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.

1. Izberite, ali želite izvoziti podatke za [ciljanje na stike](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ali [ciljanje na podjetja](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) v orodju LinkedIn. 

1. V razdelku **Ujemanje podatkov** za ciljanje stikov izberite vsaj eno polje, ki predstavlja e-poštni naslov stranke, ID oglasa Apple, ID oglasa Google, ID uporabnika Google ali ime in priimek. Če izberete ciljanje podjetja, izberite vsaj eno polje, ki predstavlja ime podjetja, e-poštno domeno, URL strani LinkedIn, simbol zaloge ali spletno mesto. Za nadaljnjo opredelitev izvoza lahko izberete dodatna polja. 

1. Izberite segmente, ki jih želite izvoziti. Ujemajoče se ciljne skupine v LinkedIn Campaign Manager bodo samodejno ustvarjene z imenom segmentov za izvoz. Vsak segment bo prikazal ločeno ciljno skupino. 

1. Izberite **Shrani**.

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab). Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite, da Dynamics 365 Customer Insights prenese podatke v LinkedIn Ads, dovolite prenos podatkov zunaj meja zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno potencialno občutljivih podatkov, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da LinkedIn Ads izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti, ki jih morda imate. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Vaš skrbnik Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza, da prenehate uporabljati to funkcijo.