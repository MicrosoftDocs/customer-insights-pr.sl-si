---
title: Vzpostavljanje povezave s tabelami v storitvi Microsoft Dataverse
description: Uvozite podatke iz upravljanega jezera podatkov Microsoft Dataverse.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 81412ea8259e690eb839676d82ab31847854a97e
ms.sourcegitcommit: a8e99cf8b23ccc00d76c1dee22afd808a160a5c8
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/22/2022
ms.locfileid: "8464121"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Povezovanje s podatki v upravljanem jezeru podatkov Microsoft Dataverse

Ta članek vsebuje informacije o tem, kako Dataverse uporabniki se lahko hitro povežejo z analitičnimi entitetami v a Microsoft Dataverse upravljano jezero. 

> [!NOTE]
> Morate biti admin na Dataverse organizacije, da nadaljujete in si ogledate seznam subjektov, ki so na voljo v upravljanem jezeru.

## <a name="important-considerations"></a>Pomembni premisleki

1. Lokacija za shranjevanje podatkov, shranjenih v spletnih storitvah, kot je Azure Data Lake Storage, se lahko razlikuje od lokacije za obdelovanje ali shranjevanje v storitvi Dynamics 365 Customer Insights.Z uvozom ali povezovanjem s podatki, shranjenimi v spletnih storitvah, se strinjate, da se lahko podatki prenašajo in shranjujejo Dynamics 365 Customer Insights . [Več o tem v Microsoftovem centru za zaupanje](https://www.microsoft.com/trust-center).
2. Samo Dataverse subjekti z [sledenje spremembam](/power-platform/admin/enable-change-tracking-control-data-synchronization) omogočene so vidne. Te entitete je mogoče izvoziti v Dataverse - upravljano podatkovno jezero in uporabljeno v Customer Insights. Izven škatle Dataverse tabele imajo privzeto omogočeno sledenje spremembam. Za tabele po meri morate vklopiti sledenje spremembam. Če želite preveriti, ali a Dataverse tabela je omogočena za sledenje spremembam, pojdite na [Power Apps](https://make.powerapps.com) > **Podatki** > **mize**. Poiščite tabelo, ki vas zanima, in jo izberite. Pojdi do **Nastavitve** > **Napredne možnosti** in pregledaj **Sledi spremembam** nastavitev.

## <a name="connect-to-a-dataverse-managed-lake"></a>Povezava z upravljanim jezerom Dataverse

1. Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.

2. Izberite **Dodaj vir podatkov**.

3. Izberite **Microsoft Dataverse** in izberite **Naslednji**.

4. Vnesite **ime** za vir podatkov in izberite **Naprej**. 

5. Navedite **Naslov strežnika** za organizacijo Dataverse in izberite **Vpis**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Zaslon v koraku uvoza podatkov, v katerega lahko uporabnik vnese URL okolja Dataverse.":::

6. S seznama, ki je na voljo, izberite tabele, ki jih želite uvoziti kot entitete v vpoglede občinstva.    

   > [!NOTE]
   > Če so nekatere tabele že izbrane, jih morda uporabljajo druge aplikacije Dynamics 365 (na primer Dynamics 365 Sales Insights ali Customer Service Insights). Tega izbora ni mogoče spremeniti. Te tabele bodo na voljo kot entitete, ko bo ustvarjen vir podatkov.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Pogovorno okno s seznamom entitet v okolju Dataverse.":::

7. Shranite svoj izbor, da začnete sinhronizacijo izbranih tabel iz Dataverse. Novo dodano povezavo najdete na strani **Viri podatkov**. Dodane bodo v čakalno vrsto za osvežitev, število entitet pa bo prikazano kot 0, dokler se ne sinhronizirajo vse izbrane tabele.

Samo en vir podatkov okolja lahko istočasno uporablja isto upravljano jezero Dataverse.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Urejanje vira podatkov upravljanega jezera Dataverse

Izbor entitet uredite šele po ustvarjanju vira podatkov. Če bi bili na primer dodane dodatne entitete v Dataverse in želite uvoziti tudi njih.    
Če se želite povezati z drugim podatkovnim jezerom Dataverse, [ustvarite nov vir podatkov](#connect-to-a-dataverse-managed-lake).

1. Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.

2. Izberite tri pike poleg vira podatkov, ki ga želite posodobiti.

3. Na seznamu izberite možnost **Uredi**.

4. Izberite dodatne entitete z razpoložljivega seznama entitet in izberite **Shrani**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
