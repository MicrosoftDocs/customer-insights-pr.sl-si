---
title: Vzorčni vodnik za predvidevanje priporočil za izdelke
description: Uporabite ta vzorčni vodnik, da preskusite model predvidevanja priporočil za vnaprej pripravljene izdelke.
ms.date: 05/16/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762706"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Vzorčni vodnik za predvidevanje priporočil za izdelke

S pomočjo spodnjih vzorčnih podatkov vas bomo vodili skozi celotni primer predvidevanja priporočil za izdelke.

## <a name="scenario"></a>Scenarij

Contoso je podjetje, ki proizvaja visokokakovostno kavo in kavne avtomate, ki jih prodaja prek njihovega spletnega mesta Contoso Coffee. Njihov cilj je razumeti, katere izdelke priporočiti svojim rednim strankam. Če vedo, katere izdelke stranke bolj **verjetno kupujejo**, si prihranijo tržna prizadevanja, saj se lahko osredotočijo na določene izdelke.

## <a name="prerequisites"></a>Zahteve

- Vsaj [dovoljenja sodelavcev](permissions.md) v storitvi Customer Insights.
- Priporočamo, da izvedete naslednje korake [v novem okolju](manage-environments.md).

## <a name="task-1---ingest-data"></a>1. opravilo – vnos podatkov

Preglejte članke [o zaužitju podatkov](data-sources.md) in [uvoz podatkovnih virov z uporabo Power Query konektorji](connect-power-query.md) posebej. Z naslednjimi informacijami domnevamo, da ste na splošno seznanjeni z vnosom podatkov.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Vnos podatkov o strankah s platforme elektronskega poslovanja

1. Ustvarite vir podatkov z imenom **EPoslovanje**, izberite možnost uvoza in izberite povezovalnik **Besedilo/CSV**.

1. Vnesite URL za stike e-trgovine: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:
   - **DateOfBirth**: datum
   - **CreatedOn**: datum/čas/časovni pas

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pretvorite datum rojstva v datum.":::

1. V polju »Ime« v desnem podoknu preimenujte vir podatkov iz **Poizvedba** v **StikiEPoslovanja**.

1. **Shranite** vir podatkov.

### <a name="ingest-online-purchase-data"></a>Vnos podatkov o spletnem nakupu

1. Dodajte še nabor podatkov z istega vira podatkov **EPoslovanje**. Znova izberite povezovalnik **Besedilo/CSV**.

1. Vnesite URL za **Spletni nakupi** podatki [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline).

1. Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:
   - **PurchasedOn**: datum/čas
   - **TotalPrice**: valuta

1. V stranskem podoknu v polju **Ime** preimenujte svoj vir podatkov iz **Poizvedba** v **NakupiEPoslovanja**.

1. **Shranite** vir podatkov.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Vnos podatkov o strankah iz sheme za zvestobo

1. Ustvarite vir podatkov z imenom **ShemaZvestobe**, izberite možnost uvoza in izberite povezovalnik **Besedilo/CSV**.

1. Vnesite URL za stike e-trgovine [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty).

1. Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:
   - **DateOfBirth**: datum
   - **RewardsPoints**: celo število
   - **CreatedOn**: datum/čas

1. V desnem podoknu v polju **Ime** preimenujte svoj vir podatkov iz **Poizvedba** v **zvesteStranke**.

1. **Shranite** vir podatkov.

## <a name="task-2---data-unification"></a>2. opravilo – poenotenje podatkov

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>3. opravilo – konfiguracija predvidevanja priporočil za izdelke

Z vzpostavljenimi enotnimi profili strank lahko zdaj izvajamo priporočilo izdelka predvidevanje.

1. V razdelku **Obveščanje** > **Predvidevanje** izberite **Priporočilo za izdelke**.

1. Izberite **Začetek**.

1. Poimenujte model **Model predvidevanja priporočil za vnaprej pripravljene izdelke** in izhodno entiteto **ModelPredvidevanjaPriporočilZaVnaprejPripravljeneIzdelke**.

