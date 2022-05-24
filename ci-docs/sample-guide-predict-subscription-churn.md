---
title: Vzorčni vodnik za predvidevanje izgube naročnin
description: S tem vzorčnim vodnikom preizkusite vnaprej pripravljeni model za predvidevanje izgube naročnin.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 5a8eeafecacef3d0bb4a798b698cf490423ca98d
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741431"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Vzorčni vodnik za predvidevanje izgube naročnin

S spodnjimi vzorčnimi podatki vam bomo razložili celovit primer predvidevanja izgube naročnin. 

## <a name="scenario"></a>Scenarij

Contoso je podjetje, ki proizvaja visokokakovostno kavo in kavne avtomate, ki jih prodaja prek njihovega spletnega mesta Contoso Coffee. Pred kratkim so začeli naročniško dejavnost, s katero so stranke redno dobivale kavo. Njihov cilj je razumeti, katere naročene stranke bi lahko v naslednjih nekaj mesecih odpovedale naročnino. Znanje o tem, katere stranke se bodo **verjetno izgubile**, jim lahko pomaga, da bolje izkoristijo tržna prizadevanja tako, da se osredotočijo na njihovo ohranitev.

## <a name="prerequisites"></a>Zahteve

- Vsaj [dovoljenja sodelavcev](permissions.md) v storitvi Customer Insights.
- Priporočamo, da izvedete naslednje korake [v novem okolju](manage-environments.md).

## <a name="task-1---ingest-data"></a>1. opravilo – vnos podatkov

Preglejte članke [o zaužitju podatkov](data-sources.md) in [uvoz podatkovnih virov z uporabo Power Query konektorji](connect-power-query.md) posebej. Z naslednjimi informacijami domnevamo, da ste na splošno seznanjeni z vnosom podatkov. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Vnos podatkov o strankah s platforme elektronskega poslovanja

1. Ustvarite vir podatkov z imenom **EPoslovanje**, izberite možnost uvoza in izberite povezovalnik **Besedilo/CSV**.

1. Vnesite URL za stike za elektronsko poslovanje https://aka.ms/ciadclasscontacts.

1. Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:

   - **DateOfBirth**: datum
   - **CreatedOn**: datum/čas/časovni pas

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pretvorite datum rojstva v datum.":::

1. V polju **Ime** v desnem podoknu preimenujte vir podatkov iz **Poizvedba** v **StikiEPoslovanja**

1. Shranite vir podatkov.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Vnos podatkov o strankah iz sheme za zvestobo

1. Ustvarite vir podatkov z imenom **ShemaZvestobe**, izberite možnost uvoza in izberite povezovalnik **Besedilo/CSV**.

1. Vnesite URL za stike za elektronsko poslovanje https://aka.ms/ciadclasscustomerloyalty.

1. Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:

   - **DateOfBirth**: datum
   - **RewardsPoints**: celo število
   - **CreatedOn**: datum/čas

1. V desnem podoknu v polju **Ime** preimenujte svoj vir podatkov iz **Poizvedba** v **zvesteStranke**.

1. Shranite vir podatkov.

### <a name="ingest-subscription-information"></a>Vnos podatkov o naročnini

1. Ustvarite vir podatkov z imenom **ZgodovinaNaročnin**, izberite možnost uvoza in izberite povezovalnik **Besedilo/CSV**.

1. Vnesite URL za stike za elektronsko poslovanje https://aka.ms/ciadchurnsubscriptionhistory.

1. Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:

   - **SubscriptionID**: celo število
   - **SubscriptionAmount**: valuta
   - **SubscriptionEndDate**: datum/čas
   - **SubscriptionStartDate**: datum/čas
   - **TransactionDate**: datum/čas
   - **IsRecurring**: True/False
   - **Is_auto_renew**: True/False
   - **RecurringFrequencyInMonths**: celo število

1. V desnem podoknu v polju **Ime** preimenujte svoj vir podatkov iz **Poizvedba** v **SubscriptionHistory**.

1. Shranite vir podatkov.

### <a name="ingest-customer-data-from-website-reviews"></a>Vnesite podatke o strankah iz ocen spletnih mest

1. Ustvarite vir podatkov z imenom **Spletno mesto**, izberite možnost uvoza in izberite povezovalnik **Besedilo/CSV**.

