---
title: Povezovanje podatkov Common Data Model z računom Azure Data Lake
description: Delo s podatki Common Data Model z uporabo storitve Azure Data Lake Storage.
ms.date: 05/24/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: 2e8564950a3269180a85f80fb736d2dcbd1b03b6
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833405"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Povezava z mapo Common Data Model z uporabo računa Azure Data Lake

Ta članek vsebuje informacije o tem, kako vnesti podatke Dynamics 365 Customer Insights iz mape Common Data Model z uporabo vašega Azure Data Lake Storage Račun 2. generacije.

## <a name="important-considerations"></a>Pomembni premisleki

- Podatki v vaši shrambi Azure Data Lake morajo upoštevati standard Common Data Model. Druge oblike zapisa trenutno niso podprte.

- Vključevanje podatkov podpira zgolj račune za shrambo Azure Data Lake *Gen2*. Računov za shrambo Azure Data Lake Gen1 ne morete uporabljati za vključevanje podatkov.

- Račun za shranjevanje podatkov Azure Data Lake mora imeti [Imenski prostor hierarhičen je omogočen](/azure/storage/blobs/data-lake-storage-namespace).

- Če želite preveriti pristnost z glavnim imenom storitve Azure, preverite, ali je konfiguriran v najemniku. Za več informacij glejte [Povežite se z an Azure Data Lake Storage Račun 2. generacije z principalom storitve Azure](connect-service-principal.md).

- Azure Data Lake, ki ga želite povezati in od katerega želite vključiti podatke, mora biti v isti regiji Azure kot okolje Dynamics 365 Customer Insights. Povezave do mape Common Data Model iz jezera podatkov v drugi regiji Azure niso podprte. Če želite poznati Azurno regijo okolja, pojdite na **Admin** > **sistem** > **O** v Customer Insights.

