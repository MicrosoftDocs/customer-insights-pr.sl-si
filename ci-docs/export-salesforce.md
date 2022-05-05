---
title: Podatke iz storitve Customer Insights izvozite v Saleforce Marketing Cloud
description: Naučite se, kako konfigurirati povezavo in podatke izvoziti v Salesforce Marketing Cloud.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: aaf5c2607099bbfccf7ed75330267da8c3c5fe1b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643880"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a>Izvoz segmentov in drugih podatkov v Salesforce Marketing Cloud (predogled)

Podatke o strankah uporabite v programu Salesforce Marketing Cloud tako, da jih izvozite s pomočjo lokacije protokola za varen prenos datotek (SFTP).

## <a name="prerequisites-for-connection"></a>Predpogoji za povezavo

- Razpoložljivost gostitelja SFTP in ustreznih skrbniških poverilnic. [Kako nastaviti lokacije SFTP za Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Vzpostavite povezavo s storitvijo Salesforce Marketing Cloud

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Za konfiguriranje povezave izberite možnost **Dodaj povezavo**, nato pa **Salesforce Marketing Cloud**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vnesite **uporabniško ime**, **geslo**, **ime gostitelja** in **izvozno mapo** za vaš račun SFTP.

1. Če želite preskusiti povezavo, izberite **Preveri**.

1. Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Za ustvarjanje novega izvoza izberite **Dodaj cilj**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku SFTP. Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.

1. Izberite, ali želite izvoziti podatke z možnostjo **Gzipped** ali **Razširjeno** in **ločilo polja** za izvožene datoteke.

1. Izberite entitete, na primer segmente, ki jih želite izvoziti.

   > [!NOTE]
   > Vsaka izbrana entiteta bo ob izvozu razdeljena na do pet izhodnih datotek. 

1. Izberite **Shrani**.

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab). Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Podatke Customer Insights iz lokacije SFTP izvozite v Saleforce Marketing Cloud

1. Za uvoz podatkovne datoteke Customer Insights iz lokacije SFTP ustvarite [razširitve podatkov v storitvi Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) za uvoz podatkovne datoteke Customer Insights z lokacije SFTP.

2. [Uvozite podatke z lokacije SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) v razširitev podatkov Salesforce Marketing Cloud. 

3. Za uvoz podatkov v razširitve podatkov nastavite avtomatizacijo. Preberite več o [avtomatizacijah spuščanja datotek in načrtovanih avtomatizacijah](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Določite [avtomatizacijo spuščanja datotek](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) ali  [načrtovano avtomatizacijo](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Tukaj je naveden primer [avtomatizacije s SFTP-jem](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov prek SFTP-ja, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da cilj za izvoz izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
