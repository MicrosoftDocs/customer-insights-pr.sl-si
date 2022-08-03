---
title: Izvoz podatkov v gostitelje SFTP (predogled) (vsebuje video)
description: Naučite se, kako konfigurirati povezavo in izvažati na lokacijo SFTP.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207249"
---
# <a name="export-data-to-sftp-hosts-preview"></a>Izvoz podatkov v gostitelje SFTP (predogled)

Uporabite svoje podatke o strankah v aplikacijah drugih ponudnikov tako, da jih izvozite na lokacijo protokola za varen prenos datotek (SFTP).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>Zahteve

- Razpoložljivost gostitelja SFTP in ustreznih poverilnic

## <a name="known-limitations"></a>Znane omejitve

- Cilji SFTP za požarnimi zidovi trenutno niso podprti.
- Trajanje izvoza je odvisno od zmogljivosti vašega sistema. Kot minimalno konfiguracijo strežnika priporočamo dvojedrni procesor in 1 Gb pomnilnika.
- Do 100 milijonov profilov strank, kar lahko traja 90 minut pri uporabi priporočene minimalne konfiguracije dveh CPU jeder in 1 Gb pomnilnika.
- Če za preverjanje pristnosti uporabljate ključ SSH, se prepričajte, da ste [ustvarite svoj zasebni ključ](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) kot format PEM ali SSH.COM. Če uporabljate Putty, pretvorite svoj zasebni ključ tako, da izvozite kot Open SSH. Podprte so naslednje oblike zasebnih ključev:
  - RSA v formatu OpenSSL PEM in ssh.com
  - DSA v formatu OpenSSL PEM in ssh.com
  - ECDSA 256/384/521 v formatu OpenSSL PEM
  - ED25519 in RSA v obliki ključa OpenSSH

## <a name="set-up-connection-to-sftp"></a>Nastavitev povezave s storitvijo SFTP

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **SFTP**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto jo lahko uporabljajo samo skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Izberite, ali želite preverjanje pristnosti prek SSH ali uporabniškega imena/gesla za svojo povezavo in navedite potrebne podrobnosti. Če za preverjanje pristnosti uporabljate ključ SSH, se prepričajte, da ste [ustvarite svoj zasebni ključ](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) kot format PEM ali SSH.COM. Če uporabljate Putty, pretvorite svoj zasebni ključ tako, da izvozite kot Open SSH. Podprte so naslednje oblike zasebnih ključev:
   - RSA v formatu OpenSSL PEM in ssh.com
   - DSA v formatu OpenSSL PEM in ssh.com
   - ECDSA 256/384/521 v formatu OpenSSL PEM
   - ED25519 in RSA v obliki ključa OpenSSH

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

> [!TIP]
> Izvoz entitet, ki vsebujejo veliko količino podatkov, lahko povzroči več datotek CSV v isti mapi za vsak izvoz. Razdelitev izvozov se zgodi zaradi učinkovitosti, da se zmanjša čas, potreben za dokončanje izvoza.

[!INCLUDE [footer-include](includes/footer-banner.md)]
