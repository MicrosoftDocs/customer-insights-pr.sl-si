---
title: Izvozi segmente v Facebook Ads Manager (predogled) (vsebuje video)
description: Naučite se, kako konfigurirati povezavo in izvažati v Upravitelja oglasov za Facebook.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01be1a075db0da05dc5536aea8a33093f9a2ea13
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195034"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Izvozi segmente v Facebook Ads Manager (predogled)

Izvozite segmente poenotenih profilov strank v Upravitelja oglasov za Facebook za ustvarjanje oglaševalskih akcij v storitvama Facebook in Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Zahteve

- A [Facebook Ads račun](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) ki vključuje a [Facebook Poslovni račun](https://business.facebook.com/).
- Skrbniške pravice na [Facebook Ads račun](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Znane omejitve

- Do 10 milijonov profilov strank na izvoz v Facebook Ads Manager, kar lahko traja do 90 minut.
- Samo segmenti.
- Facebook *seznam strank* vtipkati [občinstva po meri](https://www.facebook.com/business/help/744354708981227?id=2469097953376494) samo.
  > [!NOTE]
  > V nekaterih primerih boste na spustnem seznamu morda videli ciljne skupine po meri različnih vrst. Če izberete drugo vrsto, ki ni *seznam strank*, izvoz ne uspe.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Nastavitev povezave z Upraviteljem oglasov za Facebook

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **Facebook Ads Manager**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. [Dovoli sodelujočim, da uporabljajo povezavo za izvoze](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Preverjanje pristnosti z oglasi za Facebook:

   1. Izberite možnost **Nadaljujte s storitvijo Facebook** za prijavo v svoj oglaševalski račun Facebook.

   1. Omogočite dovoljenje **ads_management** po preverjanju pristnosti s storitvijo Facebook.

   1. Izberite **račun za oglaševanje v storitvi Facebook**, s katerim želite delati.

   1. Na spustnem seznamu izberite možnost **Trenutno občinstvo po meri** ali ustvarite **Novo občinstvo po meri**.

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz**.

1. V **Povezava za izvoz** polju izberite povezavo med Facebook Razdelek Ad Manager. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Vnesite ime za izvoz.

1. V **Povežite podatke** polje izberite **E-naslov**, **in naslov**, oz **Telefon** poslati na Facebook Ads Manager.

1. Preslikajte pripadajoče atribute iz poenotene entitete stranke za izbrani identifikator ključa.
   > [!TIP]
   > Največ možnosti za ujemanje boste dosegli, če za identifikator ključa izberete možnost **E-poštni naslov**. Dodajanje dodatnih identifikatorjev lahko izboljša ujemanje.

1. Izberite **Dodajanje atributa** za preslikavo več atributov za pošiljanje v Upravitelja oglasov za Facebook. Atributi upravitelja oglasov za Facebook se preslikajo v naslednja uporabnikom prijazna imena: **IM** = **Ime**, **PR** = **Priimek**, **ZI** = **Začetnica imena**, **TELEFON** = **Telefon**, **SP** = **Spol**, **DR** = **Datum rojstva**, **DRŽ** = **Država**, **MST** = **Mesto**, **PŠ** = **Poštna številka**, **DRŽAVA** = **Država/regija**

1. Izberite segmente, ki jih želite izvoziti.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
