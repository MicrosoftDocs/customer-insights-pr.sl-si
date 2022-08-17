---
title: Oglejte si konfiguracijo sistema
description: Preberite več o sistemskih nastavitvah v storitvi Dynamics 365 Customer Insights.
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 2498814a3d2e6330124fb97c036b9b310bcf1f7a
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246267"
---
# <a name="view-system-configuration"></a>Oglejte si konfiguracijo sistema

Oglejte si informacije o sistemu, stanje sistema in uporabo API-ja.

## <a name="view-api-usage"></a>Ogled uporabe API-ja

Oglejte si podrobnosti o uporabi API-ja v realnem času in poglejte, kateri dogodki so se zgodili v danem časovni okvir.

1. Pojdi do **skrbnik** > **Sistem** in izberite **uporaba API-ja** zavihek.

1. **Izberite časovni okvir** za ogled.

   The **uporaba API-ja** stran vsebuje tri razdelke:

   - **Klici API** – grafikon, ki prikazuje skupno število klicev API-ja v izbranem časovnem okviru.
   - **Prenos podatkov** – grafikon, ki prikazuje količino podatkov, ki so bili preneseni prek API-ja v izbranem časovnem okviru.
   - **Postopki** – tabela z vrsticami za vsak razpoložljiv postopek API-ja in podrobnosti o uporabi postopkov. Izberite ime operacije, na katero želite iti [referenco API-ja](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operacije, ki uporabljajo [vnos podatkov v realnem času](real-time-data-ingestion.md) vsebujejo simbol daljnogleda za ogled uporabe API-ja v realnem času.

   1. Izberite daljnogled, da ga odprete **Uporaba API-ja v realnem času** podokno s podrobnostmi o uporabi operacije.
   1. **Izberite časovni okvir** za ogled.
   1. Uporabi **Združi po** izberite, kako najbolje predstaviti svoje interakcije v realnem času. Združite podatke po API-ju **Metoda**, **ime subjekta** (zaužita entiteta), **Ustvaril** (vir dogodka), **Rezultat** (uspeh ali neuspeh) oz **Kode napak**. Podatki so na voljo kot grafikon zgodovine in kot tabela.

## <a name="view-system-information"></a>Ogled informacij o sistemu

Oglejte si okolje prikazno ime, ID, regijo, vrsto in ID seje.

1. Pojdi do **skrbnik** > **Sistem** in izberite **O tem** zavihek.

1. Za ogled jezika in države/regije izberite zavihek **Splošno**.

### <a name="update-preferred-language-or-countryregion"></a>Posodobite želeni jezik ali državo/regijo

Vpogledi strank [podpira veliko jezikov](/dynamics365/get-started/availability). Aplikacija uporablja vaše jezikovne nastavitve za prikaz elementov, kot so meni, besedilo oznake in sistemska sporočila, v vašem izbranem jeziku.

Uvoženi podatki in informacije, ki ste jih vnesli ročno, niso prevedeni.

1. Pojdi do **skrbnik** > **Sistem** in izberite **Splošno** zavihek.

1. Če želite spremeniti izbrani jezik, na spustnem meniju izberite možnost **Jezik**.

1. Če želite spremeniti izbrano oblikovanje datumov, časa in številk, uporabite spustni meni **Oblika zapisa države/regije**. Prikaže se predogled oblikovanja. Sistem samodejno predlaga izbiro, ko izberete nov jezik.

1. Izberite **Shrani**.

## <a name="view-system-status"></a>Prikaži stanje sistema

Spremljajte napredek nalog, vnos podatkov, izvoz podatkov in številne druge pomembne procese izdelka. Preglejte informacije, da zagotovite popolnost svojih aktivnih nalog in procesov.

1. Pojdi do **skrbnik** > **Sistem** in izberite **Stanje** zavihek.

   Status in informacije o obdelavi za prikaz različnih procesov. Oglejte si **Ime** naloge, **Stanje** njegovega zadnjega izvajanja in kdaj je bil **Zadnja posodobitev**.

1. Če si želite ogledati podrobnosti o zadnjih nekaj zagonih, izberite ime naloge ali procesa.

1. Če si želite ogledati podrobnosti napredka za opravilo, izberite stanje. The **Podrobnosti o napredku** zasloni v podoknu.

   :::image type="content" source="media/system-progress-details.png" alt-text="Podokno s podrobnostmi o napredku sistema":::

1. Za ogled podrobnosti napredka za vsa opravila izberite **Celoten potek dela**.

### <a name="status-definitions"></a>Definicije stanja

Sistem uporablja naslednje statuse za naloge in procese:

|Status  |Definicija  |
|---------|---------|
|Preklicano |Nalogo ali postopek je uporabnik preklical, preden se je končal.   |
|Neuspelo   |Pri opravilu ali procesu so se pojavile napake.         |
|Ni uspelo  |Naloga ali postopek ni uspel.  |
|Ni začeto   |Vir podatkov še nima vnesenih podatkov ali pa je opravilo še vedno v načinu osnutka.         |
|Predelava  |Naloga ali proces je v teku.  |
|Osveževanje    |Naloga ali proces je v teku. Za preklic te operacije izberite **Osvežujoče** in **Prekliči delo**. Če zaustavite osveževanje opravila ali procesa, se povrne v stanje zadnjega osveževanja.       |
|Preskočeno  |Naloga ali proces je bil preskočen. Eden ali več nadaljnjih postopkov, od katerih je odvisno opravilo, ne uspe ali ste jih preskočili.|
|Uspelo  |Opravilo ali proces je bil uspešno zaključen. Za vire podatkov označuje, da so bili podatki uspešno vneseni, če je čas omenjen v **Osvežena** stolpec.|
|V čakalni vrsti | Obdelava je v čakalni vrsti in se bo začela, ko bodo končana vsa opravila in procesi navzgor. Za več informacij glejte [Osveži procese](#refresh-processes).|

### <a name="refresh-processes"></a>Osveži procese

Osvežitev za naloge in procese se izvaja v skladu z [nastavljen urnik](schedule-refresh.md).

|Obdelaj  |Description  |
|---------|---------|
|Dejavnost  |Zažene se ročno (enkratna osvežitev). Odvisno od postopka spajanja. Vpogledi so odvisni od njegove obdelave.|
|Povezava analize |Zažene se ročno (enkratna osvežitev). Odvisno od segmentov.  |
|Priprava analize |Zažene se ročno (enkratna osvežitev). Odvisno od segmentov.  |
|Priprava podatkov   |Potrebuje entiteto za delovanje. Vir podatkov entitete so odvisne od zaužitja. Obogatene entitete so odvisne od obogatitev. Entiteta stranke je odvisna od združitve.  |
|Viri podatkov   |Ni odvisno od nobenega drugega postopka. Ujemanje je odvisno od uspešnega dokončanja tega postopka.  |
|Obogatitve   |Zažene se ročno (enkratna osvežitev). Odvisno od postopka spajanja. |
|Izvozne destinacije |Zažene se ročno (enkratna osvežitev). Odvisno od segmentov.  |
|Vpogledi |Zažene se ročno (enkratna osvežitev). Odvisno od segmentov.  |
|Obveščanje   |Odvisno od združitve.   |
|Povezovanje |Odvisno je od obdelave virov podatkov, uporabljenih v definiciji ujemanja.      |
|Mere  |Zažene se ročno (enkratna osvežitev). Odvisno od postopka spajanja.  |
|Spajanje   |Odvisno je od dokončanja postopka ujemanja. Segmenti, mere, obogatitev, iskanje, dejavnosti, predvidevanja in priprava podatkov so odvisni od uspešnega dokončanja tega postopka.   |
|Profili   |Zažene se ročno (enkratna osvežitev). Odvisno od postopka spajanja. |
|Poišči   |Zažene se ročno (enkratna osvežitev). Odvisno od postopka spajanja. |
|Segmenti  |Zažene se ročno (enkratna osvežitev). Odvisno od postopka spajanja. Vpogledi so odvisni od njegove obdelave.|
|Sistem   |Odvisno je od dokončanja postopka ujemanja. Segmenti, mere, obogatitev, iskanje, dejavnosti, predvidevanja in priprava podatkov so odvisni od uspešnega dokončanja tega postopka.   |
|uporabnik.  |Zažene se ročno (enkratna osvežitev). Odvisno od entitet.  |

Izberite stanje procesa, če si želite ogledati podrobnosti o napredku celotnega opravila, v katerem je bil. Zgornji postopki osveževanja lahko pomagajo razumeti, kaj lahko storite, da odpravite a **Preskočeno** oz **V čakalni vrsti** nalogo ali proces.


[!INCLUDE [footer-include](includes/footer-banner.md)]
