---
title: Ustvarite novo okolje
description: Namen okolja in kako ustvariti novega.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 5e301b4ff0a7586fb143b154b773791b3bd645b7
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648137"
---
# <a name="create-a-new-environment"></a>Ustvarite novo okolje 

## <a name="overview"></a>Pregled

Okolje je prostor, kjer upravljate s svojimi delovnimi prostori in povezavami. Kako uporabljate okolja, je odvisno od vaše organizacije in primera uporabe. Omogoča na primer ustvarjanje:

- enega okolja,
- ločenih okolij za preskušanje in proizvodnjo,
- ločenih okolij za določene skupine ali oddelke v vaši organizaciji, ki vsebujejo ustrezne dogodke za vsak občinstvo,
- ločenih okolij za različne globalne podružnice vašega podjetja,
- povezav do zmogljivosti vpogledov v občinstvo Customer Insights.

## <a name="create-a-new-environment"></a>Ustvarite novo okolje

1. Na desni strani glavne pasice izberite izbirnik okolja in nato možnost **+Novo**.

   :::image type="content" source="media/environment-picker.png" alt-text="Izberite izbirnik okolja.":::

1. V podoknu **Nastavitev**, vnesite **ime okolja**.

1. Izberite **vrsto** računa, odvisno od vrste vašega načrta.

1. Izberite **Regija** in izberite **Naprej**. 

1. Vnesite **ime delovnega prostora**, ki vam omogoča zbiranje podatkov za določeno spletno mesto ali aplikacije. Za več informacij glejte razdelek [Ustvarjanje delovnega prostora](create-workspace.md).

1. Izberite **vrsto delovnega prostora** (spletno ali mobilno), ki ga želite ustvariti. 

1. Izberite možnost **Prikaz naprednih nastavitev**, če želite omogočiti ali onemogočiti te izbirne nastavitve:

   - Preklopite možnost **Iz neznanega v znano** na »omogočeno«, da povežete spletne dogodke z uporabniki, ki že imajo preverjeno pristnost. Za več informacij odprite razdelek [Prepoznavanje spletnih dogodkov za obiskovalce, ki že imajo preverjeno pristnost](unknown-to-known.md)
   - Preklopite možnost **Filtriranje prometa botov** na »omogočeno«, da odstranite spletni promet botov za ta delovni prostor. 

1. Ko končate, izberite možnost **Dokončaj**. 

1. Namestite izrezek kode, da začnete prejemati podatke, nato pa izberite možnost **Končaj**, da ustvarite delovni prostor. Za več informacij si oglejte razdelek [Pregled virov za razvijalce](developer-resources.md).

> [!NOTE]
> Zdaj lahko dodate člane in jim dodelite raven dovoljenj s seznama **Vloga**. Za več informacij glejte [Vloge in dovoljenja](user-roles.md). 

Za več informacij glejte [Upravljanje okolij in delovnih prostorov](manage-environments-workspaces.md).

## <a name="work-with-your-new-environment"></a>Delajte z novim okoljem

- [Ustvarite delovni prostor](../engagement-insights/create-workspace.md) in dodajte člane.
- [Dodajte kodo na svoje spletno mesto](../engagement-insights/instrument-website.md) ali v [mobilno aplikacijo](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps).
- Oglejte si [sprotno poročilo](../engagement-insights/view-reports.md) ali ustvarite [poročila po meri](../engagement-insights/custom-reports.md).
- [Ustvarite izboljšane dogodke](../engagement-insights/refined-events.md) za izvoz.
- [Izvozite podatke](../engagement-insights/export-events.md) v Data Lake Storage.

[!INCLUDE[footer-include](../includes/footer-banner.md)]