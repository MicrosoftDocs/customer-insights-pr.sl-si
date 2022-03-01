---
title: Semantične preslikave (predogledna različica)
description: Pregled semantičnih preslikav in njihova uporaba.
ms.date: 09/28/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: b0884b8b6a2c5abe4b3967d1b57d11a3a6d65c5b
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 10/11/2021
ms.locfileid: "7622955"
---
# <a name="semantic-mappings"></a>Semantične preslikave

Semantične preslikave vam omogočajo preslikavo podatkov o nedejavnosti v vnaprej določene sheme. Te sheme pomagajo vpogledom v občinstvo, da bolje razumejo vaše atribute podatkov. Semantična preslikava in predloženi podatki omogočajo nove vpoglede in funkcije v vpogledih v občinstvo. Če želite podatke o dejavnosti preslikati v sheme, preglejte dokumentacijo [dejavnosti](activities.md).

**Semantične preslikave so trenutno omogočene za okolja, ki temeljijo na poslovnih računih**. *ContactProfile* je edina vrsta semantične preslikave, ki je trenutno na voljo v vpogledih v občinstvo.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Določitev preslikave za semantično entiteto »ContactProfile«

1. V vpogledih v občinstvo odprite razdelek **Podatki** > **Semantične preslikave (predogledna različica)**.

1. Izberite **Dodaj semantično preslikavo**, da začnete vodeno izkušnjo.

1. V koraku **Podatki entitete** nastavite vrednosti za naslednja polja:

   - **Ime preslikave za semantično entiteto**: vnesite ime preslikave za semantično entiteto.
   - **Izvorna entiteta**: izberite entiteto, ki vsebuje podatke za stik.
   - **Primarni ključ**: izberite polje, ki edinstveno določi zapis stika. Ne sme vsebovati podvojenih, praznih ali manjkajočih vrednosti.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Nastavite preslikavo za semantično entiteto z imenom, izvorno entiteto in primarnim ključem.":::

1. Če želite nadaljevati, izberite **Naprej**.

1. V koraku **Odnosi** konfigurirajte podrobnosti za povezavo vaših podatkov za stik z ustreznimi podatki o računu. V koraku so upodobljene povezave med entitetami.  

   Obstajata dve vrsti poti odnosov, ki jih je mogoče uporabiti: **Neposredni odnosi** in **Posredni odnosi**. Za več informacij pojdite na [neposredne in posredne poti odnosa](relationships.md#relationship-paths).

   1. Izberite **Dodaj odnos** in konfigurirajte odnos.
   1. Izberite atribut iz izvorne entitete, ki povezuje vašo entiteto stika z drugo entiteto.
   1. Izberite entiteto, s katero želite povezati svojo entiteto stika. Izberete lahko entiteto med razdelkom **Entiteta kupca** ali **Vmesna entiteta**. Če izberete vmesno entiteto, morate določiti drugi odnos za povezavo s ciljno entiteto kupca.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Izberite entiteto kupca ali vmesno entiteto.":::

   1. Vnesite **Ime odnosa**. Če odnos med vašimi entitetami že obstaja, je ime odnosa samo za branje. Če ne obstaja odnos, bo ustvarjen nov odnos z imenom, ki ga vnesete.
   1. Izberite **Uporabi**, da dokončate konfiguracijo odnosa.

   > [!NOTE]
   > Konfigurirate lahko več odnosov med entiteto stika in drugimi entitetami kupca z vmesnimi entitetami.
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Upodobitev različnih odnosov povezuje entitete stika z entitetami kupca.":::

1. Izberite **Naprej**, ko končate s konfiguracijo odnosa.

1. V koraku **Nastavitev semantične vrste** izberite **Semantična vrsta**. Trenutno obstaja ena **Semantična vrsta**, poimenovana *ContactProfile*.

1. Podatke preslikajte v *ContactProfile* **Semantična vrsta** za prikazana polja.
   - Obvezno polje: ID stika
   - Izbirna polja: ime, priimek, datum rojstva, spol, prvi e-poštni naslov in prva telefonska številka

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Atribute podatkov za stik preslikajte v predvidena obvezna in izbirna polja.":::

1. Če želite nadaljevati, izberite **Naprej**.

1. V koraku **Pregled** si oglejte konfiguracijo semantične preslikave. Izberite **Uredi** za ustrezni razdelek, da uveljavite spremembe.

1. Izberite **Shrani**, da shranite svojo novo **Semantično preslikavo**.

1. Po shranjevanju lahko izberete **Zagon**, da obdelate semantično preslikavo, ali pa izberite **Zapri**, da shranite svojo semantično preslikavo brez obdelave.

1. Če želite naknadno zagnati semantično preslikavo, izberite semantično preslikavo in izberite **Osveži**.

> [!TIP]
> Na voljo je [šest vrst stanja](system.md#status-types) za opravila/postopke. Poleg tega je večina postopkov [odvisna od drugih nadaljnjih postopkov](system.md#refresh-policies). Izberete lahko stanje postopka in si ogledate podrobnosti o poteku celotnega posla. Ko za enega izmed poslov izberete **Prikaži podrobnosti**, se prikažejo dodatne informacije: čas obdelave, zadnji datum obdelave ter vse napake in opozorila, povezana z opravilom.

## <a name="manage-existing-semantic-mappings"></a>Upravljanje obstoječih semantičnih preslikav

V razdelku **Podatki** > **Semantične preslikave (predogledna različica)** si lahko ogledate vse shranjene semantične preslikave in jih upravljate. Vsako semantično preslikavo predstavlja ločena vrstica. Našli boste podrobnosti o izvorni entiteti, semantični vrsti, vrsti preslikave in njenem statusu.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Možnosti za upravljanje semantičnih preslikav.":::

- **Uredi**: odpre konfiguracijo nastavitve semantične preslikave v koraku pregleda. Spremenite lahko trenutno konfiguracijo. Izberite možnost **Shrani** in **Zaženi** za obdelavo sprememb.

- **Osveži**: osveži izbrano semantično preslikavo z najnovejšimi podatki iz entitet, ki so del njene konfiguracije. Če osvežite katero koli semantično preslikavo, boste osvežili vse semantične preslikave iste vrste.

- **Preimenuj**: odpre pogovorno okno, v katero lahko vnesete drugo ime za izbrano semantično preslikavo. Če želite uporabiti spremembe, izberite **Shrani**.

- **Izbriši**: odpre pogovorno okno za potrditev izbrisa izbrane semantične preslikave. Prav tako lahko izbrišete več kot eno semantično preslikavo hkrati, tako da izberete semantične preslikave in ikono za brisanje. Izberite možnost **Izbriši**, da pordite izbris.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