1. Določite tri pogoje za model:

   - **Število izdelkov**: nastavite to vrednost na **5**. Ta nastavitev določi, koliko izdelkov želite priporočiti svojim strankam.

   - **Pričakovani ponovljeni nakupi**: izberite **Da**, če želite izdelke vključiti v priporočilo izdelkov, ki so jih vaše stranke že kupile.

   - **Obdobje zajema podatkov:** izberite vsaj **365 dni**. Ta nastavitev določa obdobje zajema podatkov strankine dejavnosti, ki ga bo model upošteval pri vnosu priporočil.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Oblikujte nastavitve za model s priporočili za izdelke.":::

1. V **Dodajte zahtevane podatke** korak, izberite **Dodajte podatke**.

1. V **Dodajte podatke** podoknu, izberite **SalesOrderLine** kot subjekt zgodovine nakupov. Na tej točki verjetno še ni konfiguriran. Odprite povezavo v podoknu, da ustvarite dejavnost z naslednjimi koraki:
   1. Vnesite an **Ime dejavnosti** in izberite *Nakupi e-trgovine: e-trgovina* kot **Subjekt dejavnosti**. The **Primarni ključ** je *PurchaseId*.
   1. Določite in poimenujte razmerje do *Kontakti e-trgovine: subjekt e-trgovine* in izberite **ContactId** kot tuji ključ.
   1. Za poenotenje dejavnosti nastavite **Dejavnost dogodka** kot *Skupna cena* in časovni žig do *Kupljeno dne*. Določite lahko več polj, kot je opisano v [Aktivnosti strank](activities.md).
   1. Za **Vrsta dejavnosti**, izberite *SalesOrderLine*. Preslikajte naslednja polja dejavnosti:
      - ID vrstice naročila: PurchaseId
      - ID naročila: PurchaseId
      - Podatki o naročilu: PurchasedOn
      - ID izdelka: ProductId
      - Znesek: TotalPrice
   1. Preglejte in dokončajte dejavnost, preden se vrnete na konfiguracijo modela.

1. Nazaj v **Izberite dejavnosti** korak, izberite novo ustvarjeno dejavnost v **dejavnosti** oddelek. Izberite **Naslednji** in preslikava atributov je že izpolnjena. Izberite **Shrani**.

1. V tem vzorčnem vodniku preskočimo **Dodajte informacije o izdelku** in **Filtri za izdelke** nastavljeno, ker nimamo podatkov o izdelku.

1. V **Posodobitve podatkov** korak, nastavite urnik modela.

   Model se mora redno usposabljati, da se nauči novih vzorcev, ko vnese nove podatke. V tem primeru izberite **Mesečno**.

1. Po pregledu vseh podrobnosti izberite **Shrani in zaženi**. Prvi zagon modela bo trajal nekaj minut.

## <a name="task-4---review-model-results-and-explanations"></a>4. opravilo – preglejte rezultate modela in razlage

Model naj dokonča usposabljanje in ocenjevanje podatkov. Zdaj lahko pregledate pojasnila modela s priporočili za izdelke. Za več informacij glejte [Pregled stanja in rezultatov predvidevanja](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>5. opravilo – ustvarjanje segmenta najbolj prodajanih izdelkov

Z zagonom produkcijskega modela ustvarite novo entiteto, ki jo lahko vidite v razdelku **Podatki** > **Entitete**.

Na podlagi entitete, ki jo je ustvaril model, lahko ustvarite nov segment.

1. Izberite **Segmenti**. Izberite **Novo** in izberite **Ustvarite iz inteligence**.

   ![Ustvarjanje segmenta z izhodnimi podatki modela.](media/segment-intelligence.png)

1. Izberite končno točko **ModelPredvidevanjaPriporočilZaVnaprejPripravljeneIzdelke** in določite segment:

   - Polje: IDIzdelka
   - Vrednost: izberite najboljše tri ID-je izdelka

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Ustvarite segment iz rezultatov modela.":::

Zdaj imate segment, ki se dinamično posodablja in identificira stranke, ki bi jih morda zanimale nakup treh najbolj priporočenih izdelkov.

Za več informacij glejte [Ustvarjanje in upravljanje segmentov](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
