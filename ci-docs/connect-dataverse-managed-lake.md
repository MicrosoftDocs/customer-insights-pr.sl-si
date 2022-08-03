---
title: Povezovanje s podatki v upravljanem jezeru podatkov Microsoft Dataverse
description: Uvozite podatke iz upravljanega jezera podatkov Microsoft Dataverse.
ms.date: 07/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: b21150a1c51bdad35250cae7fde7f38a014ec876
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206973"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Povezovanje s podatki v upravljanem jezeru podatkov Microsoft Dataverse

Microsoft Dataverse uporabniki se lahko hitro povežejo z analitičnimi subjekti v a Microsoft Dataverse upravljano jezero. Samo en vir podatkov okolja lahko istočasno uporablja isto upravljano jezero Dataverse.

> [!NOTE]
> Morate biti skrbnik na Dataverse organizaciji za nadaljevanje in ogled seznama entitet, ki so na voljo v upravljanem jezeru.

## <a name="prerequisites"></a>Zahteve

- Lokacija za shranjevanje podatkov, shranjenih v spletnih storitvah, kot je Azure Data Lake Storage, se lahko razlikuje od lokacije za obdelovanje ali shranjevanje v storitvi Dynamics 365 Customer Insights.Z uvozom ali povezovanjem s podatki, shranjenimi v spletnih storitvah, se strinjate, da je mogoče podatke prenašati in shranjevati z njimi Dynamics 365 Customer Insights . [Več o tem v Microsoftovem središču zaupanja](https://www.microsoft.com/trust-center).

- Samo Dataverse subjekti z [sledenje spremembam](/power-platform/admin/enable-change-tracking-control-data-synchronization) omogočene so vidne. Te entitete je mogoče izvoziti v Dataverse - upravljano podatkovno jezero in uporabljeno v Customer Insights. Izven škatle Dataverse tabele imajo privzeto omogočeno sledenje spremembam. Za tabele po meri morate vklopiti sledenje spremembam. Če želite preveriti, ali a Dataverse tabela je omogočena za sledenje spremembam, pojdite na [Power Apps](https://make.powerapps.com) > **podatki** > **Mize**. Poiščite tabelo, ki vas zanima, in jo izberite. Pojdi do **nastavitve** > **Napredne možnosti** in pregledajte **Sledi spremembam** nastavitev.

## <a name="connect-to-a-dataverse-managed-lake"></a>Povezava z upravljanim jezerom Dataverse

1. Pojdite na **Podatki** > **Viri podatkov**.

1. Izberite **Dodaj vir podatkov**.

1. Izberite **Microsoft Dataverse**.

1. Vnesite a **Ime** za vir podatkov in neobvezno **Opis**.

1. Navedite **Naslov strežnika** za organizacijo Dataverse in izberite **Vpis**.

1. Na razpoložljivem seznamu izberite tabele, ki jih želite vnesti kot entitete v Customer Insights.

   > [!NOTE]
   > Če so nekatere tabele že izbrane, jih morda uporabljajo druge aplikacije Dynamics 365 (na primer Dynamics 365 Sales Insights ali Customer Service Insights). Tega izbora ni mogoče spremeniti. Te tabele bodo na voljo kot entitete, ko bo ustvarjen vir podatkov.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Pogovorno okno s seznamom entitet v okolju Dataverse.":::

1. Shranite svoj izbor, da začnete sinhronizacijo izbranih tabel iz Dataverse. Novo dodano povezavo najdete na strani **Viri podatkov**. Dodane bodo v čakalno vrsto za osvežitev, število entitet pa bo prikazano kot 0, dokler se ne sinhronizirajo vse izbrane tabele.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Nalaganje podatkov lahko traja nekaj časa. Po uspešni osvežitvi lahko vnesene podatke pregledate iz [**Entitete**](entities.md) strani.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Urejanje vira podatkov upravljanega jezera Dataverse

Izbor entitet uredite šele po ustvarjanju vira podatkov. Če bi bili na primer dodane dodatne entitete v Dataverse in želite uvoziti tudi njih.
Če se želite povezati z drugim podatkovnim jezerom Dataverse, [ustvarite nov vir podatkov](#connect-to-a-dataverse-managed-lake).

1. Pojdite na **Podatki** > **Viri podatkov**.

1. Izberite poleg vir podatkov, ki ga želite posodobiti **Uredi**.

1. Na razpoložljivem seznamu entitet izberite dodatne entitete.

1. Kliknite **Shrani** da uveljavite svoje spremembe in se vrnete na **Viri podatkov** strani.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
