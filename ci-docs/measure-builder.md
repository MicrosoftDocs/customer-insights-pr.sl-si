---
title: Ustvarite mere z graditeljem mer
description: Zgradite meritve iz nič za analizo ključnih meritev o vašem podjetju.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: fac00b8a1b4ca6e09dd29abe46dfe240adcc029e
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170885"
---
# <a name="create-measures-with-measure-builder"></a>Ustvarite mere z graditeljem mer

Measure builder vam omogoča definiranje izračunov z uporabo matematičnih operatorjev, funkcij združevanja in filtrov. Definirajte mere z uporabo atributov iz entitet, ki so povezane z enotnim *Stranka* entiteta.

Ustvarjanje mer v okoljih B-to-C in B-to-B deluje na enak način. Vendar, če vaše B-to-B okolje [uporablja račune s hierarhijami](relationships.md#set-up-account-hierarchies), izberite, ali želite meritev združiti v povezanih podračunih.

# <a name="individual-consumers-b-to-c"></a>[Posamezni potrošniki (prodaja strankam)](#tab/b2c)

Izdelajte mere na ravni posameznega kupca (atribut kupca, meritev kupca) ali na ravni podjetja/organizacije (poslovni ukrep). Atribut stranke in meritev stranke vam omogočata sledenje uspešnosti na stranko. Na primer skupna poraba posamezne stranke. Poslovne meritve spremljajo uspešnost posameznega podjetja. Na primer skupni prihodek podjetja.

- Atribut stranke: ustvari izhod kot nov atribut, ki se shrani kot nov stolpec v sistemsko ustvarjeni entiteti z imenom *Customer_Measure*. Pri osveževanju atributa stranke se vsi drugi atributi stranke v *Customer_Measure* istočasno osveževanje entitete. Poleg tega so atributi stranke prikazani na kartici profila stranke. Ko je atribut zagnan ali shranjen, ne morete spremeniti atributa stranke v mero stranke.

- Mera stranke: ustvari izhod kot lastno entiteto in je ne morete spremeniti v atribut stranke, ko je enkrat zagnan ali shranjen. Mere stranke niso prikazane na kartici profila stranke.

- Poslovni ukrep: ustvari izhod kot lastno entiteto in se prikaže na domači strani vašega okolja Customer Insights.

1. Pojdi do **Ukrepi**.

1. Izberite **Novo** > **Ustvarite svojo**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Prazen konfiguracijski zaslon za meritev od B do C." lightbox="media/measure-b2c.png":::

1. Izberite **Uredi podrobnosti** poleg Ukrep brez naslova. Vnesite ime za mero. Po želji dodajte [oznake](work-with-tags-columns.md#manage-tags) po meri.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Pogovorno okno za urejanje podrobnosti.":::

1. Izberite **Dokončano**.

1. Če želite slediti uspešnosti na poslovni ravni, preklopite **Vrsta meritve** do **Poslovni nivo**. **Raven stranke** je privzeto izbrano. **Raven stranke** samodejno doda *Identifikacijska številka stranke* atribut Dimensions medtem ko **Poslovni nivo** samodejno odstrani.

1. V konfiguracijskem območju izberite funkcijo združevanja iz **Izberite funkcijo** spustni meni. Združevalne funkcije vključujejo:
   - **Vsota**
   - **Povprečje**
   - **Število**
   - **Št. enoličnih**
   - **Maksimum**
   - **Min**
   - **Najprej**: vzame prvo vrednost podatkovnega zapisa
   - **Zadnje**: vzame zadnjo vrednost, ki je bila dodana v podatkovni zapis
   - **ArgMax** : najde podatkovni zapis, ki daje največjo vrednost ciljne funkcije
   - **ArgMin** : najde podatkovni zapis, ki daje najmanjšo vrednost iz ciljne funkcije

1. Izberite **Dodaj atribut** da izberete podatke za ustvarjanje te mere.

   1. Izberite zavihek **Atributi**.
   1. Podatkovna entiteta: izberite entiteto, ki vključuje atribut, ki ga želite izmeriti.
   1. Atribut podatkov: izberite atribut, ki ga želite uporabiti v združevalni funkciji za izračun mere. Naenkrat lahko izberete le en atribut.
   1. Po želji lahko izberete podatkovni atribut iz obstoječe mere, tako da izberete **Ukrepi** ali poiščite ime entitete ali mere.
   1. Izberite **Dodaj**.

1. Če želite zgraditi bolj zapletene mere, dodajte več atributov ali uporabite matematične operatorje v svoji funkciji merjenja.

1. Če želite dodati filtre, v konfiguracijskem območju izberite možnost **Filter**. Uporaba filtrov bo za izračun mere uporabila le zapise, ki se ujemajo s filtri.
  
   1. V razdelku **Dodaj atribut**, in sicer v podoknu **Filtri**, izberite atribut, ki ga želite uporabiti za ustvarjanje filtrov.
   1. Nastavite operatorje filtrov, da določite filter za vsak izbrani atribut.
   1. Izberite **Uporabi**.

1. Izberite **Dimenzija** da izberete več polj, ki jih želite dodati kot stolpce izhodni entiteti mere.

   1. Izberite možnost **Uredi razsežnosti**, da dodate atribute podatkov, po katerih želite vrednosti mer razvrstiti v skupine. Na primer po mestu ali spolu.
      > [!TIP]
      > Če ste izbrali **Raven stranke** kot **Vrsta meritve** the *Identifikacijska številka stranke* atribut je že dodan. Če odstranite atribut, **Vrsta meritve** preklopi na **Poslovni nivo**.
   1. Izberite **Dokončano**.

1. Če so v vaših podatkih vrednosti, ki jih je treba nadomestiti s celim številom, izberite **Pravila**. Konfigurirajte pravilo in se prepričajte, da jih nadomestite le s celimi števili. Zamenjajte na primer *null* z *0*.

1. Če obstaja več poti med podatkovno entiteto, ki ste jo preslikali, in *Stranka* subjekt, izberite enega od identificiranih [poti odnosov entitet](relationships.md). Rezultati mere se lahko razlikujejo glede na izbrano pot.

   1. Izberite **Pot odnosa** in nato pot entitete, ki jo je treba uporabiti za identifikacijo vaše mere. Če obstaja samo ena pot do entitete *stranke*, ta nadzor ne bo prikazan.
   1. Izberite **Dokončano**.

1. Če želite dodati več izračunov za mero, izberite možnost **Nov izračun**. Za nove izračune uporabite samo entitete na isti poti entitete. Dodatni izračuni bodo prikazani kot novi stolpci v entiteti izhodnih mer. Po želji izberite **Uredi ime** da ustvarite ime za izračun.

1. Izberite navpično elipso (&vellip;) o izračunu do **Dvojnik** oz **Odstrani** izračun iz mere.

1. Na območju **predogleda** boste videli podatkovno shemo entitete izhodnih mer, vključno s filtri in razsežnostmi. Predogled se dinamično odziva na spremembe v konfiguraciji.

1. Izberite možnost **Zaženi** za izračun rezultatov za konfigurirano mero. Izberite možnost **Shrani in zapri**, če želite obdržati trenutno konfiguracijo in mero zagnati pozneje. The **Ukrepi** prikazi strani.

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (podjetja podjetjem)](#tab/b2b)

Izdelajte mere na nivoju posameznih računov (mera kupca) ali na ravni vseh računov (mera podjetja).

- Ukrep za stranko: ustvarja rezultat kot lastno entiteto. Mere stranke niso prikazane na kartici profila stranke.

- Poslovni ukrep: ustvari izhod kot lastno entiteto in se prikaže na domači strani vašega okolja Customer Insights.

1. Pojdi do **Ukrepi**.

1. Izberite **Novo**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Prazen konfiguracijski zaslon za meritev B-to-B.":::

1. Izberite **Uredi podrobnosti** poleg Ukrep brez naslova. Vnesite ime za mero. Po želji dodajte [oznake](work-with-tags-columns.md#manage-tags) po meri. 
   :::image type="content" source="media/measures_edit_details.png" alt-text="Pogovorno okno za urejanje podrobnosti.":::

1. Izberite **Dokončano**.

1. V konfiguracijskem območju izberite funkcijo združevanja iz **Izberite funkcijo** spustni meni. Združevalne funkcije vključujejo:
   - **Vsota**
   - **Povprečje**
   - **Število**
   - **Št. enoličnih**
   - **Maksimum**
   - **Min**
   - **Najprej**: vzame prvo vrednost podatkovnega zapisa
   - **Zadnje**: vzame zadnjo vrednost, ki je bila dodana v podatkovni zapis

1. Izberite **Dodaj atribut** da izberete podatke za ustvarjanje te mere.

   1. Izberite zavihek **Atributi**.
   1. Podatkovna entiteta: izberite entiteto, ki vključuje atribut, ki ga želite izmeriti.
   1. Atribut podatkov: izberite atribut, ki ga želite uporabiti v združevalni funkciji za izračun mere. Naenkrat lahko izberete le en atribut.
   1. Po želji lahko izberete podatkovni atribut iz obstoječe mere, tako da izberete **Ukrepi** ali poiščite ime entitete ali mere.
   1. Izberite možnost **Dodaj**, da meri dodate izbrani atribut.

1. Če želite zgraditi bolj zapletene mere, dodajte več atributov ali uporabite matematične operatorje v svoji funkciji merjenja.

1. Če želite dodati filtre, v konfiguracijskem območju izberite možnost **Filter**. Uporaba filtrov bo za izračun mere uporabila le zapise, ki se ujemajo s filtri.
  
   1. V razdelku **Dodaj atribut**, in sicer v podoknu **Filtri**, izberite atribut, ki ga želite uporabiti za ustvarjanje filtrov.
   1. Nastavite operatorje filtrov, da določite filter za vsak izbrani atribut.
   1. Izberite možnost **Dodaj**, da meri dodate filter.

1. Izberite **Dimenzija** da izberete več polj, ki jih želite dodati kot stolpce izhodni entiteti mere.

   1. Izberite možnost **Uredi razsežnosti**, da dodate atribute podatkov, po katerih želite vrednosti mer razvrstiti v skupine. Na primer po mestu ali spolu.
      > [!TIP]
      > The *Identifikacijska številka stranke* atribut je že dodan, kar pomeni, da gre za vrsto meritve na ravni stranke. Če odstranite atribut, se vrsta ukrepa spremeni v poslovno raven.
   1. Izberite možnost **Končano**, da meri dodate razsežnosti.

1. Če so v vaših podatkih vrednosti, ki jih je treba nadomestiti s celim številom, izberite **Pravila**. Konfigurirajte pravilo in se prepričajte, da jih nadomestite le s celimi števili. Zamenjajte na primer *null* z *0*.

1. Če ti [uporabite račune s hierarhijami](relationships.md#set-up-account-hierarchies), pregled **Združite podračune**.
   - Če je nastavljen na **Izklopljeno**, se mera izračuna za vsak račun. Vsak račun dobi svoj rezultat.
   - Če je nastavljen na **Vklopljeno**, izberite **Uredi** za izbiro hierarhije računa glede na uvožene hierarhije. Ukrep bo dal le en rezultat, ker je združen s podračuni.

1. Če obstaja več poti med podatkovno entiteto, ki ste jo preslikali, in *Stranka* subjekt, izberite enega od identificiranih [poti odnosov entitet](relationships.md). Rezultati mere se lahko razlikujejo glede na izbrano pot.

   1. Izberite **Pot odnosa** in nato pot entitete, ki jo je treba uporabiti za identifikacijo vaše mere. Če obstaja samo ena pot do entitete *stranke*, ta nadzor ne bo prikazan.
   1. Izberite možnost **Končano**, da uporabite izbor.

1. Izberite navpično elipso (&vellip;) o izračunu do **Dvojnik** oz **Odstrani** izračun iz mere.

1. Na območju **predogleda** boste videli podatkovno shemo entitete izhodnih mer, vključno s filtri in razsežnostmi. Predogled se dinamično odziva na spremembe v konfiguraciji.

1. Izberite možnost **Zaženi** za izračun rezultatov za konfigurirano mero. Izberite možnost **Shrani in zapri**, če želite obdržati trenutno konfiguracijo in mero zagnati pozneje. The **Ukrepi** prikazi strani.

---

## <a name="next-step"></a>Naslednji korak

Za ustvarjanje uporabite obstoječe ukrepe [segment strank](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
