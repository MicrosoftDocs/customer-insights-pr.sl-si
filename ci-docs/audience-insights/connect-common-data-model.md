---
title: Povezovanje podatkov Common Data Model z računom Azure Data Lake
description: Delo s podatki Common Data Model z uporabo storitve Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643478"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Povezava z mapo Common Data Model z uporabo računa Azure Data Lake

V tem članku so informacije o vključitvi podatkov iz mape Common Data Model z vašim računom Azure Data Lake Storage Gen2.

## <a name="important-considerations"></a>Pomembni premisleki

- Podatki v vaši shrambi Azure Data Lake morajo upoštevati standard Common Data Model. Druge oblike zapisa trenutno niso podprte.

- Vključevanje podatkov podpira zgolj račune za shrambo Azure Data Lake *Gen2*. Računov za shrambo Azure Data Lake Gen1 ne morete uporabljati za vključevanje podatkov.

- Če želite preveriti pristnost z glavnim imenom storitve Azure, preverite, ali je konfiguriran v najemniku. Za več informacij glejte [Povezovanje vpogledov v občinstvo in računa Azure Data Lake Storage Gen2 z glavnim imenom storitve Azure](connect-service-principal.md).

- Azure Data Lake, ki ga želite povezati in od katerega želite vključiti podatke, mora biti v isti regiji Azure kot okolje Dynamics 365 Customer Insights. Povezave do mape Common Data Model iz jezera podatkov v drugi regiji Azure niso podprte. Če želite ugotoviti območje Azure v okolju, izberite **Skrbnik** > **Sistem** > **Vizitka** v razdelku vpogledov v občinstvo.

- Podatki, shranjeni v spletnih storitvah, se lahko shranijo na drugem mestu kot na mestu, kjer se podatki obdelujejo ali shranjujejo v storitvi Dynamics 365 Customer Insights. Z uvažanjem podatkov ali povezovanjem s podatki, shranjenimi v spletnih storitvah, se strinjate, da se podatki lahko prenesejo in shranijo v storitvi Dynamics 365 Customer Insights. [Več o tem preberite v Microsoftovem središču zaupanja.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>Vzpostavitev povezave z mapo Common Data Model

1. Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.

1. Izberite **Dodaj vir podatkov**.

1. Izberite **Vzpostavitev povezave z mapo Common Data Model**, vnesite **ime** za vir podatkov in izberite **Naprej**.

1. Izbirate lahko med možnostjo, ki temelji na viru, in možnostjo preverjanja pristnosti, ki temelji na naročnini. Za več informacij glejte [Povezovanje vpogledov v občinstvo in računa Azure Data Lake Storage Gen2 z glavnim imenom storitve Azure](connect-service-principal.md). Vnesite podatke **vsebnika** in izberite **Naprej**.
   > [!div class="mx-imgBorder"]
   > ![Pogovorno okno za vnos podrobnosti o povezavi za Azure Data Lake](media/enter-new-storage-details.png)

1. V pogovornem oknu **Izberite mapo Common Data Model** izberite datoteko model.json, iz katere želite uvoziti podatke, in izberite **Naprej**.
   > [!NOTE]
   > Vsaka datoteka model.json, povezana z drugim virom podatkov v okolju, ne bo prikazana na seznamu.

1. V izbrani datoteki model.json boste prejeli seznam razpoložljivih entitet. Oglejte si ga in izberite možnost s seznama razpoložljivih entitet, nato pa izberite možnost **Shrani**. Vse izbrane entitete bodo vključene iz novega vira podatkov.
   > [!div class="mx-imgBorder"]
   > ![Pogovorno okno s seznamom entitet iz datoteke model.json](media/review-entities.png)

8. Navedite, za katere podatkovne entitete želite omogočiti profiliranje podatkov, in izberite **Shrani**. Profiliranje podatkov omogoča analitiko in druge zmogljivosti. Izberete lahko celotno entiteto, pri čemer se izbere vse atribute iz entitete, ali izberete določene atribute po svoji izbiri. Privzeto nobena entiteta ni omogočena za profiliranje podatkov.
   > [!div class="mx-imgBorder"]
   > ![Pogovorno okno, ki prikazuje profiliranje podatkov](media/dataprofiling-entities.png)

9. Ko shranite svoje nastavitve, se odpre stran **Viri podatkov**. Zdaj bi se vam morala prikazati povezava mape Common Data Model kot vir podatkov.

> [!NOTE]
> Datoteka model.json se lahko v istem okolju poveže samo z enim virom podatkov. Vendar pa je isto datoteko model.json mogoče uporabiti za vire podatkov v več okoljih.

## <a name="edit-a-common-data-model-folder-data-source"></a>Urejanje vira podatkov mape Common Data Model

Lahko posodobite ključ za dostop za račun za shrambo, ki vsebuje mapo Common Data Model. Lahko pa tudi spremenite datoteko model.json. Če se želite povezati z drugim vsebnikom iz računa za shrambo ali spremeniti ime računa, [ustvarite novo povezavo vira podatkov](#connect-to-a-common-data-model-folder).

1. Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.

2. Izberite tri pike poleg vira podatkov, ki ga želite posodobiti.

3. Na seznamu izberite možnost **Uredi**.

4. Po želji posodobite **Ključ za dostop** in izberite **Naprej**.

   ![Pogovorno okno za urejanje in posodobitev ključa za dostop za obstoječi vir podatkov](media/edit-access-key.png)

5. Po želji lahko posodobitev opravite prek povezave s ključem kupca s povezavo, ki temelji na viru ali naročnini. Za več informacij glejte [Povezovanje vpogledov v občinstvo in računa Azure Data Lake Storage Gen2 z glavnim imenom storitve Azure](connect-service-principal.md). Ob posodobitvi povezave ne morete spremeniti podatkov **vsebnika**.
   > [!div class="mx-imgBorder"]
   > ![Pogovorno okno za vnos podrobnosti o povezavi za Azure Data Lake](media/enter-existing-storage-details.png)

6. Izberete lahko tudi drugo datoteko model.json z drugačnim naborom entitet iz vsebnika.

7. Po želji lahko izberete dodatne entitete za vključitev. Če ne obstajajo odvisnosti, lahko tudi odstranite vse izbrane entitete.

   > [!IMPORTANT]
   > Če v obstoječi datoteki model.json in naboru entitet obstajajo odvisnosti, se prikaže sporočilo o napaki in ne morete izbrati druge datoteke model.json. Odstranite te odvisnosti, preden spremenite datoteko model.json, ali ustvarite nov vir podatkov z datoteko model.json, ki jo želite uporabiti, da vam ne bo treba odstraniti odvisnosti.

8. Po želji lahko izberete dodatne atribute ali entitete, da omogočite profiliranje podatkov ali onemogočite že izbrane.   
