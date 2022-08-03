---
title: Izvoz podatkov v Salesforce Marketing Cloud (predogled)
description: Naučite se, kako konfigurirati povezavo in podatke izvoziti v Salesforce Marketing Cloud.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197058"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Izvoz podatkov v Salesforce Marketing Cloud (predogled)

Podatke o strankah uporabite v programu Salesforce Marketing Cloud tako, da jih izvozite s pomočjo lokacije protokola za varen prenos datotek (SFTP).

## <a name="prerequisites"></a>Zahteve

- An [Gostitelj SFTP za Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) in ustrezne skrbniške poverilnice.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Nastavite povezavo s Salesforce Marketing Cloud

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **Salesforce Marketing Cloud**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto jo lahko uporabljajo samo skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vnesite **uporabniško ime**, **geslo**, **ime gostitelja** in **izvozno mapo** za vaš račun SFTP.

1. Če želite preskusiti povezavo, izberite **Preveri**.

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku SFTP. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Vnesite ime za izvoz.

1. Izberite, ali želite izvoziti podatke z možnostjo **Gzipped** ali **Razširjeno** in **ločilo polja** za izvožene datoteke.

1. Izberite entitete, na primer segmente, ki jih želite izvoziti.

   > [!NOTE]
   > Vsaka izbrana entiteta bo pri izvozu razdeljena na največ pet izhodnih datotek.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Podatke Customer Insights iz lokacije SFTP izvozite v Saleforce Marketing Cloud

1. Za uvoz podatkovne datoteke Customer Insights iz lokacije SFTP ustvarite [razširitve podatkov v storitvi Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) za uvoz podatkovne datoteke Customer Insights z lokacije SFTP.

2. [Uvozite podatke z lokacije SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) v razširitev podatkov Salesforce Marketing Cloud.

3. Za uvoz podatkov v razširitve podatkov nastavite avtomatizacijo. Preberite več o [avtomatizacijah spuščanja datotek in načrtovanih avtomatizacijah](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Določite [avtomatizacijo spuščanja datotek](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) ali  [načrtovano avtomatizacijo](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Tukaj je naveden primer [avtomatizacije s SFTP-jem](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
