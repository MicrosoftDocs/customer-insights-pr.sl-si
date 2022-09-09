---
title: Povezava z mapo Common Data Model z uporabo računa Azure Data Lake
description: Delo s podatki Common Data Model z uporabo storitve Azure Data Lake Storage.
ms.date: 07/27/2022
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
ms.openlocfilehash: d79b2d34e425e123224209814fef6e367c77c813
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/02/2022
ms.locfileid: "9396111"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Vzpostavljanje povezave s podatki v storitvi Azure Data Lake Storage

Vnesite podatke v Dynamics 365 Customer Insights z uporabo vašega Azure Data Lake Storage Gen2 račun. Vnos podatkov je lahko polni ali postopen.

## <a name="prerequisites"></a>Zahteve

- Podpore za vnos podatkov Azure Data Lake Storage *Gen2* izključno račune. Za vnos podatkov ne morete uporabiti računov Data Lake Storage Gen1.

- The Azure Data Lake Storage mora imeti račun [hierarhičen imenski prostor omogočen](/azure/storage/blobs/data-lake-storage-namespace). Podatki morajo biti shranjeni v obliki mape hierarhičen, ki določa korensko mapo in ima podmape za vsako entiteto. Podmape imajo lahko polne podatke ali mape z inkrementalnimi podatki.

- Če želite preveriti pristnost z glavnim imenom storitve Azure, preverite, ali je konfiguriran v najemniku. Za več informacij glejte [Povežite se z Azure Data Lake Storage Gen2 račun z glavnim servisom Azure](connect-service-principal.md).

- The Azure Data Lake Storage iz katerega se želite povezati in prejeti podatke, mora biti v isti regiji Azure kot Dynamics 365 Customer Insights okolju. Povezave do mape Common Data Model iz jezera podatkov v drugi regiji Azure niso podprte. Če želite poznati območje okolja Azure, pojdite na **skrbnik** > **Sistem** > **O tem** v Customer Insights.

