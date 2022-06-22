---
title: Povezovanje podatkov Common Data Model z računom Azure Data Lake
description: Delo s podatki Common Data Model z uporabo storitve Azure Data Lake Storage.
ms.date: 05/30/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: 2ab7ec77252be33f1203959c2a596ddec20425f2
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011593"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Vzpostavljanje povezave s podatki v storitvi Azure Data Lake Storage

Vnesite podatke v Dynamics 365 Customer Insights z uporabo svojega Azure Data Lake Storage Račun 2. generacije. Zaužitje podatkov je lahko polno ali postopoma.

## <a name="prerequisites"></a>Zahteve

- Podpira vnos podatkov Azure Data Lake Storage *Gen2* izključno račune. Za vnos podatkov ne morete uporabiti računov Data Lake Storage Gen1.

- The Azure Data Lake Storage račun mora imeti [Imenski prostor hierarhičen je omogočen](/azure/storage/blobs/data-lake-storage-namespace). Podatki morajo biti shranjeni v formatu mape hierarhičen, ki definira korensko mapo in ima podmape za vsako entiteto. Podmape imajo lahko polne podatke ali mape z inkrementalnimi podatki.

- Če želite preveriti pristnost z glavnim imenom storitve Azure, preverite, ali je konfiguriran v najemniku. Za več informacij glejte [Povežite se z an Azure Data Lake Storage Račun 2. generacije z principalom storitve Azure](connect-service-principal.md).

- The Azure Data Lake Storage iz katerih se želite povezati in prevzeti podatke, morajo biti v isti regiji Azure kot Dynamics 365 Customer Insights okolje. Povezave do mape Common Data Model iz jezera podatkov v drugi regiji Azure niso podprte. Če želite poznati Azurno regijo okolja, pojdite na **Admin** > **sistem** > **O** v Customer Insights.

