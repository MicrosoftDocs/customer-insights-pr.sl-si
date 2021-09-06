---
title: 'Povezovalnik LiveRamp '
description: Naučite se, kako konfigurirati povezavo in izvažati v LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7940db3efacad62ba16099849b3e3ca00d2a5cc1ed31e15a34209c0797e6ae13
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035665"
---
# <a name="export-segments-to-liverampreg-preview"></a>Izvoz segmentov v LiveRamp&reg; (predogledna različica)

Vklopite svoje podatke na platformi LiveRamp za povezovanje z več kot 500 platformami v digitalni, družbeni in televizijski sferi. Delajte s podatki v rešitvi LiveRamp, da ciljate, ukinete in prilagodite oglaševalske akcije.

## <a name="prerequisites-for-a-connection"></a>Predpogoji za povezavo

- Za uporabo tega povezovalnika potrebujete naročnino za LiveRamp.
- Če želite pridobiti naročnino, neposredno [kontaktirajte LiveRamp](https://liveramp.com/contact/). [Preberite več o LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>Nastavitev povezave s storitvijo LiveRamp

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajanje povezave** in izberite **LiveRamp** za konfiguracijo povezave.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Navedite **Uporabniško ime** in **Geslo** za svoj račun LiveRamp Secure FTP (SFTP).
Te poverilnice se lahko razlikujejo od vaših poverilnic za LiveRamp Onboarding.

1. Izberite **Preveri**, da preskusite povezavo z LiveRamp.

1. Po uspešnem preverjanju podajte soglasje za **Zasebnost podatkov in skladnost**, tako da izberete potrditveno polje **Strinjam se**.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Za ustvarjanje novega izvoza izberite **Dodaj cilj**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku LiveRamp. Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.

1. V polju **Izbira identifikatorja ključa** izberite **E-pošta**, **Ime in naslov** ali **Telefon** za pošiljanje v LiveRamp za reševanje identitete.
   > [!div class="mx-imgBorder"]
   > ![Povezovalnik LiveRamp s preslikavo atributov.](media/export-liveramp-segments.png "Povezovalnik LiveRamp s preslikavo atributov")

1. Preslikajte pripadajoče atribute iz poenotene entitete stranke za izbrani identifikator ključa.

1. Izberite **Dodajanje atributa** za preslikavo več atributov za pošiljanje v LiveRamp.

   > [!TIP]
   > Če v LiveRamp pošljete več atributov identifikatorja ključa, boste verjetno dobili višjo stopnjo ujemanja.

1. Izberite segmente, ki jih želite izvoziti v LiveRamp.

1. Izberite **Shrani**.

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab). Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Liveramp, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Liveramp izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
