---
title: Povezovanje s podatki v upravljanem jezeru podatkov Microsoft Dataverse
description: Uvozite podatke iz upravljanega jezera podatkov Microsoft Dataverse.
ms.date: 05/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 9ae0b964d8d39835715b7ddadc712e2338b855af
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082165"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Povezovanje s podatki v upravljanem jezeru podatkov Microsoft Dataverse

Microsoft Dataverse uporabniki se lahko hitro povežejo z analitičnimi entitetami v a Microsoft Dataverse upravljano jezero.

> [!NOTE]
> Morate biti admin na Dataverse organizacije, da nadaljujete in si ogledate seznam subjektov, ki so na voljo v upravljanem jezeru.

## <a name="important-considerations"></a>Pomembni premisleki

1. Lokacija za shranjevanje podatkov, shranjenih v spletnih storitvah, kot je Azure Data Lake Storage, se lahko razlikuje od lokacije za obdelovanje ali shranjevanje v storitvi Dynamics 365 Customer Insights.Z uvozom ali povezovanjem s podatki, shranjenimi v spletnih storitvah, se strinjate, da se lahko podatki prenašajo in shranjujejo Dynamics 365 Customer Insights . [Več o tem v Microsoftovem centru za zaupanje](https://www.microsoft.com/trust-center).
2. Samo Dataverse subjekti z [sledenje spremembam](/power-platform/admin/enable-change-tracking-control-data-synchronization) omogočene so vidne. Te entitete je mogoče izvoziti v Dataverse - upravljano podatkovno jezero in uporabljeno v Customer Insights. Izven škatle Dataverse tabele imajo privzeto omogočeno sledenje spremembam. Za tabele po meri morate vklopiti sledenje spremembam. Če želite preveriti, ali a Dataverse tabela je omogočena za sledenje spremembam, pojdite na [Power Apps](https://make.powerapps.com) > **Podatki** > **mize**. Poiščite tabelo, ki vas zanima, in jo izberite. Pojdi do **Nastavitve** > **Napredne možnosti** in pregledaj **Sledi spremembam** nastavitev.

## <a name="connect-to-a-dataverse-managed-lake"></a>Povezava z upravljanim jezerom Dataverse

1. Pojdite na **Podatki** > **Viri podatkov**.

1. Izberite **Dodaj vir podatkov**.

1. Izberite **Microsoft Dataverse**.

1. Vnesite a **ime** za vir podatkov in izbirno **Opis**.

1. Navedite **Naslov strežnika** za organizacijo Dataverse in izberite **Vpis**.

1. Na seznamu, ki je na voljo, izberite tabele, ki jih želite prenesti kot entitete v Customer Insights.

   > [!NOTE]
   > Če so nekatere tabele že izbrane, jih morda uporabljajo druge aplikacije Dynamics 365 (na primer Dynamics 365 Sales Insights ali Customer Service Insights). Tega izbora ni mogoče spremeniti. Te tabele bodo na voljo kot entitete, ko bo ustvarjen vir podatkov.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Pogovorno okno s seznamom entitet v okolju Dataverse.":::

1. Shranite svoj izbor, da začnete sinhronizacijo izbranih tabel iz Dataverse. Novo dodano povezavo najdete na strani **Viri podatkov**. Dodane bodo v čakalno vrsto za osvežitev, število entitet pa bo prikazano kot 0, dokler se ne sinhronizirajo vse izbrane tabele.

Samo en vir podatkov okolja lahko istočasno uporablja isto upravljano jezero Dataverse.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Urejanje vira podatkov upravljanega jezera Dataverse

Izbor entitet uredite šele po ustvarjanju vira podatkov. Če bi bili na primer dodane dodatne entitete v Dataverse in želite uvoziti tudi njih.
Če se želite povezati z drugim podatkovnim jezerom Dataverse, [ustvarite nov vir podatkov](#connect-to-a-dataverse-managed-lake).

1. Pojdite na **Podatki** > **Viri podatkov**.

1. Zraven vir podatkov, ki ga želite posodobiti, izberite **Uredi**.

1. Izberite dodatne entitete z razpoložljivega seznama entitet in izberite **Shrani**.
