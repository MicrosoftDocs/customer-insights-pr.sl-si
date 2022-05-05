---
title: Obogatitev profilov podjetij z Dun & Bradstreet
description: Splošne informacije o obogatitvi tretjih oseb Dun & Bradstreet.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: ecbbf2c94020bf395f4eb70a99a63cea335af2dd
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653804"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Obogatitev profilov podjetij z Dun & Bradstreet (predogled)

Dun & Bradstreet ponuja komercialne podatke, analitiko in vpoglede za podjetja. Strankam omogoča poenoten profil strank, s katerimi podjetja obogatijo svoje podatke. Obogatitve vključujejo atribute, kot so številka DUNS, velikost podjetja, lokacija, industrija in drugo.

## <a name="prerequisites"></a>Zahteve

Za konfiguriranje obogatitve Dun & Bradstreet morajo biti izpolnjeni naslednji predpogoji:

- Imate aktivno [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) licenco.
- Za podjetja imate [poenotene profile strank](customer-profiles.md).
- Dun & Bradstreet [povezavo](connections.md) je konfiguriran s strani skrbnika. Lahko ga ustvarite, če ga imate [skrbnik](permissions.md#admin) dovoljenja in poverilnice Dun & Bradstreet Connect. 

## <a name="setting-up-your-dun--bradstreet-project"></a>Postavitev vašega projekta Dun & Bradstreet

Kot licencirani uporabnik Dun & Bradstreet lahko nastavite projekt v [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). 


1. Prijavite se v [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Za pridobitev poverilnic, [obnovite svoje geslo](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Prenesi [naša datoteka predloge csv](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) ki bo uporabljen za preslikavo polj občinstvo vpogledov v ustrezna polja Dun & Bradstreet. 

1. Naložite datoteko v **Naložite podatke** korak izkušnje ustvarjanja projekta Dun & Bradstreet. 

1. Izberite vodoravne pike pod ustreznimi **vir** v novoustvarjenem projektu Dun & Bradstreet, da si ogledate razpoložljive možnosti.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Posnetek zaslona pik v projektu Dun & Bradstreet.":::

1. Izberite **Pridobite podrobnosti o S3**. Te podatke shranite na varno mesto. Potrebovali boste [vzpostaviti povezavo za obogatitev](#configure-a-connection-for-dun--bradstreet) v občinstvo vpogledi. 

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Posnetek zaslona izbora informacij s3 v projektu Dun & Bradstreet.":::



## <a name="configure-the-enrichment"></a>Konfiguriranje obogatitve

1. Pri vpogledih v občinstvo izberite **Podatki** > **Obogatitev**.

1. Izberite **Obogatite moje podatke** na ploščici Dun & Bradstreet in izberite **Začeti**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Posnetek zaslona ploščice Dun & Bradstreet.":::

1. Na spustnem seznamu izberite možnost [povezava](connections.md). Če ni na voljo nobena povezava, se obrnite na skrbnika. Če ste skrbnik, lahko ustvarite povezavo. Izberite **Dodajte povezavo** in izberite **Dun & Bradstreet**. 

1. Izberite **Povežite se z Dun & Bradstreet** za potrditev povezave.

1. Izberite **Naslednji** in izberite **Stranka nabor podatkov** želite obogatiti s podatki o podjetju Dun & Bradstreet. Izberete lahko **Stranka** entiteto, da obogatite vse svoje profile strank, ali izberite entiteto segmenta, da obogatite samo poenotene profile strank, ki jih vsebuje ta segment.

1. Izberite **Naslednji** in določite, katera polja iz vaših enotnih profilov se uporabljajo za iskanje ustreznih podatkov podjetja Dun & Bradstreet. bodisi **DUNS številka** oz **Ime podjetja** in **Država** polja so obvezna. Polje države podpira [dvo- ali trimestne kode držav](https://www.iso.org/iso-3166-country-codes.html), ime države v angleščini, ime države v maternem jeziku in območno kodo. Nekatere pogoste različice držav vključujejo:

   * ZDA: Združene države Amerike, Združene države, ZDA, Amerika.
   * CA: Kanada.
   * VB: Združeno kraljestvo, UK, Velika Britanija, VB, Združeno kraljestvo Velike Britanije in Severne Irske, Združeno kraljestvo Velike Britanije.
   * AU: Avstralija, Commonwealth of Australia.
   * FR: Francija, Francoska republika.
   * DE: Nemčija, Nemčija, Deutschland, Allemagne, Zvezna republika Nemčija, Republika Nemčija.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Podokno za preslikavo polj Dun & Bradstreet.":::

1. Izberite možnost **Naprej**, da dokončate preslikavo polj.

1. Navedite ime obogatitve in po pregledu vaše izbire izberite možnost **Shrani obogatitev**.


## <a name="configure-a-connection-for-dun--bradstreet"></a>Konfigurirajte povezavo za Dun & Bradstreet 

Za konfiguriranje povezav morate biti skrbnik. Izberite **Dodajte povezavo** pri konfiguraciji obogatitve *oz* Pojdi do **Admin** > **Povezave** in izberite **Nastaviti** na ploščici Dun & Bradstreet.

1. Izberite **Začetek**. 

1. Vnesite ime povezave v polje za **prikazno ime**.

1. Navedite veljavne poverilnice Dun & Bradstreet in podrobnosti projekta Dun & Bradstreet *Regija, pot do mape in ime mape spusti*. ti [pridobite te informacije](#setting-up-your-dun--bradstreet-project) iz projekta Dun & Bradstreet.

1. Preglejte in podajte soglasje, tako da v razdelku **Zasebnost in skladnost podatkov** izberete možnost **Strinjam se**.

1. Izberite možnost **Potrdi** za potrditev konfiguracije.

1. Po zaključku potrjevanja izberite možnost **Shrani**.
   
   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Stran za konfiguracijo povezave Dun & Bradstreet.":::

## <a name="enrichment-results"></a>Rezultati obogatitve

Po osvežitvi obogatitve lahko pregledate novo obogatene podatke podjetja v razdelku [Moje obogatitve](enrichment-hub.md). Ogledate si lahko čas zadnje posodobitve in število obogatenih profilov.

Do podrobnega prikaza vsakega obogatenega profila lahko dostopate tako, da izberete **Ogled obogatenih podatkov**.

## <a name="next-steps"></a>Naslednji koraki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Dun & Bradstreet dovolite prenos podatkov izven meja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo te podatke prenesel po vašem navodilu, vendar ste odgovorni za zagotovitev, da Dun & Bradstreet izpolnjuje vse vaše obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadarkoli odstrani, s čimer je uporaba te funkcije prekinjena.


[!INCLUDE[footer-include](includes/footer-banner.md)]
