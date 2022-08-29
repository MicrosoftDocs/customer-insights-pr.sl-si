---
title: Semantične preslikave (predogledna različica)
description: Pregled semantičnih preslikav in njihova uporaba.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 8780c11c8b091717349f0fd75a36b99c3a63ab49
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303896"
---
# <a name="semantic-mappings-preview"></a>Semantične preslikave (predogledna različica)

> [!NOTE]
> The **Semantične preslikave** Stran je na voljo samo za poslovna okolja (B-to-B), kjer so kontaktni profili že ustvarjeni s to stranjo. Še naprej lahko ustvarjate in upravljate posamezne profile stikov z uporabo **Semantične preslikave** strani. Ali pa [poenotite svoje kontaktne podatke](data-unification-contacts.md) za odstranjevanje dvojnikov, prepoznavanje ujemanj med entitetami in ustvarjanje enega poenotenega kontaktnega profila. Nato lahko uporabite poenoten kontaktni profil za ustvarjanje dejavnosti na ravni stika.

Semantične preslikave vam omogočajo preslikavo podatkov o nedejavnosti v vnaprej določene sheme. Te sheme pomagajo Customer Insights bolje razumeti atribute vaših podatkov. Semantično preslikavo in posredovani podatki omogočajo nove vpoglede in funkcije v Customer Insights. Če želite podatke o dejavnosti preslikati v sheme, preglejte dokumentacijo [dejavnosti](activities.md).

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

[!INCLUDE [footer-include](includes/footer-banner.md)]
