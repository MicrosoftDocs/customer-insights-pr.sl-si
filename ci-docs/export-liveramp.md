---
title: Izvoz segmentov v LiveRamp (predogledna različica)
description: Naučite se, kako konfigurirati povezavo in izvažati v LiveRamp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196736"
---
# <a name="export-segments-to-liverampreg-preview"></a>Izvoz segmentov v LiveRamp&reg; (predogledna različica)

Vklopite svoje podatke na platformi LiveRamp za povezovanje z več kot 500 platformami v digitalni, družbeni in televizijski sferi. Delajte s podatki v rešitvi LiveRamp, da ciljate, ukinete in prilagodite oglaševalske akcije.

## <a name="prerequisites"></a>Zahteve

- Naročnina LiveRamp za uporabo tega priključka. Če želite pridobiti naročnino, neposredno [kontaktirajte LiveRamp](https://liveramp.com/contact/). [Preberite več o LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>Znane omejitve

- Izvoz LiveRamp uporablja izvoz SFTP. Cilji SFTP za požarnimi zidovi trenutno niso podprti.
- Če za preverjanje pristnosti uporabljate ključ SSH, se prepričajte, da ste [ustvarite svoj zasebni ključ](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) kot format PEM ali SSH.COM. Če uporabljate Putty, pretvorite svoj zasebni ključ tako, da izvozite kot Open SSH. Podprte so naslednje oblike zasebnih ključev:
  - RSA v formatu OpenSSL PEM in ssh.com
  - DSA v formatu OpenSSL PEM in ssh.com
  - ECDSA 256/384/521 v formatu OpenSSL PEM
  - ED25519 in RSA v obliki ključa OpenSSH
- Trajanje izvoza je odvisno od zmogljivosti vašega sistema. Kot minimalno konfiguracijo strežnika priporočamo dvojedrni procesor in 1 Gb pomnilnika.
- Izvoz entitet z do 100 milijoni profilov strank lahko traja 90 minut, če uporabite priporočeno minimalno konfiguracijo dvojedrnega procesorja in 1 Gb pomnilnika.
- Dejansko število profilov (ali podatkov), ki jih lahko izvozite v LiveRamp, je odvisno od vaše naročnine na LiveRamp.

## <a name="set-up-connection-to-liveramp"></a>Nastavitev povezave s storitvijo LiveRamp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **LiveRamp**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto jo lahko uporabljajo samo skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Izberite, ali želite preverjanje pristnosti prek SSH ali uporabniškega imena/gesla za svojo povezavo in navedite potrebne podrobnosti.

1. Izberite **Preveri**, da preskusite povezavo z LiveRamp.

1. Po uspešnem preverjanju preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **Strinjam se**.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku LiveRamp. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Vnesite ime za izvoz.

1. V **Povežite podatke** polje izberite **E-naslov**, **in naslov**, oz **Telefon** za pošiljanje v LiveRamp za razrešitev identitete.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="Povezovalnik LiveRamp s preslikavo atributov.":::

1. Preslikajte ustrezne atribute iz vaše entiteta *Stranka* za izbrani identifikator ključa.

1. Izberite **Dodajanje atributa** za preslikavo več atributov za pošiljanje v LiveRamp.

   > [!TIP]
   > Če v LiveRamp pošljete več atributov identifikatorja ključa, boste verjetno dobili višjo stopnjo ujemanja.

1. Izberite segmente, ki jih želite izvoziti.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
