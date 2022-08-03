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
ms.openlocfilehash: 7c9588ac7a132ca6f43cf26ea3a744109a0dd2b8
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183651"
---
# <a name="semantic-mappings-preview"></a>Semantične preslikave (predogledna različica)

Semantične preslikave vam omogočajo preslikavo podatkov o nedejavnosti v vnaprej določene sheme. Te sheme pomagajo Customer Insights bolje razumeti atribute vaših podatkov. Semantično preslikavo in posredovani podatki omogočajo nove vpoglede in funkcije v Customer Insights. Če želite podatke o dejavnosti preslikati v sheme, preglejte dokumentacijo [dejavnosti](activities.md).

**Semantične preslikave so trenutno omogočene za okolja, ki temeljijo na poslovnih računih**. *ContactProfile* je edina vrsta semantične preslikave, ki je trenutno na voljo v Customer Insights.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Določitev preslikave za semantično entiteto »ContactProfile«

1. Pojdi do **podatki** > **Semantične preslikave (predogled)**.

1. Izberite **Dodaj semantično preslikavo**, da začnete vodeno izkušnjo.

1. V koraku **Podatki entitete** nastavite vrednosti za naslednja polja:

   - **Ime preslikave semantične entitete** : Ime za vašo preslikavo semantične entitete.
   - **Izvorna entiteta** : Entiteta, ki vključuje kontaktne podatke.
   - **Primarni ključ** : Polje, ki enolično identificira zapis stika. Ne sme vsebovati podvojenih, praznih ali manjkajočih vrednosti.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Nastavite preslikavo za semantično entiteto z imenom, izvorno entiteto in primarnim ključem.":::

1. Izberite **Naprej**.