1. Vnesite URL za stike za elektronsko poslovanje https://aka.ms/ciadclasswebsite.

1. Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:

   - **ReviewRating**: celo število
   - **ReviewDate**: datum

1. V polju »Ime« v desnem podoknu preimenujte vir podatkov iz **Poizvedba** v **spletneOcene**.

## <a name="task-2---data-unification"></a>2. opravilo – poenotenje podatkov

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-the-subscription-churn-prediction"></a>3. opravilo – konfiguracija predvidevanja izgube naročnin

Z vzpostavljenimi poenotenimi profili strank lahko zdaj zaženemo predvidevanje izgube naročnin. Za podrobnejše korake glejte [Odliv naročnin predvidevanje](predict-subscription-churn.md) Članek. 

1. Odprite **Obveščanje** > **Odkrivanje** in izberite uporabo možnosti **Model izgube strank**.

1. Izberite možnost **Naročnina** in izberite **Začetek**.

1. Poimenujte model **Predvidevanje izgube naročnine OOB** in izhodno entiteto **PredvidevanjeIzgubeNaročnineOOB**.

1. Določite dva pogoja za model izgube:

   * **Dnevi po koncu naročnine**: **vsaj 60** dni. Če stranka v tem obdobju po preteku naročnine ne podaljša naročnine, se šteje za izgubljeno. 

   * **Opredelitev izgube**: **vsaj 93** dni. Trajanje, ki ga model predvideva, za stranke, ki bi se lahko izgubile. Bolj kot gledate v prihodnost, manj natančni so rezultati.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Izberite časovno obdobje za predvidevanje modela in opredelitev izgube.":::

1. Izberite **Dodajanje zahtevanih podatkov** in izberite **Dodajanje podatkov** za zgodovino naročnin.

1. Dodajte entiteto **Naročnina: ZgodovinaNaročnin** in preslikajte polja iz elektronskega poslovanja v ustrezna polja, ki jih zahteva model.

1. Združite entiteto **Naročnina: ZgodovinaNaročnin** z **StikiEPoslovanja: EPoslovanje**, poimenujte odnos **NaročninaEPoslovanja**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Pridružite se entitetam elektronskega poslovanja.":::

1. V razdelku Dejavnosti strank dodajte entiteto **spletneOcene: Spletno mesto** in preslikajte polja iz spletneOcene v ustrezna polja, ki jih zahteva model. 
   - Primarni ključ: ReviewId
   - Časovni žig: ReviewDate
   - Dogodek: ReviewRating

1. Konfigurirajte dejavnost za ocene spletnih mest. Izberite dejavnost **Preglej** in združite entiteto **spletneOcene: Spletno mesto** z **StikiEPoslovanja: EPoslovanje**.

1. Izberite **Naprej** za nastavitev urnika modela.

   Model se mora redno usposabljati, da se nauči novih vzorcev, ko vnese nove podatke. V tem primeru izberite **Mesečno**.

1. Po pregledu vseh podrobnosti izberite **Shrani in zaženi**.

## <a name="task-4---review-model-results-and-explanations"></a>4. opravilo – preglejte rezultate modela in razlage

Model naj dokonča usposabljanje in ocenjevanje podatkov. Zdaj si lahko ogledate razlage modela izgube naročnine. Za več informacij glejte [Pregled stanja in rezultatov predvidevanja](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>5. opravilo – ustvarjanje segmenta strank z visokim tveganjem izgube

Z zagonom produkcijskega modela ustvarite novo entiteto, ki jo lahko vidite v razdelku **Podatki** > **Entitete**.   

Na podlagi entitete, ki jo je ustvaril model, lahko ustvarite nov segment.

1.  Izberite **Segmenti**. Izberite **Novo** in izberite **Ustvari iz** > **Obveščanje**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Ustvarjanje segmenta z izhodnimi podatki modela.":::

1. Izberite končno točko **PredvidevanjeIzgubeNaročnineOOB** in definirajte segment: 
   - Polje: ChurnScore
   - Operator: večje kot
   - Vrednost: 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Nastavite segment izgube naročnine.":::

Zdaj imate segment, ki se dinamično posodablja, v katerem so prepoznane stranke z visokim tveganjem izgube za to naročniško dejavnost.

Za več informacij glejte [Ustvarjanje in upravljanje segmentov](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]