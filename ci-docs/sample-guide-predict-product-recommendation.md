---
title: Vzorčni vodnik za predvidevanje priporočil za izdelke
description: Uporabite ta vzorčni vodnik, da preskusite model predvidevanja priporočil za vnaprej pripravljene izdelke.
ms.date: 09/19/2022
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
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610164"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Vzorčni vodnik za predvidevanje priporočil za izdelke

Ta vodnik vas vodi skozi primer priporočila izdelka predvidevanje od konca do konca z uporabo vzorčnih podatkov. Priporočamo, da preizkusite to predvidevanje [v novem okolju](manage-environments.md).

## <a name="scenario"></a>Scenarij

Contoso je podjetje, ki proizvaja visokokakovostno kavo in kavne aparate. Izdelke prodajajo prek spletnega mesta Contoso Coffee. Njihov cilj je razumeti, katere izdelke priporočiti svojim rednim strankam. Vedeti, katere stranke so več **verjetno za nakup** jim lahko pomaga prihraniti trženjska prizadevanja z osredotočanjem na določene elemente.

## <a name="prerequisites"></a>Zahteve

- Vsaj [dovoljenja sodelavcev](permissions.md) v storitvi Customer Insights.

## <a name="task-1---ingest-data"></a>1. opravilo – vnos podatkov

Preglejte članke [o zaužitju podatkov](data-sources.md) in [povezovanje z a Power Query vir podatkov](connect-power-query.md). Naslednje informacije predvidevajo, da ste seznanjeni z zaužitjem podatkov na splošno.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Vnos podatkov o strankah s platforme elektronskega poslovanja

1. Ustvari Power Query vir podatkov z imenom **e-trgovina** in izberite **Besedilo/CSV** priključek.

1. Vnesite URL za stike e-trgovine:https://aka.ms/ciadclasscontacts.

1. Med urejanjem podatkov izberite **Preobrazba** in potem **Prvo vrstico uporabite kot glave**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:
   - **DateOfBirth**: datum
   - **CreatedOn**: datum/čas/časovni pas

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pretvorite datum rojstva v datum.":::

1. V **Ime** polje v desnem podoknu preimenujte vir podatkov v **eCommerceContacts**.

1. **Shranite** vir podatkov.

### <a name="ingest-online-purchase-data"></a>Vnos podatkov o spletnem nakupu

1. Dodajte še nabor podatkov z istega vira podatkov **EPoslovanje**. Znova izberite povezovalnik **Besedilo/CSV**.

1. Vnesite URL za podatke o spletnih nakupih https://aka.ms/ciadclassonline.

1. Med urejanjem podatkov izberite **Preobrazba** in potem **Prvo vrstico uporabite kot glave**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:
   - **PurchasedOn**: datum/čas
   - **TotalPrice**: valuta

1. V **Ime** polje v stranskem podoknu preimenujte vir podatkov v **eCommercePurchases**.

1. **Shranite** vir podatkov.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Vnos podatkov o strankah iz sheme za zvestobo

1. Ustvari vir podatkov z imenom **Shema zvestobe** in izberite **Besedilo/CSV** priključek.

1. Vnesite URL za zveste stranke https://aka.ms/ciadclasscustomerloyalty.

1. Med urejanjem podatkov izberite **Preobrazba** in potem **Prvo vrstico uporabite kot glave**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:
   - **DateOfBirth**: datum
   - **RewardsPoints**: celo število
   - **CreatedOn**: datum/čas

1. V **Ime** polje v desnem podoknu preimenujte vir podatkov v **loyCustomers**.

1. **Shranite** vir podatkov.

## <a name="task-2---data-unification"></a>2. opravilo – poenotenje podatkov

Preglejte članek [o poenotenju podatkov](data-unification.md). Naslednje informacije predvidevajo, da poznate poenotenje podatkov na splošno.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Naloga 3 - Ustvarite dejavnost zgodovine transakcij

Preglejte članek [o dejavnostih strank](activities.md). Naslednje informacije predvidevajo, da ste seznanjeni z ustvarjanjem dejavnosti na splošno.