- Podatki, shranjeni v spletnih storitvah, so lahko shranjeni na drugi lokaciji kot tam, kjer se podatki obdelujejo ali shranjujejo Dynamics 365 Customer Insights.Z uvozom ali povezovanjem s podatki, shranjenimi v spletnih storitvah, se strinjate, da se lahko podatki prenašajo in shranjujejo Dynamics 365 Customer Insights . [Več o tem v Microsoftovem centru za zaupanje](https://www.microsoft.com/trust-center).

- Za dostop do računa za shranjevanje mora biti principal storitve Customer Insights v eni od naslednjih vlog. Za več informacij glejte [Dodelite dovoljenja ravnatelju storitve za dostop do računa za shranjevanje](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account).
  - Bralnik podatkov shrambe zbirke dvojiških podatkov
  - Lastnik podatkov shrambe zbirke dvojiških podatkov
  - Sodelujoči v shrambi zbirke dvojiških podatkov

- Podatki v vašem Data Lake Storageu morajo slediti standardu skupnega podatkovnega modela za shranjevanje vaših podatkov in imeti manifest skupnega podatkovnega modela, ki predstavlja shemo podatkovnih datotek (*.csv ali *.parquet). Manifest mora vsebovati podrobnosti o entitetah, kot so stolpci entitet in tipi podatkov ter lokacija podatkovne datoteke in vrsta datoteke. Za več informacij glejte [Manifest skupnega podatkovnega modela](/common-data-model/sdk/manifest). Če manifest ni prisoten, lahko skrbniški uporabniki z dostopom Lastnik podatkov blob podatkov shranjevanja ali dostop sodelavec definirajo shemo pri zaužitju podatkov.

## <a name="connect-to-azure-data-lake-storage"></a>Vzpostavljanje povezave s storitvijo Azure Data Lake Storage

1. Pojdite na **Podatki** > **Viri podatkov**.

1. Izberite **Dodaj vir podatkov**.

1. Izberite **Shramba podatkovnega jezera Azure**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Pogovorno okno za vnos podrobnosti povezave za Azure Data Lake." lightbox="media/data_sources_ADLS.png":::

1. Vnesite a **ime** za vir podatkov in izbirno **Opis**. Ime enolično identificira vir podatkov in se sklicuje na nadaljnjih procesih in ga ni mogoče spremeniti.

1. Izberite eno od naslednjih možnosti za **Povežite svoj prostor za shranjevanje s pomočjo**. Za več informacij glejte [Povežite Customer Insights z Azure Data Lake Storage Račun 2. generacije z principalom storitve Azure](connect-service-principal.md).

   - **Vir Azure** : Vnesite **Id. vira** . Izbirno, če želite prenesti podatke iz računa za shranjevanje prek zasebne povezave Azure, izberite **Omogoči zasebno povezavo**. Za več informacij glejte [Zasebne povezave](security-overview.md#private-links-tab).
   - **Naročnina na Azure** : Izberite **Naročnina** in nato **Skupina virov** in **Račun za shranjevanje**. Izbirno, če želite prenesti podatke iz računa za shranjevanje prek zasebne povezave Azure, izberite **Omogoči zasebno povezavo**. Za več informacij glejte [Zasebne povezave](security-overview.md#private-links-tab).
  
   > [!NOTE]
   > Za ustvarjanje vir podatkov potrebujete eno od naslednjih vlog za vsebnik ali račun za shranjevanje:
   >
   >  - Podatki shranjevalnih blokov Uporabnik z dovoljenjem za branje zadostujejo za branje iz računa za shranjevanje in vnos podatkov v Customer Insights. 
   >  - Podatki shranjevalnih blokov sodelavec ali lastnik so potrebni, če želite datoteke manifestov urejati neposredno v Customer Insights.  
  
1. Izberite ime za **Vsebnik** ki vsebuje podatke in shemo (datoteka model.json ali manifest.json) za uvoz podatkov in izberite **Naslednji**.
   > [!NOTE]
   > Vsaka datoteka model.json ali manifest.json, povezana z drugim virom podatkov v okolju, ne bo prikazana na seznamu. Vendar pa je isto datoteko model.json ali ali manifest.json mogoče uporabiti za vire podatkov v več okoljih.

1. Če želite ustvariti novo shemo, pojdite na [Ustvarite novo datoteko sheme](#create-a-new-schema-file).

1. Če želite uporabiti obstoječo shemo, se pomaknite do mape, ki vsebuje datoteko model.json ali manifest.cdm.json. Datoteko lahko poiščete v imeniku.

1. Izberite datoteko json in izberite **Naslednji**. Prikaže se seznam razpoložljivih entitet.

   :::image type="content" source="media/review-entities.png" alt-text="Pogovorno okno s seznamom entitet, ki jih želite izbrati":::

1. Izberite entitete, ki jih želite vključiti.

   :::image type="content" source="media/ADLS_required.png" alt-text="Pogovorno okno, ki prikazuje Zahtevano za primarni ključ":::

   > [!TIP]
   > Če želite urediti entitete v vmesniku za urejanje JSON, izberite **Pokaži več** > **Uredite datoteko sheme**. Izvedite spremembe in izberite **Shrani**.

1. Za izbrane entitete, ki zahtevajo postopno zaužitje, **Obvezno** prikaže pod **Postopno osveževanje**. Za vsako od teh entitet glej [Konfigurirajte postopno osveževanje za vire podatkov Azure Data Lake](incremental-refresh-data-sources.md).

1. Za izbrane entitete, pri katerih primarni ključ ni bil definiran, **Obvezno** prikaže pod **Primarni ključ**. Za vsakega od teh subjektov:
   1. Izberite **Obvezno**. The **Uredi entiteto** panelni zasloni.
   1. Izberite **Primarni ključ**. Primarni ključ je edinstven atribut za entiteto. Atribut je veljaven primarni ključ samo v primeru, če ne vsebuje podvojenih vrednosti, manjkajočih vrednosti ali ničelnih vrednosti. Kot primarni ključi so podprti atributi vrste podatkov niz, celo število in GUID.
   1. Po želji spremenite vzorec particije.
   1. Izberite **Zapri** da shranite in zaprete ploščo.

1. Izberite število **Lastnosti** za vsako vključeno entiteto. The **Upravljajte atribute** prikaže stran.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Pogovorno okno za izbiro profiliranja podatkov.":::

   1. Ustvarite nove atribute, uredite ali izbrišite obstoječe atribute. Spremenite lahko ime, obliko podatkov ali dodate pomensko vrsto.
   1. Če želite omogočiti analitiko in druge zmogljivosti, izberite **Profiliranje podatkov** za celotno entiteto ali za posebne atribute. Privzeto nobena entiteta ni omogočena za profiliranje podatkov.
   1. Izberite **Dokončano**.

1. Izberite **Shrani**. The **Viri podatkov** odpre se stran z novim vir podatkov v **Osvežujoče** stanje.

### <a name="create-a-new-schema-file"></a>Ustvarite novo datoteko sheme

1. Izberite **Nova datoteka sheme**.

1. Vnesite ime za datoteko in izberite **Shrani**.

1. Izberite **Nova entiteta**. The **Nova entiteta** panelni zasloni.

1. Vnesite ime subjekta in izberite **Lokacija podatkovnih datotek**.
   - **Več datotek .csv ali .parquet** : poiščite korensko mapo, izberite vrsto vzorca in vnesite izraz.
   - **Posamezne datoteke .csv ali .parquet** : Poiščite datoteko .csv ali .parquet in jo izberite.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Pogovorno okno za ustvarjanje nove entitete z označeno lokacijo podatkovnih datotek.":::

1. Izberite **Shrani**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Pogovorno okno za definiranje ali samodejno ustvarjanje atributov.":::

1. Izberite **definirati atribute** če želite ročno dodati atribute, ali izberite **jih samodejno ustvari**. Če želite določiti atribute, vnesite ime, izberite obliko podatkov in neobvezno semantično vrsto. Za samodejno ustvarjene atribute:

   1. Ko so atributi samodejno ustvarjeni, izberite **Pregledajte atribute**. The **Upravljajte atribute** prikaže stran.

   1. Prepričajte se, da je oblika podatkov pravilna za vsak atribut.

   1. Če želite omogočiti analitiko in druge zmogljivosti, izberite **Profiliranje podatkov** za celotno entiteto ali za posebne atribute. Privzeto nobena entiteta ni omogočena za profiliranje podatkov.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Pogovorno okno za izbiro profiliranja podatkov.":::

   1. Izberite **Dokončano**. The **Izberite entitete** prikaže stran.

1. Nadaljujte z dodajanjem entitet in atributov, če je primerno.

1. Ko so vse entitete dodane, izberite **Vključi** vključiti entitete v vir podatkov zaužitje.

   :::image type="content" source="media/ADLS_required.png" alt-text="Pogovorno okno, ki prikazuje Zahtevano za primarni ključ":::

1. Za izbrane entitete, ki zahtevajo postopno zaužitje, **Obvezno** prikaže pod **Postopno osveževanje**. Za vsako od teh entitet glej [Konfigurirajte postopno osveževanje za vire podatkov Azure Data Lake](incremental-refresh-data-sources.md).

1. Za izbrane entitete, pri katerih primarni ključ ni bil definiran, **Obvezno** prikaže pod **Primarni ključ**. Za vsakega od teh subjektov:
   1. Izberite **Obvezno**. The **Uredi entiteto** panelni zasloni.
   1. Izberite **Primarni ključ**. Primarni ključ je edinstven atribut za entiteto. Atribut je veljaven primarni ključ samo v primeru, če ne vsebuje podvojenih vrednosti, manjkajočih vrednosti ali ničelnih vrednosti. Kot primarni ključi so podprti atributi vrste podatkov niz, celo število in GUID.
   1. Po želji spremenite vzorec particije.
   1. Izberite **Zapri** da shranite in zaprete ploščo.

1. Izberite **Shrani**. The **Viri podatkov** odpre se stran z novim vir podatkov v **Osvežujoče** stanje.


## <a name="edit-an-azure-data-lake-storage-data-source"></a>Uredi an Azure Data Lake Storage vir podatkov

Posodobite lahko *Povežite se z računom za shranjevanje z uporabo* možnost. Za več informacij glejte [Povežite Customer Insights z Azure Data Lake Storage Račun 2. generacije z principalom storitve Azure](connect-service-principal.md). Če se želite povezati z drugim vsebnikom iz računa za shrambo ali spremeniti ime računa, [ustvarite novo povezavo vira podatkov](#connect-to-azure-data-lake-storage).

1. Pojdite na **Podatki** > **Viri podatkov**.

1. Zraven vir podatkov, ki ga želite posodobiti, izberite **Uredi**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Pogovorno okno za urejanje Azure Data Lake vir podatkov.":::

1. Spremenite katerega koli od naslednjih podatkov:

   - **Opis**
   - **Povežite svoj prostor za shranjevanje s pomočjo** in informacije o povezavi. Ob posodobitvi povezave ne morete spremeniti podatkov **vsebnika**.
      > [!NOTE]
      > Računu za shranjevanje ali vsebniku mora biti dodeljena ena od naslednjih vlog:
        > - Bralnik podatkov shrambe zbirke dvojiških podatkov
        > - Lastnik podatkov shrambe zbirke dvojiških podatkov
        > - Sodelujoči v shrambi zbirke dvojiških podatkov

   - **Omogoči zasebno povezavo** če želite prenesti podatke iz računa za shranjevanje prek zasebne povezave Azure. Za več informacij glejte [Zasebne povezave](security-overview.md#private-links-tab).

1. Izberite **Naprej**.
1. Spremenite kar koli od naslednjega:
   - Pomaknite se do druge datoteke model.json ali manifest.json z drugačnim naborom entitet iz vsebnika.
   - Če želite dodati dodatne entitete za zaužitje, izberite **Nova entiteta**.
   - Če želite odstraniti vse že izbrane entitete, če ni odvisnosti, izberite entiteto in **Izbriši**.
      > [!IMPORTANT]
      > Če obstajajo odvisnosti za obstoječo datoteko model.json ali manifest.json in nabor entitet, se prikaže sporočilo o napaki, vi pa ne morete izbrati druge datoteke model.json ali manifest.json. Odstranite te odvisnosti, preden spremenite datoteko model.json ali manifest.json oziroma ustvarite nov vir podatkov z datoteko model.json ali manifest.json, ki jo želite uporabiti, da se izognete odstranjevanju odvisnosti.
   - Če želite spremeniti lokacijo podatkovne datoteke ali primarni ključ, izberite **Uredi**.
   - Če želite spremeniti podatke o postopnem zaužitju, glejte [Konfigurirajte postopno osveževanje za vire podatkov Azure Data Lake](incremental-refresh-data-sources.md)

1. Izberite **Lastnosti** za dodajanje ali spreminjanje atributov ali za omogočanje profiliranja podatkov. Nato izberite **Končano**.

1. Kliknite **Shrani** da uporabite spremembe in se vrnete na **Viri podatkov** stran.
