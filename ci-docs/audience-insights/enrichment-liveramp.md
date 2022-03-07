---
title: Obogatitev podatkov o identiteti LiveRamp
description: Obogatite profile strank s podatki LiveRamp.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ee65cb49447df61dd5c298a84ad21bc119ead558
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/02/2022
ms.locfileid: "8373088"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Obogatite profile strank s podatki o identiteti iz LiveRamp (predogled) 

LiveRamp zagotavlja deterministično ločevanje identitete brez povezave in konsolidacijo podatkov strank. Osebne identifikatorje v svojih podatkih o strankah lahko preslikate v graf identitete AbiliTec in prejmete AbiliTec ID-je. Te ID-je lahko nato uporabite za boljše poenotenje podatkov vaših strank. 

## <a name="prerequisites"></a>Zahteve 

Za konfiguracijo obogatitve morajo biti izpolnjeni naslednji predpogoji: 

- Imate aktivno naročnino na LiveRamp. Za naročnino se obrnite na svojo ekipo za račun LiveRamp ali na [dynamics@liveramp.com](mailto:dynamics@liveramp.com) za več informacij.   

- Aktivna naročnina AbiliTec z ID-jem odjemalca in skrivnostjo za dostop do API-ja. Za več informacij glejte [AbiliTec API Developer Hub](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Podprte države/regije 

Trenutno podpiramo obogatitev profilov strank s podatki LiveRamp samo v Združenih državah. 

## <a name="configure-the-enrichment"></a>Konfiguriranje obogatitve 

1. Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**. 

1. Izberite **Obogatite moje podatke** na **Identiteta** ploščice. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Ploščica identitete na strani s pregledom obogatitve.":::

1. Na spustnem seznamu izberite možnost [povezava](connections.md). Če ni na voljo nobena povezava, se obrnite na skrbnika. Če ste skrbnik, lahko vzpostavite povezavo tako, da izberete **Dodajte povezavo**. Izberite **LiveRamp** s spustnega seznama. 

1. Izberite **Naslednji** in izberite **Stranka nabor podatkov** želite obogatiti s podatki o identiteti iz LiveRamp. Izberete lahko *Stranka* entiteto, da obogatite vse svoje profile strank ali izberite a *segmentu* subjekt, da obogati samo profile strank, ki jih vsebuje ta segment. 

1. Izberite **Naslednji** in določite, katere vrste polj iz vaših enotnih profilov naj se uporabljajo za iskanje ujemajočih se podatkov o identiteti iz LiveRamp. Vsaj eno od polj **Ime in naslov**, **·**, oz **E-naslov** je potrebno. 

   > [!TIP]
   > Več ključnih identifikatorjev in polj preslikate, večja je verjetnost za višjo stopnjo ujemanja 

1. Preslikajte polja iz vašega unified *Stranka* entiteto, ki bo uporabljena za ujemanje z grafom ID-ja AbiliTec LiveRamp. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Možnosti preslikave podatkov za obogatitev LiveRamp.":::

1. Izberite možnost **Naprej**, da dokončate preslikavo polj. 

1. Zagotovite a **ime** za obogatitev in **Izhodna entiteta**. 

1. Po pregledu svoje izbire izberite možnost **Shrani obogatitev**. 

## <a name="configure-the-connection-for-liveramp"></a>Konfigurirajte povezavo za LiveRamp 

Za to morate biti skrbnik [konfigurirajte povezave](connections.md). Izberite **Dodajte povezavo** ko konfigurirate obogatitev ali pojdite na **Admin** > **Povezave** in izberite **Nastaviti** na **LiveRamp** ploščice. 

:::image type="content" source="media/liveramp-connection.png" alt-text="Konfiguracijsko podokno za nastavitev povezave s storitvijo LiveRamp AbiliTec.":::

1. Za **prikazno ime**, vnesite ime povezave. 

1. Navedite veljaven ID odjemalca LiveRamp in skrivnost. 

1. Preberite in podajte soglasje za **Zasebnost podatkov in skladnost** tako, da potrdite polje **Strinjam se**. 

1. Izberite možnost **Potrdi** za potrditev konfiguracije. 

1. Za dokončanje povezave izberite **Shrani**. 

## <a name="enrichment-results"></a>Rezultati obogatitve 

Če želite začeti postopek obogatitve, v ukazni vrstici izberite Zaženi. Prav tako lahko dovolite, da sistem samodejno zažene obogatitev kot del a [načrtovana osvežitev](system.md#schedule-tab). Čas obdelave je odvisen od velikosti podatkov o stranki. 

Ko je postopek obogatitve končan, lahko pregledate podatke o novo obogatenih profilih strank pod **Moje obogatitve**. Poleg tega boste našli čas zadnje posodobitve in število obogatenih profilov. 

Do podrobnega pogleda vsakega obogatenega profila lahko dostopate z izbiro **Pogled obogaten** podatkov. 

## <a name="next-steps"></a>Naslednji koraki

Nadgradite svoje obogatene podatke o strankah. Uporabite ID-je AbiliTec za konsolidacijo profilov strank v osebni pogled. 
[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost 

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v LiveRamp dovolite prenos podatkov izven meja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo te podatke prenesel po vašem navodilu, vendar ste odgovorni za zagotovitev, da LiveRamp izpolnjuje vse vaše obveznosti glede zasebnosti ali varnosti. Za več informacij si oglejte [Microsoftova izjava o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732). Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadar koli odstrani in s tem prekini uporabo te funkcije. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
