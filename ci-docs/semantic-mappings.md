---
title: Semantične preslikave (predogledna različica)
description: Pregled semantičnih preslikav in njihova uporaba.
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: b3a0643ab71c98ce212f4e4581a584d8382c67eb
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083152"
---
# <a name="semantic-mappings-preview"></a>Semantične preslikave (predogledna različica)

Semantične preslikave vam omogočajo preslikavo podatkov o nedejavnosti v vnaprej določene sheme. Te sheme pomagajo Customer Insights bolje razumeti atribute vaših podatkov. Semantično preslikavo in posredovani podatki omogočajo nove vpoglede in funkcije v Customer Insights. Če želite podatke o dejavnosti preslikati v sheme, preglejte dokumentacijo [dejavnosti](activities.md).

**Semantične preslikave so trenutno omogočene za okolja, ki temeljijo na poslovnih računih**. *KontaktProfil* je edina vrsta semantičnega preslikavanja, ki je trenutno na voljo v Customer Insights.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Določitev preslikave za semantično entiteto »ContactProfile«

1. Pojdi do **Podatki** > **Semantične preslikave (predogled)**.

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

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Upravljanje obstoječih semantičnih preslikav

V razdelku **Podatki** > **Semantične preslikave (predogledna različica)** si lahko ogledate vse shranjene semantične preslikave in jih upravljate. Vsako semantično preslikavo predstavlja ločena vrstica. Našli boste podrobnosti o izvorni entiteti, semantični vrsti, vrsti preslikave in njenem statusu.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Možnosti za upravljanje semantičnih preslikav.":::

- **Uredi**: odpre konfiguracijo nastavitve semantične preslikave v koraku pregleda. Spremenite lahko trenutno konfiguracijo. Izberite možnost **Shrani** in **Zaženi** za obdelavo sprememb.

- **Osveži**: osveži izbrano semantično preslikavo z najnovejšimi podatki iz entitet, ki so del njene konfiguracije. Če osvežite katero koli semantično preslikavo, boste osvežili vse semantične preslikave iste vrste.

- **Preimenuj**: odpre pogovorno okno, v katero lahko vnesete drugo ime za izbrano semantično preslikavo. Če želite uporabiti spremembe, izberite **Shrani**.

- **Izbriši**: odpre pogovorno okno za potrditev izbrisa izbrane semantične preslikave. Prav tako lahko izbrišete več kot eno semantično preslikavo hkrati, tako da izberete semantične preslikave in ikono za brisanje. Izberite možnost **Izbriši**, da pordite izbris.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Uporabite preslikavo semantične entitete ContactProfile za ustvarjanje dejavnosti na ravni stika

Po ustvarjanju a *KontaktProfil* semantično preslikavo entitet, lahko zajamete dejavnosti stikov. Omogoča vam, da na časovnici dejavnosti za račun vidite, kateri stik je bil odgovoren za posamezno dejavnost. Večina korakov sledi tipični konfiguraciji preslikave dejavnosti.

   > [!NOTE]
   > Da bi dejavnosti na ravni stika delovale, morate imeti oboje **ID računa** in **ID stika** atribute za vsak zapis znotraj vaših podatkov o dejavnosti.

1. [Definiraj a *KontaktProfil* preslikava semantičnih entitet.](#define-a-contactprofile-semantic-entity-mapping) In zaženite semantično preslikavo.

1. Pojdi do **Podatki** > **Dejavnosti**.

1. Izberite **Dodaj dejavnost** ustvariti novo dejavnost.

1. Poimenujte dejavnost, izberite izvorno entiteto dejavnosti in izberite primarni ključ entitete dejavnosti.

1. V **Odnosi** korak, ustvarite posredno razmerje med vašimi izvornimi podatki o dejavnosti in računi, pri čemer uporabite svoje kontaktne podatke kot posredniško enoto. Za več informacij glejte [neposrednih in posrednih odnosih](relationships.md#relationship-paths).
   - Primer razmerja za dejavnost, ki se imenuje *Nakupi*:
      - **Podatki o izvorni dejavnosti nakupov** > **Kontaktni podatki** na atribut **ID stika**
      - **Kontaktni podatki** > **Podatki o računu** na atribut **ID računa**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Primer postavitve razmerja.":::

1. Ko nastavite Odnosi, izberite **Naslednji** in dokončajte konfiguracijo preslikave dejavnosti. Za podrobne korake pri ustvarjanju dejavnosti glejte [opredeliti dejavnost](activities.md).

1. Zaženite svoje preslikave dejavnosti.

1. Vaše dejavnosti na ravni stika bodo zdaj vidne na časovnici vaše stranke.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Končni rezultat po konfiguraciji kontaktnih aktivnosti":::

### <a name="contact-level-activity-timeline-filtering"></a>Filtriranje časovne osi dejavnosti na ravni stika

Ko konfigurirate preslikavo dejavnosti na ravni stika in ga zaženete, bo časovnica dejavnosti za vaše stranke posodobljena. Vključuje njihove ID-je ali imena, odvisno od vašega *KontaktProfil* konfiguracijo za dejavnosti, na katere so delovali. Dejavnosti lahko filtrirate po stikih na časovnici, da vidite določene stike, ki vas zanimajo. Poleg tega si lahko ogledate vse dejavnosti, ki niso dodeljene določenemu stiku, tako da izberete **Dejavnosti, ki niso preslikane v stik**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Možnosti filtriranja so na voljo za dejavnosti na ravni stika.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
