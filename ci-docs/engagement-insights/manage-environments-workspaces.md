---
title: Upravljanje delovnih prostorov in okolij
description: Ustvarjanje, preimenovanje in brisanje delovnih prostorov in okolij.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 09/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: a5b48db5ae23ea65bf608d67348d493bfdc7678f
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486055"
---
# <a name="manage-environments-and-workspaces"></a>Upravljanje okolij in delovnih prostorov

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Pregled

Delovni prostor je prostor za shranjevanje ter upravljanje dogodkov in poročil. Tam si lahko v realnem času ogledate dejavnost uporabnikov. Ko ustvarite delovni prostor, izberete vrsto podatkov, ki jo boste poslali delovnemu prostoru. Trenutno so podprti spletni podatki in mobilne aplikacije.

Okolje je prostor, kjer upravljate s svojimi delovnimi prostori in povezavami. Kako uporabljate okolja, je odvisno od vaše organizacije in primera uporabe. Omogoča na primer ustvarjanje:

-   enega okolja,
-   ločenih okolij za preskušanje in proizvodnjo,
-   ločenih okolij za določene skupine ali oddelke v vaši organizaciji, ki vsebujejo ustrezne dogodke za vsak občinstvo,
-   ločenih okolij za različne globalne podružnice vašega podjetja,
-   povezav do zmogljivosti vpogledov v občinstvo Customer Insights.

## <a name="choose-an-environment-and-create-a-workspace"></a>Izberite okolje in ustvarite delovni prostor 

Vsak delovni prostor mora biti v okolju. Ko ustvarite delovni prostor, lahko izberete že obstoječe okolje ali ustvarite novo. Nato lahko dodate člane delovnega prostora in začnete zbirati podatke.

**Ustvarjanje prvega delovnega prostora**

1. Pri vpogledih v interakcije izberite **Novo** iz preklopnika delovnega prostora. 

   :::image type="content" source="media/New-workspace.png" alt-text="Izbirnik delovnega prostora na strani Customer Insights.":::

1. S seznama izberite okolje ali izberite **Ustvari novo okolje**.

1. Vnesite ime in shranite **ime delovnega prostora**. 

1. Izberite vrsto okolja, ki ga želite ustvariti, odvisno od tega, ali želite dogajanje oceniti na spletnem mestu ali v mobilni aplikaciji. 

1. Lahko dodate člane in jim dodelite raven dovoljenj s seznama **Vloga**. Nato izberite **Končaj**, da ustvarite delovni prostor oz. **Naprej** za namestitev kode. 

1. Namestite izrezek kode, da začnete prejemati podatke, in nato izberite **Končano**. 

## <a name="manage-a-workspace"></a>Upravljanje delovnega prostora

V okolju lahko hkrati vzdržujete več delovnih prostorov. Od vaše [vloge](user-roles.md) je odvisno, na kakšen način lahko v njih opravljate delo. 

 - Delovni prostor lahko upravljate le kot skrbnik okolja ali skrbnik delovnega prostora.
 - Če ste skrbnik delovnega prostora, lahko preimenujete obstoječe delovne prostore ali jih izbrišete. 

### <a name="edit-a-workspace-name"></a>Urejanje imena delovnega prostora

1. Odprite **Skrbnik** > **Delovni prostor** in izberite **Nastavitve**.

1. V polje **Ime delovnega prostora** vnesite novo ime.

1. Če želite uporabiti spremembe, izberite **Shrani**.

### <a name="delete-a-workspace"></a>Brisanje delovnega prostora

Če izbrišete delovni prostor, boste trajno odstranili vso vsebino, podatke, nastavitve in dovoljenja tega prostora. Tega ni mogoče razveljaviti.

1. Odprite **Skrbnik** > **Delovni prostor** in izberite **Nastavitve**.

1. Izberite **Izbriši delovni prostor**. 

1. V pogovornemu oknu **Brisanje delovnega prostora** vnesite **POTRDITEV BRISANJA**. 

1. Izberite **Izbriši** za trajno brisanje delovnega prostora.

### <a name="manage-workspace-members"></a>Upravljanje članov delovnega prostora

1. Odprite **Skrbnik** > **Delovni prostor** in izberite **Člani**.

1. Izberite **Dodaj člane**, da omogočite dostop in [dodelite vloge](user-roles.md). Trenutno je na voljo samo **Skrbnik delovnega prostora**.

1. Izberite **Dodaj člane**, da jih dodate v svoj delovni prostor.

## <a name="manage-an-environment"></a>Upravljanje okolja

Kot skrbnik okolja lahko do okolja dostopate v levem podoknu za krmarjenje. Konfigurirate lahko nastavitve okolja, druge skrbnike okolja in delovne prostore. Izberite zavihke za premikanje med različnimi območji v skrbniškem centru.

:::image type="content" source="media/New-environment.png" alt-text="Skrbniško središče za okolje.":::

### <a name="create-an-environment"></a>Ustvarjanje okolja

1. V izbirniku delovnega prostora izberite **+Novo**.

1. V vodeni izkušnji odprite spustni meni **Okolje** in izberite **Ustvari novo okolje**. 

1. Navedite **Ime okolja**.

   :::image type="content" source="media/create-environment.png" alt-text="Začnite z vodeno izkušnjo, da navedete podrobnosti o okolju.":::

1. Izberite **Regija** in izberite **Naprej**. 

1. Navedite ime delovnega prostora in izberite, katero vrsto delovnega prostora želite ustvariti. 

1.  Po želji dodajte člane in kopirajte izrezek kode, da dokončate postopek ustvarjanja.

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

1. V pogovornemu oknu **Brisanje delovnega prostora** vnesite **POTRDITEV BRISANJA**. 

1. Izberite **Izbriši** za trajen izbris okolja.

## <a name="manage-connections"></a>Upravljanje povezav

Vzpostavitev povezav z vpogledi v občinstvo vam omogoča, da si ogledate poročila v vpogledih v občinstvo na podlagi poenotenih profilov strank. 

Za več informacij glejte [Ustvarjanje povezave med vpogledi občinstva in vpogledi v interakcije](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Upravljanje osebnih podatkov

Če želite zaščititi osebne podatke svoje stranke, lahko izbrišete ali izvozite podatke, ki omogočajo prepoznavanje končnega uporabnika.

Za več informacije glejte [Brisanje in izvoz podatkov o dogodkih, ki vsebujejo osebne podatke](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
