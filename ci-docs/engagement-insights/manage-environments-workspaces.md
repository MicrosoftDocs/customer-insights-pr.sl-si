---
title: Upravljanje delovnih prostorov in okolij
description: Ustvarjanje, preimenovanje in brisanje delovnih prostorov in okolij.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 279af24358a1d6ea2b4cc75d5496042af73a7cae
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645466"
---
# <a name="manage-environments-and-workspaces"></a>Upravljanje okolij in delovnih prostorov

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Pregled

Ta tema predstavlja, kako upravljati delovne prostore in okolja, ko so že ustvarjena. 

- *Delovni prostor* je prostor za shranjevanje ter upravljanje dogodkov in poročil. Tam si lahko v realnem času ogledate dejavnost uporabnikov. Ko ustvarite delovni prostor, izberete vrsto podatkov, ki jo boste poslali delovnemu prostoru. Trenutno so podprti spletni podatki in mobilne aplikacije. Za več informacij glejte razdelek [Ustvarjanje delovnega prostora in dodajanje članov](create-workspace.md).

- *Okolje* je prostor, kjer upravljate s svojimi delovnimi prostori in povezavami. Za več informacij glejte [Ustvarjanje novega okolja](create-new-environment.md).

## <a name="manage-an-existing-workspace"></a>Upravljanje obstoječega delovnega prostora

V okolju lahko hkrati vzdržujete več delovnih prostorov. Od vaše [vloge](user-roles.md) je odvisno, na kakšen način lahko v njih opravljate delo. 

 - Delovni prostor lahko upravljate le kot skrbnik okolja ali skrbnik delovnega prostora.
 - Če ste skrbnik delovnega prostora, lahko preimenujete obstoječe delovne prostore ali jih izbrišete. 

:::image type="content" source="media/workspace-edit.png" alt-text="Središče skrbnika delovnega prostora":::

### <a name="edit-a-workspace-name"></a>Urejanje imena delovnega prostora

1. Odprite **Skrbnik** > **Delovni prostor** in izberite **Nastavitve**.

1. V polje **Ime delovnega prostora** vnesite novo ime.

1. Če želite uporabiti spremembe, izberite **Shrani**.

### <a name="delete-a-workspace"></a>Brisanje delovnega prostora

Če izbrišete delovni prostor, boste trajno odstranili vso vsebino, podatke, nastavitve in dovoljenja tega prostora. Tega ni mogoče razveljaviti.

1. Odprite **Skrbnik** > **Delovni prostor** in izberite **Nastavitve**.

1. Izberite **Izbriši delovni prostor**. 

1. V pogovornem oknu **Brisanje delovnega prostora**, vnesite napis **POTRDI BRISANJE** z velikimi tiskanimi črkami. 

1. Izberite **Izbriši** za trajno brisanje delovnega prostora.

### <a name="manage-workspace-members"></a>Upravljanje članov delovnega prostora

1. Odprite **Skrbnik** > **Delovni prostor** in izberite **Člani**.

1. Izberite **Dodaj člane**, da omogočite dostop in [dodelite vloge](user-roles.md). Trenutno je na voljo samo **Skrbnik delovnega prostora**.

1. Izberite **Dodaj člane**, da jih dodate v svoj delovni prostor.

## <a name="manage-an-existing-environment"></a>Upravljanje obstoječega okolja

Kot skrbnik okolja lahko do okolja dostopate v levem podoknu za krmarjenje. Konfigurirate lahko nastavitve okolja, druge skrbnike okolja in delovne prostore. Izberite zavihke za premikanje med različnimi območji v skrbniškem centru.

:::image type="content" source="media/environment-edit.png" alt-text="Skrbniško središče za okolje.":::

### <a name="rename-an-environment"></a>Preimenovanje okolja

1. Odprite **Skrbnik** > **Okolje** in izberite **Nastavitve**.

1. Posodobite **Ime okolja** in izberite **Shrani**, da uveljavite spremembe.

### <a name="manage-environment-members"></a>Upravljanje članov okolja

1. Odprite **Skrbnik** > **Okolje** in izberite **Člani**.

1. Izberite **Dodaj člane**, da posodobite člane in [dodelite vloge](user-roles.md). Trenutno je na voljo samo **Skrbnik okolja**.

1. Izberite **Dodaj člane**, da jih dodate v svoje okolje.

### <a name="delete-an-environment"></a>Brisanje okolja

Skrbniki okolja lahko izbrišejo okolja. Preden lahko izbrišete okolje, morate odstraniti vse njegove delovne prostore.

1. Odprite **Skrbnik** > **Okolje** in izberite **Nastavitve**.

1. Izberite **Izbriši okolje**. 

1. V pogovornem oknu **Brisanje delovnega prostora**, vnesite napis **POTRDI BRISANJE** z velikimi tiskanimi črkami. 

1. Izberite **Izbriši** za trajen izbris okolja.

## <a name="manage-connections"></a>Upravljanje povezav

Vzpostavitev povezav z vpogledi v občinstvo vam omogoča, da si ogledate poročila v vpogledih v občinstvo na podlagi poenotenih profilov strank. 

Za več informacij glejte [Ustvarjanje povezave med vpogledi občinstva in vpogledi v interakcije](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Upravljanje osebnih podatkov

Če želite zaščititi osebne podatke svoje stranke, lahko izbrišete ali izvozite podatke, ki omogočajo prepoznavanje končnega uporabnika.

Za več informacije glejte [Brisanje in izvoz podatkov o dogodkih, ki vsebujejo osebne podatke](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