- Podatki, shranjeni v spletnih storitvah, so lahko shranjeni na drugem mestu kot tam, kjer se podatki obdelujejo ali shranjujejo Dynamics 365 Customer Insights.Z uvozom ali povezovanjem s podatki, shranjenimi v spletnih storitvah, se strinjate, da je mogoče podatke prenašati in shranjevati z njimi Dynamics 365 Customer Insights . [Več o tem v Microsoftovem središču zaupanja](https://www.microsoft.com/trust-center).

- Vodja storitve Customer Insights mora imeti eno od naslednjih vlog za dostop do računa za shranjevanje. Za več informacij glejte [Podelite dovoljenja glavnemu servisu za dostop do računa za shranjevanje](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account).
  - Bralnik podatkov shrambe zbirke dvojiških podatkov
  - Lastnik podatkov shrambe zbirke dvojiških podatkov
  - Sodelujoči v shrambi zbirke dvojiških podatkov

- Uporabnik, ki vzpostavi povezavo vir podatkov, potrebuje najmanj dovoljenj sodelavec za podatke o shranjevalnem bloku za račun za shranjevanje.

- Podatki v vašem Data Lake Storageu bi morali slediti standardu skupnega podatkovnega modela za shranjevanje vaših podatkov in imeti skupni manifest podatkovnega modela, ki predstavlja shemo podatkovnih datotek (*.csv ali *.parquet). Manifest mora vsebovati podrobnosti o entitetah, kot so stolpci entitet in tipi podatkov, ter lokacijo in vrsto podatkovne datoteke. Za več informacij glejte [Manifest skupnega podatkovnega modela](/common-data-model/sdk/manifest). Če manifest ni prisoten, lahko skrbniški uporabniki z dostopom lastnika podatkov bloba shrambe ali podatkov bloba shranjevanja sodelavec določijo shemo pri vnosu podatkov.

## <a name="connect-to-azure-data-lake-storage"></a>Vzpostavljanje povezave s storitvijo Azure Data Lake Storage

1. Pojdite na **Podatki** > **Viri podatkov**.

1. Izberite **Dodaj vir podatkov**.

1. Izberite **Shramba podatkovnega jezera Azure**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Pogovorno okno za vnos podrobnosti povezave za Azure Data Lake." lightbox="media/data_sources_ADLS.png":::

1. Vnesite a **Ime** za vir podatkov in neobvezno **Opis**. Ime enolično identificira vir podatkov in je navedeno v nadaljnjih procesih in ga ni mogoče spremeniti.

1. Izberite eno od naslednjih možnosti za **Povežite shrambo z uporabo**. Za več informacij glejte [Povežite Customer Insights z Azure Data Lake Storage Gen2 račun z glavnim servisom Azure](connect-service-principal.md).

   - **Vir Azure** : Vnesite **ID vira** . Po želji izberite, če želite prenesti podatke iz računa za shranjevanje prek zasebne povezave Azure **Omogoči zasebno povezavo**. Za več informacij glejte [Zasebne povezave](security-overview.md#set-up-an-azure-private-link).
   - **Naročnina na Azure** : izberite **Naročnina** in nato **Skupina virov** in **Račun za shranjevanje**. Po želji izberite, če želite prenesti podatke iz računa za shranjevanje prek zasebne povezave Azure **Omogoči zasebno povezavo**. Za več informacij glejte [Zasebne povezave](security-overview.md#set-up-an-azure-private-link).
  
   > [!NOTE]
   > Za ustvarjanje vir podatkov potrebujete eno od naslednjih vlog za vsebnik ali račun za shranjevanje:
   >
   >  - Storage Blob Data Uporabnik z dovoljenjem za branje zadostuje za branje iz računa za shranjevanje in vnos podatkov v Customer Insights.
   >  - Podatki bloba za shranjevanje sodelavec ali Lastnik je potreben, če želite urejati datoteke manifesta neposredno v Customer Insights.  
  
1. Izberite ime za **Posoda** ki vsebuje podatke in shemo (datoteka model.json ali manifest.json), iz katere želite uvoziti podatke, in izberite **Naslednji**.
   > [!NOTE]
   > Vsaka datoteka model.json ali manifest.json, povezana z drugim virom podatkov v okolju, ne bo prikazana na seznamu. Vendar pa je isto datoteko model.json ali ali manifest.json mogoče uporabiti za vire podatkov v več okoljih.

1. Če želite ustvariti novo shemo, pojdite na [Ustvari novo datoteko sheme](#create-a-new-schema-file).

1. Če želite uporabiti obstoječo shemo, se pomaknite do mape, ki vsebuje datoteko model.json ali manifest.cdm.json. Datoteko lahko poiščete v imeniku.

1. Izberite datoteko json in izberite **Naslednji**. Prikaže se seznam razpoložljivih entitet.

   :::image type="content" source="media/review-entities.png" alt-text="Pogovorno okno s seznamom subjektov za izbiro":::

1. Izberite entitete, ki jih želite vključiti.

   :::image type="content" source="media/ADLS_required.png" alt-text="Pogovorno okno, ki prikazuje Zahtevano za primarni ključ":::

   > [!TIP]
   > Če želite urediti entiteto v vmesniku za urejanje JSON, izberite entiteto in nato **Uredi datoteko sheme**. Spremenite in izberite **Shrani**.

1. Za izbrane entitete, ki zahtevajo postopno zaužitje, **Obvezno** prikaže pod **Postopna osvežitev**. Za vsako od teh entitet glejte [Konfigurirajte inkrementalno osvežitev za vire podatkov Azure Data Lake](incremental-refresh-data-sources.md).

1. Za izbrane entitete, kjer primarni ključ ni bil definiran, **Obvezno** prikaže pod **Primarni ključ**. Za vsako od teh entitet:
   1. Izberite **Obvezno**. The **Uredi entiteto** panelni zasloni.
   1. Izberite **Primarni ključ**. Primarni ključ je atribut, edinstven za entiteto. Atribut je veljaven primarni ključ samo v primeru, če ne vsebuje podvojenih vrednosti, manjkajočih vrednosti ali ničelnih vrednosti. Kot primarni ključi so podprti atributi podatkovnega tipa niz, celo število in GUID.
   1. Po želji spremenite vzorec particije.
   1. Izberite **Zapri** da shranite in zaprete ploščo.

1. Izberite število **Lastnosti** za vsako vključeno entiteto. The **Upravljanje atributov** prikazi strani.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Pogovorno okno za izbiro profiliranja podatkov.":::

   1. Ustvarite nove atribute, uredite ali izbrišite obstoječe atribute. Spremenite lahko ime, obliko zapisa podatkov ali dodate semantično vrsto.
   1. Če želite omogočiti analitiko in druge zmožnosti, izberite **Profiliranje podatkov** za celotno entiteto ali za določene atribute. Privzeto nobena entiteta ni omogočena za profiliranje podatkov.
   1. Izberite **Dokončano**.

1. Izberite **Shrani**. The **Viri podatkov** odpre se stran, ki prikazuje novo vir podatkov v **Osvežujoče** stanje.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Nalaganje podatkov lahko traja nekaj časa. Po uspešni osvežitvi lahko vnesene podatke pregledate iz [**Entitete**](entities.md) strani.

### <a name="create-a-new-schema-file"></a>Ustvari novo datoteko sheme

1. Izberite **Nova datoteka sheme**.

1. Vnesite ime datoteke in izberite **Shrani**.

1. Izberite **Nova entiteta**. The **Nova entiteta** panelni zasloni.

1. Vnesite ime subjekta in izberite **Lokacija podatkovnih datotek**.
   - **Več datotek .csv ali .parquet** : poiščite korensko mapo, izberite vrsto vzorca in vnesite izraz.
   - **Posamezne datoteke .csv ali .parquet** : poiščite datoteko .csv ali .parquet in jo izberite.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Pogovorno okno za ustvarjanje nove entitete z označeno lokacijo podatkovnih datotek.":::

1. Izberite **Shrani**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Pogovorno okno za definiranje ali samodejno ustvarjanje atributov.":::

1. Izberite **določite atribute** če želite ročno dodati atribute, ali izberite **jih samodejno ustvari**. Če želite definirati atribute, vnesite ime, izberite obliko zapisa podatkov in izbirni semantični tip. Za samodejno ustvarjene atribute:

   1. Ko so atributi samodejno ustvarjeni, izberite **Pregled atributov**. The **Upravljanje atributov** prikazi strani.

   1. Prepričajte se, da je oblika podatkov pravilna za vsak atribut.

   1. Če želite omogočiti analitiko in druge zmožnosti, izberite **Profiliranje podatkov** za celotno entiteto ali za določene atribute. Privzeto nobena entiteta ni omogočena za profiliranje podatkov.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Pogovorno okno za izbiro profiliranja podatkov.":::

   1. Izberite **Dokončano**. The **Izberite entitete** prikazi strani.

1. Nadaljujte z dodajanjem entitet in atributov, če je primerno.

1. Ko so dodane vse entitete, izberite **Vključi** za vključitev entitet v vir podatkov zaužitje.

   :::image type="content" source="media/ADLS_required.png" alt-text="Pogovorno okno, ki prikazuje Zahtevano za primarni ključ":::

1. Za izbrane entitete, ki zahtevajo postopno zaužitje, **Obvezno** prikaže pod **Postopna osvežitev**. Za vsako od teh entitet glejte [Konfigurirajte inkrementalno osvežitev za vire podatkov Azure Data Lake](incremental-refresh-data-sources.md).

1. Za izbrane entitete, kjer primarni ključ ni bil definiran, **Obvezno** prikaže pod **Primarni ključ**. Za vsako od teh entitet:
   1. Izberite **Obvezno**. The **Uredi entiteto** panelni zasloni.
   1. Izberite **Primarni ključ**. Primarni ključ je atribut, edinstven za entiteto. Atribut je veljaven primarni ključ samo v primeru, če ne vsebuje podvojenih vrednosti, manjkajočih vrednosti ali ničelnih vrednosti. Kot primarni ključi so podprti atributi podatkovnega tipa niz, celo število in GUID.
   1. Po želji spremenite vzorec particije.
   1. Izberite **Zapri** da shranite in zaprete ploščo.

1. Izberite **Shrani**. The **Viri podatkov** odpre se stran, ki prikazuje novo vir podatkov v **Osvežujoče** stanje.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Nalaganje podatkov lahko traja nekaj časa. Po uspešni osvežitvi lahko vnesene podatke pregledate iz [**Entitete**](entities.md) strani.

## <a name="edit-an-azure-data-lake-storage-data-source"></a>Uredi an Azure Data Lake Storage vir podatkov

Lahko posodobite *Povežite se z računom za shranjevanje z uporabo* možnost. Za več informacij glejte [Povežite Customer Insights z Azure Data Lake Storage Gen2 račun z glavnim servisom Azure](connect-service-principal.md). Če se želite povezati z drugim vsebnikom iz računa za shrambo ali spremeniti ime računa, [ustvarite novo povezavo vira podatkov](#connect-to-azure-data-lake-storage).

1. Pojdite na **Podatki** > **Viri podatkov**.

1. Izberite poleg vir podatkov, ki ga želite posodobiti **Uredi**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Pogovorno okno za urejanje podatkovnega jezera Azure vir podatkov.":::

1. Spremenite katero koli od naslednjih informacij:

   - **Opis**
   - **Povežite shrambo z uporabo** in informacije o povezavi. Ob posodobitvi povezave ne morete spremeniti podatkov **vsebnika**.
      > [!NOTE]
      > Računu za shranjevanje ali vsebniku mora biti dodeljena ena od naslednjih vlog:
        > - Bralnik podatkov shrambe zbirke dvojiških podatkov
        > - Lastnik podatkov shrambe zbirke dvojiških podatkov
        > - Sodelujoči v shrambi zbirke dvojiških podatkov

   - **Omogoči zasebno povezavo** če želite prenesti podatke iz računa za shranjevanje prek zasebne povezave Azure. Za več informacij glejte [Zasebne povezave](security-overview.md#set-up-an-azure-private-link).

1. Izberite **Naprej**.
1. Spremenite kar koli od naslednjega:
   - Pomaknite se do druge datoteke model.json ali manifest.json z drugačnim naborom entitet iz vsebnika.
   - Če želite dodati dodatne entitete za vnos, izberite **Nova entiteta**.
   - Če želite odstraniti vse že izbrane entitete, če ni odvisnosti, izberite entiteto in **Izbriši**.
      > [!IMPORTANT]
      > Če obstajajo odvisnosti za obstoječo datoteko model.json ali manifest.json in nabor entitet, se prikaže sporočilo o napaki, vi pa ne morete izbrati druge datoteke model.json ali manifest.json. Odstranite te odvisnosti, preden spremenite datoteko model.json ali manifest.json oziroma ustvarite nov vir podatkov z datoteko model.json ali manifest.json, ki jo želite uporabiti, da se izognete odstranjevanju odvisnosti.
   - Če želite spremeniti lokacijo podatkovne datoteke ali primarni ključ, izberite **Uredi**.
   - Če želite spremeniti inkrementalne podatke o vnosu, glejte [Konfigurirajte inkrementalno osvežitev za vire podatkov Azure Data Lake](incremental-refresh-data-sources.md).
   - Spremenite samo ime entitete, da se bo ujemalo z imenom entitete v datoteki .json.

     > [!NOTE]
     > Ime entitete v Customer Insights naj bo vedno enako imenu entitete v datoteki model.json ali manifest.json po zaužitju. Customer Insights preveri vsa imena entitet z model.json ali manifest.json med vsako osvežitvijo sistema. Če je ime entitete spremenjeno v Customer Insights ali zunaj njega, pride do napake, ker Customer Insights ne najde novega imena entitete v datoteki .json. Če je bilo ime vstavljene entitete pomotoma spremenjeno, uredite ime entitete v Customer Insights, da se bo ujemalo z imenom v datoteki .json.

1. Izberite **Lastnosti** za dodajanje ali spreminjanje atributov ali za omogočanje profiliranja podatkov. Nato izberite **Končano**.

1. Kliknite **Shrani** da uveljavite svoje spremembe in se vrnete na **Viri podatkov** strani.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
