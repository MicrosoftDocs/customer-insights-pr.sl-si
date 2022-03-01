---
title: 'Povezovalnik LiveRamp '
description: Naučite se izvoziti podatke v rešitev LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 86aa8c66a47ee61741082c95f05d2e5ce3f06f35
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667204"
---
# <a name="liverampreg-connector-preview"></a>Povezovalnik za LiveRamp&reg; (predogled)

Aktivirajte svoje podatke v rešitvi LiveRamp, da povežete več kot 500 platform po digitalnih, družabnih in televizijskih ekosistemih. Delajte s podatki v rešitvi LiveRamp, da ciljate, ukinete in prilagodite oglaševalske akcije.

## <a name="prerequisites"></a>Zahteve

- Za uporabo tega povezovalnika potrebujete naročnino za LiveRamp.
- Če želite pridobiti naročnino, neposredno [kontaktirajte LiveRamp](https://liveramp.com/contact/). [Preberite več o LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>Povezovanje v LiveRamp

1. Pri vpogledih v občinstvo izberite **Skrbnik** > **Cilji izvoza**.

1. Pri ploščici **LiveRamp** izberite **Nastavi**.

1. Dajte svojemu cilju prepoznavno ime v polju **Prikazno ime**.

1. Navedite **Uporabniško ime** in **Geslo** za svoj račun LiveRamp Secure FTP (SFTP).
Te poverilnice se lahko razlikujejo od vaših poverilnic za LiveRamp Onboarding.

1. Izberite **Preveri**, da preskusite povezavo z LiveRamp.

1. Po uspešnem preverjanju podajte soglasje za **Zasebnost podatkov in skladnost**, tako da izberete potrditveno polje **Strinjam se**.

1. Izberite **Naprej**, da nastavite povezovalnik LiveRamp.

## <a name="configure-the-connector"></a>Konfiguracija povezovalnika

1. V polju **Izbira identifikatorja ključa** izberite **E-pošta**, **Ime in naslov** ali **Telefon** za pošiljanje v LiveRamp za reševanje identitete.

1. Preslikajte pripadajoče atribute iz poenotene entitete stranke za izbrani identifikator ključa.

1. Izberite **Dodaj atribut**, da preslikate dodatne atribute za pošiljanje v LiveRamp.

   > [!TIP]
   > Če v LiveRamp pošljete več atributov identifikatorja ključa, boste verjetno dobili višjo stopnjo ujemanja.

1. Izberite segmente, ki jih želite izvoziti v LiveRamp.

1. Izberite **Shrani**.

> [!div class="mx-imgBorder"]
> ![Povezovalnik LiveRamp s preslikavo atributov](media/export-liveramp-segments.png "Povezovalnik LiveRamp s preslikavo atributov")

## <a name="export-the-data"></a>Izvoz podatkov

Izvoz se bo kmalu začel, če so bile izpolnjene zahteve za izvoz. Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).
Ko je izvoz uspešno dokončan, se lahko vpišete v LiveRamp Onboarding, da aktivirate in distribuirate svoje podatke.

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Liveramp, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Liveramp izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.