- Podatki, shranjeni v spletnih storitvah, so lahko shranjeni na drugi lokaciji kot tam, kjer se podatki obdelujejo ali shranjujejo Dynamics 365 Customer Insights.Z uvozom ali povezovanjem s podatki, shranjenimi v spletnih storitvah, se strinjate, da se lahko podatki prenašajo in shranjujejo Dynamics 365 Customer Insights . [Več o tem v Microsoftovem centru za zaupanje](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-common-data-model-folder"></a>Vzpostavitev povezave z mapo Common Data Model

1. Pojdite na **Podatki** > **Viri podatkov**.

1. Izberite **Dodaj vir podatkov**.

1. Izberite **Shramba podatkovnega jezera Azure**, vnesite a **ime** za vir podatkov, nato izberite **Naslednji**.

   - Če ste pozvani, izberite enega od vzorčnih naborov podatkov, ki se nanašajo na vašo panogo, nato izberite **Naslednji**.

1. Izbirate lahko med možnostjo, ki temelji na viru, in možnostjo preverjanja pristnosti, ki temelji na naročnini. Za več informacij glejte [Povežite se z an Azure Data Lake Storage Račun 2. generacije z principalom storitve Azure](connect-service-principal.md). Vnesite **Naslov strežnika**, izberite **Vpiši se**, nato izberite **Naslednji**.
   > [!div class="mx-imgBorder"]
   > ![Pogovorno okno za vnos novih podrobnosti povezave za Azure Data Lake.](media/enter-new-storage-details.png)
   > [!NOTE]
   > Za vsebnik v računu za shranjevanje potrebujete eno od naslednjih vlog, da ustvarite vir podatkov:
   >
   >  - Podatki shranjevalnih blokov Uporabnik z dovoljenjem za branje zadostujejo za branje iz računa za shranjevanje in zaužitje podatkov v Customer Insights. 
   >  - Podatki shranjevalnih blokov sodelavec ali lastnik so potrebni, če želite datoteke manifesta urejati neposredno v Customer Insights.

1. V pogovornem oknu **Izberite mapo Common Data Model** izberite datoteko model.json ali manifest.json, iz katere želite uvoziti podatke, in izberite možnost **Naprej**.
   > [!NOTE]
   > Vsaka datoteka model.json ali manifest.json, povezana z drugim virom podatkov v okolju, ne bo prikazana na seznamu.

1. Videli boste seznam razpoložljivih entitet v izbrani datoteki model.json ali manifest.json. Preglejte in izberite s seznama razpoložljivih entitet, nato izberite **Shrani**. Vse izbrane entitete bodo vključene iz novega vira podatkov.
   > [!div class="mx-imgBorder"]
   > ![Pogovorno okno s seznamom entitet iz datoteke model.json.](media/review-entities.png)

1. Označite, katere podatkovne entitete želite omogočiti profiliranje podatkov, nato izberite **Shrani**. Profiliranje podatkov omogoča analitiko in druge zmogljivosti. Izberete lahko celotno entiteto, pri čemer se izbere vse atribute iz entitete, ali izberete določene atribute po svoji izbiri. Privzeto nobena entiteta ni omogočena za profiliranje podatkov.
   > [!div class="mx-imgBorder"]
   > ![Pogovorno okno, ki prikazuje profiliranje podatkov.](media/dataprofiling-entities.png)

1. Ko shranite svoje nastavitve, se odpre stran **Viri podatkov**. Zdaj bi se vam morala prikazati povezava mape Common Data Model kot vir podatkov.

> [!NOTE]
> Datoteka model.json ali manifest.json se lahko v istem okolju poveže samo z enim virom podatkov. Vendar pa je isto datoteko model.json ali ali manifest.json mogoče uporabiti za vire podatkov v več okoljih.

## <a name="edit-a-common-data-model-folder-data-source"></a>Urejanje vira podatkov mape Common Data Model

Lahko posodobite ključ za dostop za račun za shrambo, ki vsebuje mapo Common Data Model. Prav tako lahko spremenite datoteko model.json ali manifest.json. Če se želite povezati z drugim vsebnikom iz računa za shrambo ali spremeniti ime računa, [ustvarite novo povezavo vira podatkov](#connect-to-a-common-data-model-folder).

1. Pojdite na **Podatki** > **Viri podatkov**.

2. Poleg vir podatkov, ki ga želite posodobiti, izberite navpično tritočko (&vellip;).

3. Na seznamu izberite možnost **Uredi**.

4. Po želji posodobite **Ključ za dostop** in izberite **Naprej**.

   ![Pogovorno okno za urejanje in posodobitev ključa za dostop za obstoječi vir podatkov.](media/edit-access-key.png)

5. Po želji lahko posodobitev opravite prek povezave s ključem kupca s povezavo, ki temelji na viru ali naročnini. Za več informacij glejte [Povežite se z an Azure Data Lake Storage Račun 2. generacije z principalom storitve Azure](connect-service-principal.md). Ob posodobitvi povezave ne morete spremeniti podatkov **vsebnika**.
   > [!div class="mx-imgBorder"]

   > ![Pogovorno okno za vnos podrobnosti povezave za Azure Data Lake v obstoječi račun za shrambo.](media/enter-existing-storage-details.png)

6. Izberete lahko tudi drugo datoteko model.json ali manifest.json z drugim naborom entitet iz vsebnika.

7. Po želji lahko izberete dodatne entitete za vključitev. Če ne obstajajo odvisnosti, lahko tudi odstranite vse izbrane entitete.

   > [!IMPORTANT]
   > Če obstajajo odvisnosti za obstoječo datoteko model.json ali manifest.json in nabor entitet, se prikaže sporočilo o napaki, vi pa ne morete izbrati druge datoteke model.json ali manifest.json. Odstranite te odvisnosti, preden spremenite datoteko model.json ali manifest.json oziroma ustvarite nov vir podatkov z datoteko model.json ali manifest.json, ki jo želite uporabiti, da se izognete odstranjevanju odvisnosti.

8. Po želji lahko izberete dodatne atribute ali entitete, da omogočite profiliranje podatkov ali onemogočite že izbrane.

[!INCLUDE [footer-include](includes/footer-banner.md)]