1. Ustvarite dejavnost, imenovano **eCommercePurchases** z *Nakupi e-trgovine: e-trgovina* entiteta in njen primarni ključ, **PurchaseId**.

1. Ustvarite razmerje med *Nakupi e-trgovine: e-trgovina* in *eCommerceContacts:eCommerce* z **ContactID** kot tuji ključ za povezavo obeh entitet.

1. Izberite **Skupna cena** za **EventActivity** in **PurchasedOn** za **Časovni žig**.

1. Izberite **SalesOrderLine** za **Vrsta dejavnosti** in semantično preslika podatke o dejavnosti.

1. Izvedite dejavnost.

## <a name="task-4---configure-product-recommendation-prediction"></a>4. opravilo – konfiguracija predvidevanja priporočil za izdelke

Z vzpostavljenimi poenotenimi profili strank in ustvarjeno dejavnostjo zaženite priporočilo za izdelek predvidevanje.

1. Pojdi do **Inteligenca** > **Napovedi**.

1. Na **Ustvari** zavihek izberite **Uporabite model** na **Priporočila za izdelke (predogled)** ploščica.

1. Izberite **Začetek**.

1. Poimenujte model **Model predvidevanja priporočil za vnaprej pripravljene izdelke** in izhodno entiteto **ModelPredvidevanjaPriporočilZaVnaprejPripravljeneIzdelke**.

1. Izberite **Naprej**.

1. Določite nastavitve modela:
   - **Število izdelkov** :**5** da določite, koliko izdelkov želite priporočiti svojim strankam.
   - **Pričakovani ponovni nakupi** :**ja** da v priporočilo vključi že kupljene izdelke.
   - **Okno za pogled nazaj:** **365 dni** da določite, kako daleč bo model pogledal nazaj, preden ponovno priporoči izdelek.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Oblikujte nastavitve za model s priporočili za izdelke.":::

1. Izberite **Naprej**.

1. V **Dodajte zgodovino nakupov** korak, izberite **Dodajte podatke**.

1. Izberite **SalesOrderLine** in entiteto eCommercePurchases ter izberite **Naslednji**. Zahtevani podatki se samodejno izpolnijo iz aktivnosti. Izberite **Shrani** in potem **Naslednji**.

1. Preskoči **Dodajte informacije o izdelku** in **Filtri izdelkov** korake, ker nimamo podatkov o izdelkih.

1. V **Posodobitve podatkov** korak, izberite **Mesečno** za modelni urnik.

1. Izberite **Naprej**.

1. Po pregledu vseh podrobnosti izberite **Shrani in zaženi**.

## <a name="task-5---review-model-results-and-explanations"></a>5. opravilo – preglejte rezultate modela in razlage

Model naj dokonča usposabljanje in ocenjevanje podatkov. Preglejte [razlage modelov priporočil za izdelke](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>6. opravilo – ustvarjanje segmenta najbolj prodajanih izdelkov

Z zagonom modela boste ustvarili novo entiteto, ki je navedena na zavihku **Podatki** > **Entitete**. Na podlagi entitete, ki jo je ustvaril model, lahko ustvarite nov segment.

1. Na strani z rezultati izberite **Ustvari segment**.

1. Ustvarite pravilo z uporabo **OOBProductRecommendationModelPrediction** entiteto in definirajte segment:
   - **Polje** : ID izdelka
   - **Vrednost** : Izberite prve tri ID-je izdelkov

1. Izberite **Shrani** in **Teči** segment.

Zdaj imate segment, ki se dinamično posodablja in identificira stranke, ki bi jih morda zanimal nakup petih najbolj priporočenih izdelkov. Za več informacij glejte [Ustvarjanje in upravljanje segmentov](segments.md).

> [!TIP]
> Ustvarite lahko tudi segment za model predvidevanje iz **Segmenti** stran z izbiro **Novo** in izbiranje **Ustvari iz** > **Inteligenca**. Za več informacij glejte [Ustvarite nov segment s hitrimi segmenti](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
