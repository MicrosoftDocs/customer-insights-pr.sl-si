---
title: Konfiguracija sistema v Customer Insights
description: Preberite več o sistemskih nastavitvah v storitvi Dynamics 365 Customer Insights.
ms.date: 04/21/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-schedule
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 3aa4c6529d705698e612adad86587e3c3a4db35b
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653636"
---
# <a name="system-configuration"></a>Konfiguracija sistema

Za dostop do sistemskih konfiguracij pojdite na **Admin** > **sistem** za ogled seznama sistemskih nalog in procesov.

Stran **Sistem** vključuje naslednje zavihke:
- [Status](#status-tab)
- [Urnik](#schedule-tab)
- [Uporaba API-ja](#api-usage-tab)
- [Vizitka](#about-tab)
- [Splošno](#general-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Zavihki z nastavitvami na sistemski strani.":::

## <a name="status-tab"></a>Zavihek stanja

The **Zavihek Status** omogoča spremljanje napredka opravil, vnosa podatkov, izvoza podatkov in več drugih pomembnih procesov izdelka. Preglejte informacije na tem zavihku, da zagotovite popolnost svojih aktivnih nalog in procesov.

Ta zavihek vključuje tabele s podatki o stanju in obdelavi za različne procese. Vsaka tabela spremlja **Ime** opravila in njegove ustrezne entitete, **Stanje** njegovega zadnjega izvajanja in datum **Zadnje posodobitve**. Podrobnosti zadnjih nekaj zagonov si lahko ogledate tako, da izberete ime opravila ali procesa. 

Izberite stanje poleg opravila ali procesa v **Stanje** stolpec, da odprete **Podrobnosti o napredku** podokno.

   :::image type="content" source="media/system-progress-details.png" alt-text="Podokno s podrobnostmi o napredku sistema":::

### <a name="status-definitions"></a>Definicije statusa

Sistem uporablja naslednja stanja za opravila in procese:

|Status  |Definicija  |
|---------|---------|
|Preklicano |Uporabnik je obdelavo preklical, preden se je končala.   |
|Neuspelo   |Pri uvozu podatkov je prišlo do napak.         |
|Ni uspelo  |Obdelava ni uspela.  |
|Ni začeto   |Vir podatkov še nima vključenih podatkov ali je še v načinu osnutka.         |
|Predelava  |Naloga ali proces je v teku.  |
|Osveževanje    |Uvažanje podatkov je v teku. Ta postopek lahko prekličete tako, da v stolpcu **Dejanja** izberete **Ustavi osveževanje**. Ustavitev osveževanja vira podatkov bo povrnjena na zadnje stanje osveževanja.       |
|Preskočeno  |Naloga ali proces je bil preskočen. Eden ali več nadaljnjih postopkov, od katerih je odvisno opravilo, ne uspe ali ste jih preskočili.|
|Uspelo  |Naloga ali proces je uspešno zaključen. Za vire podatkov označuje, da so bili podatki uspešno prevzeti, če je čas omenjen v **Osveženo** stolpec.|
|V čakalni vrsti | Obdelava je v čakalni vrsti in se bo začela, ko bodo končana vsa nadaljnja opravila in procesi. Za več informacij glejte [Osvežite procese](#refresh-processes).|

### <a name="refresh-processes"></a>Osvežite procese

Osvežitev nalog in procesov se izvaja v skladu z [konfiguriran urnik](#schedule-tab). 

|Obdelaj  |Description  |
|---------|---------|
|Dejavnost  |Teče ročno (enkratna osvežitev). Odvisno od postopka spajanja. Vpogledi so odvisni od njegove obdelave.|
|Povezava analize |Teče ročno (enkratna osvežitev). Odvisno od segmentov.  |
|Priprava analize |Teče ročno (enkratna osvežitev). Odvisno od segmentov.  |
|Priprava podatkov   |Za delovanje potrebuje entiteto. Entitete vir podatkov so odvisne od zaužitja. Obogatene entitete so odvisne od obogatitev. Entiteta stranke je odvisna od združitve.  |
|Viri podatkov   |Ni odvisno od nobenega drugega postopka. Ujemanje je odvisno od uspešnega dokončanja tega postopka.  |
|Obogatitve   |Teče ročno (enkratna osvežitev). Odvisno od postopka spajanja. |
|Izvozne destinacije |Teče ročno (enkratna osvežitev). Odvisno od segmentov.  |
|Vpogledi |Teče ročno (enkratna osvežitev). Odvisno od segmentov.  |
|Obveščanje   |Odvisno od združitve.   |
|Povezovanje |Odvisno je od obdelave virov podatkov, uporabljenih v definiciji ujemanja.      |
|Mere  |Teče ročno (enkratna osvežitev). Odvisno od postopka spajanja.  |
|Spajanje   |Odvisno je od dokončanja postopka ujemanja. Segmenti, mere, obogatitev, iskanje, dejavnosti, predvidevanja in priprava podatkov so odvisni od uspešnega dokončanja tega postopka.   |
|Profili   |Teče ročno (enkratna osvežitev). Odvisno od postopka spajanja. |
|Poišči   |Teče ročno (enkratna osvežitev). Odvisno od postopka spajanja. |
|Segmenti  |Teče ročno (enkratna osvežitev). Odvisno od postopka spajanja. Vpogledi so odvisni od njegove obdelave.|
|Sistem   |Odvisno je od dokončanja postopka ujemanja. Segmenti, mere, obogatitev, iskanje, dejavnosti, predvidevanja in priprava podatkov so odvisni od uspešnega dokončanja tega postopka.   |
|uporabnik.  |Teče ročno (enkratna osvežitev). Odvisno od subjektov.  |

Izberite stanje procesa, da si ogledate podrobnosti o napredku celotnega opravila, v katerem je bil. Zgornji postopki osveževanja vam lahko pomagajo razumeti, kaj lahko storite za reševanje a **Preskočeno** oz **V čakalni vrsti** nalogo ali proces.

## <a name="schedule-tab"></a>Zavihek razporeda

Uporabite zavihek **Razpored** za razporejanje samodejnih osveževanj za vse [vnesene vire podatkov](data-sources.md). Samodejno osveževanje pomaga zagotoviti, da se posodobitve iz virov podatkov odražajo v vaših poenotenih profilih strank.

> [!NOTE]
> Viri podatkov, ki jih upravljate, se osvežujejo po svojih urnikih. Če želite načrtovati osveževanje virov podatkov, ki jih upravljate, konfigurirajte nastavitve osveževanja za to določeno vir podatkov iz **Viri podatkov** stran.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Nastavitve osveževanja podatkovnega toka.":::

1. Pojdi do **Admin** > **sistem** in izberite **Urnik** zavihek.

2. Privzeto stanje za načrtovano osvežitev je **Izklopljeno**. Če želite omogočiti razporejena osveževanja, spremenite preklop na vrhu zaslona na **Vklopljeno**.

3. Za osveževanja lahko izberete **Tedensko** (privzeto) in **Dnevno**. Če nameravate razporediti tedenska osveževanja, izberite en ali več dni, ko želite zagnati osveževanje.

4. Nastavite svoj **Časovni pas**, nato uporabite spustni meni **Ura**, da nastavite uro osveževanja. Ko končate, izberite **Nastavi**. Če želite razporediti več osveževanj v enem dnevu, izberite **Dodajte drug čas**.

5. Če želite uporabiti spremembe, izberite **Shrani**.

## <a name="about-tab"></a>Zavihek vizitke

Zavihek **Več o tem** vsebuje **Prikazno ime** vaše organizacije, dejavni **ID okolja**, **Regijo** in tvoj **ID seje**. Če imate več delovnih okolij, morate vsakemu dati zlahka prepoznavno prikazno ime.

## <a name="general-tab"></a>Zavihek Splošno

Obliko jezika in države/regije lahko spremenite v zavihku **Splošno**.

Vpogled v stranke [podpira številne jezike](/dynamics365/get-started/availability). Aplikacija uporablja vaše jezikovne nastavitve za prikaz elementov, kot so meni, besedilo oznake in sistemska sporočila, v vašem izbranem jeziku.

Uvoženi podatki in informacije, ki ste jih vnesli ročno, niso prevedeni.

### <a name="update-the-settings"></a>Posodobi nastavitve

Če želite spremeniti izbrani jezik, na spustnem meniju izberite možnost **Jezik**.

Če želite spremeniti izbrano oblikovanje datumov, časa in številk, uporabite spustni meni **Oblika zapisa države/regije**. Pod tem poljem se prikaže predogled oblikovanja. Sistem bo samodejno predlagal izbiro, ko izberete nov jezik.

Izberite **Shrani**, da potrdite izbiro.

## <a name="api-usage-tab"></a>Zavihek uporabe API-ja

Poiščite podrobnosti sprotne uporabe API-ja in si oglejte dogodke, ki so se zgodili v danem časovnem okvirju. V spustnem meniju **Izberite časovni okvir** izberite časovni okvir. 

Razdelek **Uporaba API-ja** vsebuje tri razdelke: 
- **Klici API** – grafikon, ki prikazuje skupno število klicev API-ja v izbranem časovnem okviru.

- **Prenos podatkov** – grafikon, ki prikazuje količino podatkov, ki so bili preneseni prek API-ja v izbranem časovnem okviru.

-  **Postopki** – tabela z vrsticami za vsak razpoložljiv postopek API-ja in podrobnosti o uporabi postopkov. Izberete lahko ime postopka, da obiščete [sklice API-ja](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operacije, ki uporabljajo [zaužitje podatkov v realnem času](real-time-data-ingestion.md) vsebujejo gumb z binokularnim simbolom za ogled uporabe API-ja v realnem času. Izberite gumb, da odprete stransko podokno s podrobnostmi o uporabi za sprotno uporabo API-ja v trenutnem okolju.   
   V podoknu **Sprotna uporaba API-ja** uporabite polje **Združi po**, da izberete, kako najbolje predstaviti svoje interakcije v realnem času. Podatke lahko združite po metodi API-ja, določenem imenu entitete (uvožena entiteta), avtorju ustvarjanja (vir dogodka), rezultatu (uspeh ali neuspeh) ali kodah napak. Podatki so na voljo kot grafikon zgodovine in kot tabela.


[!INCLUDE [footer-include](includes/footer-banner.md)]