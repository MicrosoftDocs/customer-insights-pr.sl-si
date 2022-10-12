---
title: Vzorčni vodnik za predvidevanje izgube glede transakcij
description: S tem vzorčnim vodnikom preizkusite vnaprej pripravljeni model za predvidevanje izgube glede transakcij.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609705"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Vzorčni vodnik za predvidevanje izgube glede transakcij

Ta vodnik vam bo razložil primer odliva transakcij od konca do konca predvidevanje z uporabo vzorčnih podatkov. Priporočamo, da preizkusite to predvidevanje [v novem okolju](manage-environments.md).

## <a name="scenario"></a>Scenarij

Contoso je podjetje, ki proizvaja visokokakovostno kavo in kavne aparate. Izdelke prodajajo prek spletnega mesta Contoso Coffee. Njihov cilj je vedeti, katere stranke, ki običajno redno kupujejo njihove izdelke, ne bodo več aktivne stranke v naslednjih 60 dneh. Znanje o tem, katere stranke se bodo **verjetno izgubile**, jim lahko pomaga, da bolje izkoristijo tržna prizadevanja tako, da se osredotočijo na njihovo ohranitev.

## <a name="prerequisites"></a>Zahteve

- Vsaj [dovoljenja sodelujočega](permissions.md).

## <a name="task-1---ingest-data"></a>1. opravilo – vnos podatkov

Preglejte članke [o zaužitju podatkov](data-sources.md) in [povezovanje z a Power Query vir podatkov](connect-power-query.md). Naslednje informacije predvidevajo, da ste seznanjeni z zaužitjem podatkov na splošno.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Vnos podatkov o strankah s platforme elektronskega poslovanja

1. Ustvari vir podatkov z imenom **e-trgovina** in izberite **Besedilo/CSV** priključek.

1. Vnesite URL za stike za elektronsko poslovanje https://aka.ms/ciadclasscontacts.

1. Med urejanjem podatkov izberite **Preobrazba** in potem **Prvo vrstico uporabite kot glave**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:

   - **DateOfBirth**: datum
   - **CreatedOn**: datum/čas/časovni pas

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Spremeni datum rojstva v datum.":::

1. V **Ime** polje v desnem podoknu preimenujte vir podatkov v **eCommerceContacts**

1. Shranite vir podatkov.

### <a name="ingest-online-purchase-data"></a>Vnos podatkov o spletnem nakupu

1. Dodajte še nabor podatkov z istega vira podatkov **EPoslovanje**. Znova izberite povezovalnik **Besedilo/CSV**.

1. Vnesite URL za podatke o spletnih nakupih https://aka.ms/ciadclassonline.

1. Med urejanjem podatkov izberite **Preobrazba** in potem **Prvo vrstico uporabite kot glave**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:

   - **PurchasedOn**: datum/čas
   - **TotalPrice**: valuta

1. V **Ime** polje v desnem podoknu preimenujte vir podatkov v **eCommercePurchases**.

1. Shranite vir podatkov.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Vnos podatkov o strankah iz sheme za zvestobo

1. Ustvari vir podatkov z imenom **Shema zvestobe** in izberite **Besedilo/CSV** priključek.

1. Vnesite URL za stike za elektronsko poslovanje https://aka.ms/ciadclasscustomerloyalty.

1. Med urejanjem podatkov izberite **Preobrazba** in potem **Prvo vrstico uporabite kot glave**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:

   - **DateOfBirth**: datum
   - **RewardsPoints**: celo število
   - **CreatedOn**: datum/čas

1. V **Ime** polje v desnem podoknu preimenujte vir podatkov v **loyCustomers**.

1. Shranite vir podatkov.

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

## <a name="task-4---configure-transaction-churn-prediction"></a>4. opravilo – konfiguracija predvidevanja izgube glede transakcij

Z vzpostavljenimi poenotenimi profili strank in aktivnostjo zaženite odliv transakcij predvidevanje.

1. Pojdi do **Inteligenca** > **Napovedi**.

1. Na **Ustvari** zavihek izberite **Uporabite model** na **Model odliva strank**.

1. Izberite **Transakcijski** za vrsto odtoka in nato **Začeti**.

1. Poimenujte model **Predvidevanje izgube glede transakcij elektronskega poslovanja OOB** in izhodno entiteto **PredvidevanjeIzgubeElektronskegaPoslovanjaOOB**.

1. Izberite **Naprej**.

1. Določite nastavitve modela:

   - **predvidevanje okno** :**60** dni, da določimo, kako daleč v prihodnost želimo predvideti odliv strank.

   - **Opredelitev odliva** :**60** dni za navedbo trajanja brez nakupa, po katerem se stranka šteje za odpuščeno.

     :::image type="content" source="media/model-levers.PNG" alt-text="Izberite nastavitve modela predvidevanje Definicija okna in odmika.":::

1. Izberite **Naprej**.

1. Za zgodovino nakupov izberite **Zgodovina nakupov (priporočeno)** in nato **Dodajanje podatkov**.

1. Izberite **SalesOrderLine** in entiteto eCommercePurchases ter izberite **Naslednji**. Zahtevani podatki se samodejno izpolnijo iz aktivnosti. Izberite **Shrani** in potem **Naslednji**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Pridružite se entitetam elektronskega poslovanja.":::

1. Preskoči **Dodatni podatki (neobvezno)** korak.

1. V **Posodobitve podatkov** korak, izberite **Mesečno** za modelni urnik.

1. Po pregledu vseh podrobnosti izberite **Shrani in zaženi**.

## <a name="task-5---review-model-results-and-explanations"></a>5. opravilo – preglejte rezultate modela in razlage

Model naj dokonča usposabljanje in ocenjevanje podatkov. Preglejte razlage modela odliva. Za več informacij glejte [Oglejte si predvidevanje rezultate](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>6. opravilo – ustvarjanje segmenta strank z visokim tveganjem izgube

Z izvajanjem proizvodnega modela se ustvari nova entiteta, ki je navedena na **podatki** > **Entitete**. Na podlagi entitete, ki jo je ustvaril model, lahko ustvarite nov segment.

1. Na strani z rezultati izberite **Ustvari segment**.

1. Ustvarite pravilo z uporabo **OOBeCommerceChurnPrediction** entiteto in definirajte segment:
   - **Polje** : ChurnScore
   - **Operater** : večji kot
   - **Vrednost** : 0,6

1. Izberite **Shrani** in **Teči** segment.

Zdaj imate segment, ki se dinamično posodablja in identificira stranke z visokim tveganjem odhoda. Za več informacij glejte [Ustvarjanje in upravljanje segmentov](segments.md).

> [!TIP]
> Ustvarite lahko tudi segment za model predvidevanje iz **Segmenti** stran z izbiro **Novo** in izbiranje **Ustvari iz** > **Inteligenca**. Za več informacij glejte [Ustvarite nov segment s hitrimi segmenti](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