1. V koraku **Odnosi** konfigurirajte podrobnosti za povezavo vaših podatkov za stik z ustreznimi podatki o računu. V koraku so upodobljene povezave med entitetami.  

   Obstajata dve vrsti poti odnosov, ki jih je mogoče uporabiti: **Neposredni odnosi** in **Posredni odnosi**. Za več informacij pojdite na [neposredne in posredne poti odnosa](relationships.md#relationship-paths).

   1. Izberite **Dodaj razmerje** za konfiguracijo razmerja.
   1. Izberite atribut iz izvorne entitete, ki povezuje vašo entiteto stika z drugo entiteto.
   1. Izberite entiteto, s katero želite povezati svojo entiteto stika. Izberite entiteto iz **Entitete računa** ali **Vmesna entiteta** razdelek. Če izberete vmesno entiteto, definirajte drugo razmerje za povezavo z vašo ciljno entiteto računa.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Izberite entiteto kupca ali vmesno entiteto.":::

   1. Vnesite **Ime odnosa**. Če odnos med vašimi entitetami že obstaja, je ime odnosa samo za branje. Če ne obstaja odnos, bo ustvarjen nov odnos z imenom, ki ga vnesete.
   1. Izberite **Uporabi**, da dokončate konfiguracijo odnosa.

   > [!NOTE]
   > Konfigurirate lahko več odnosov med entiteto stika in drugimi entitetami kupca z vmesnimi entitetami.
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Upodobitev različnih odnosov povezuje entitete stika z entitetami kupca.":::

1. Izberite **Naprej**.

1. V koraku **Nastavitev semantične vrste** izberite **Semantična vrsta**. Trenutno obstaja ena **Semantična vrsta**, poimenovana *ContactProfile*.

1. Preslikajte svoj kontaktni ID v *ContactProfile* pomenski tip **ID stika**. Po želji preslikajte druga polja, kot je ime, priimek, spol ali e-pošta.

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Atribute podatkov za stik preslikajte v predvidena obvezna in izbirna polja.":::

1. Izberite **Naprej**.

1. V **Pregled** koraku, preglejte konfiguracijo semantične preslikave. Za spremembe izberite **Uredi** za ustrezen razdelek.

1. Izberite **Shrani**.

1. Za obdelavo semantične preslikave izberite **Teči**. Ali izberite **Zapri** da shranite semantično preslikavo brez obdelave. Če ga želite zagnati pozneje, izberite semantično preslikavo in izberite **Osveži**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Upravljanje obstoječih semantičnih preslikav

Pojdi do **podatki** > **Semantične preslikave (predogled)** da si ogledate svoje shranjene semantične preslikave, njihovo izvorno entiteto, semantično vrsto, vrsto preslikave in status.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Možnosti za upravljanje semantičnih preslikav.":::

Za ogled razpoložljivih dejanj izberite semantično preslikavo.
- **Uredi** trenutno konfiguracijo. Izberite možnost **Shrani** in **Zaženi** za obdelavo sprememb.
- **Osveži** semantično preslikavo, ki vključuje najnovejše podatke. Če osvežite katero koli semantično preslikavo, boste osvežili vse semantične preslikave iste vrste.
- **Preimenuj** semantično preslikavo. Izberite **Shrani**.
- **Izbriši** semantično preslikavo. Če želite izbrisati več kot eno semantično preslikavo hkrati, izberite semantično preslikavo in ikono za brisanje. Izberite možnost **Izbriši**, da pordite izbris.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Uporabite preslikavo semantične entitete ContactProfile za ustvarjanje dejavnosti na ravni stika

Po ustvarjanju a *ContactProfile* semantično preslikavo entitet, lahko zajamete dejavnosti stikov. Omogoča vam, da na časovnici dejavnosti za račun vidite, kateri stik je bil odgovoren za posamezno dejavnost. Večina korakov sledi tipični konfiguraciji preslikave dejavnosti.

   > [!NOTE]
   > Da dejavnosti na ravni stika delujejo, morate imeti oboje **AccountID** in **ContactID** atribute za vsak zapis v vaših podatkih o dejavnosti.

1. [Določite a *ContactProfile* semantično preslikavo entitet](#define-a-contactprofile-semantic-entity-mapping) in zaženite semantično preslikavo.

1. Pojdi do **podatki** > **dejavnosti**.

1. Izberite **Dodaj dejavnost** ustvariti novo dejavnost.

1. Poimenujte dejavnost, izberite izvorno entiteto dejavnosti in izberite primarni ključ entitete dejavnosti.

1. V **Odnosi** koraku ustvarite posredno razmerje med podatki o izvoru dejavnosti in računi, pri čemer uporabite svoje kontaktne podatke kot posredniško entiteto. Za več informacij glejte [neposredne in posredne poti odnosov](relationships.md#relationship-paths).
   - Primer razmerja za dejavnost, imenovano *Nakupi*:
      - **Podatki o izvorni dejavnosti nakupov** > **Kontaktni podatki** na atributu **ContactID**
      - **Kontaktni podatki** > **Podatki o računu** na atributu **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Primer postavitve razmerja.":::

1. Po nastavitvi Odnosi izberite **Naslednji** in dokončajte konfiguracijo preslikave dejavnosti. Za podrobne korake o ustvarjanju dejavnosti glejte [določite dejavnost](activities.md).

1. Zaženite svoje preslikave dejavnosti.

1. Ko se zažene preslikava dejavnosti na ravni stika, izberite **Stranke**. Aktivnosti na ravni stika so prikazane na časovnici vaše stranke.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Končni rezultat po konfiguraciji dejavnosti stika":::

### <a name="contact-level-activity-timeline-filtering"></a>Filtriranje časovne premice dejavnosti na ravni stika

Časovnica dejavnosti za vaše stranke vključuje njihove ID-je ali imena, odvisno od vašega *ContactProfile* konfiguracijo, za dejavnosti, na katerih so ukrepali. Filtrirajte dejavnosti po stikih na časovnici, da si ogledate določene stike, ki vas zanimajo. Za ogled vseh dejavnosti, ki niso dodeljene določenemu stiku, izberite **Dejavnosti niso preslikane v stik**.

:::image type="content" source="media/Contact_Activities3.png" alt-text="Možnosti filtriranja so na voljo za dejavnosti na ravni stika.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
