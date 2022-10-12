---
title: Vzorčni priročnik za predvidevanje vrednosti življenjske dobe stranke (CLV)
description: Uporabite ta vzorčni priročnik, da preizkusite model za predvidevanje vrednosti življenjske dobe stranke.
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609658"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Vzorčni priročnik za predvidevanje vrednosti življenjske dobe stranke (CLV)

Ta vodnik vas vodi skozi celovit primer življenjske vrednosti stranke (CLV) predvidevanje v Customer Insights z uporabo vzorčnih podatkov. Priporočamo, da preizkusite to predvidevanje [v novem okolju](manage-environments.md).

## <a name="scenario"></a>Scenarij

Contoso je podjetje, ki proizvaja visokokakovostno kavo in kavne aparate. Izdelke prodajajo prek spletnega mesta Contoso Coffee. Podjetje želi predvideti vrednost (prihodek), ki jo lahko njihove stranke ustvarijo v naslednjih 12 mesecih. Poznavanje pričakovane vrednosti njihovih strank v naslednjih 12 mesecih jim pomaga usmeriti svoja tržna prizadevanja na stranke z visoko vrednostjo.

## <a name="prerequisites"></a>Zahteve

- Vsaj [dovoljenja sodelujočega](permissions.md).

## <a name="task-1---ingest-data"></a>1. opravilo – vnos podatkov

Preglejte članke [o zaužitju podatkov](data-sources.md) in [povezovanje z a Power Query vir podatkov](connect-power-query.md). Naslednje informacije predvidevajo, da ste seznanjeni z zaužitjem podatkov na splošno.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Vnos podatkov o strankah s platforme elektronskega poslovanja

1. Ustvari Power Query vir podatkov z imenom **e-trgovina** in izberite **Besedilo/CSV** priključek.

1. Vnesite URL za stike za elektronsko poslovanje https://aka.ms/ciadclasscontacts.

1. Med urejanjem podatkov izberite **Preobrazba** in potem **Prvo vrstico uporabite kot glave**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:
   - **DateOfBirth**: datum
   - **CreatedOn**: datum/čas/časovni pas

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pretvorite datum rojstva v datum.":::

1. V **Ime** polje v desnem podoknu preimenujte vir podatkov v **eCommerceContacts**

1. **Shranite** vir podatkov.

### <a name="ingest-online-purchase-data"></a>Vnos podatkov o spletnem nakupu

1. Dodajte še nabor podatkov z istega vira podatkov **EPoslovanje**. Znova izberite povezovalnik **Besedilo/CSV**.

1. Vnesite URL za podatke **Spletni nakupi** https://aka.ms/ciadclassonline.

1. Med urejanjem podatkov izberite **Preobrazba** in potem **Prvo vrstico uporabite kot glave**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:
   - **PurchasedOn**: datum/čas
   - **TotalPrice**: valuta

1. V **Ime** polje v stranskem podoknu preimenujte vir podatkov v **eCommercePurchases**.

1. **Shranite** vir podatkov.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Vnos podatkov o strankah iz sheme za zvestobo

1. Ustvari vir podatkov z imenom **Shema zvestobe** in izberite **Besedilo/CSV** priključek.

1. Vnesite URL za stranke zvestobe https://aka.ms/ciadclasscustomerloyalty.

1. Med urejanjem podatkov izberite **Preobrazba** in potem **Prvo vrstico uporabite kot glave**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:
   - **DateOfBirth**: datum
   - **RewardsPoints**: celo število
   - **CreatedOn**: datum/čas

1. V **Ime** polje v desnem podoknu preimenujte vir podatkov v **loyCustomers**.

1. **Shranite** vir podatkov.

### <a name="ingest-customer-data-from-website-reviews"></a>Vnesite podatke o strankah iz ocen spletnih mest

1. Ustvari vir podatkov z imenom **Spletna stran** in izberite **Besedilo/CSV** priključek.

1. Vnesite URL za preglede spletnih mest https://aka.ms/CI-ILT/WebReviews.

1. Med urejanjem podatkov izberite **Preobrazba** in potem **Prvo vrstico uporabite kot glave**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:
   - **ReviewRating**: decimalno število
   - **ReviewDate**: datum

1. V **Ime** polje v desnem podoknu preimenujte vir podatkov v **Ocene**.

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

1. Dodajte drugo dejavnost in preslikajte imena njenih polj v ustrezna polja:
   - **Subjekt dejavnosti** : Ocene: Spletna stran
   - **Primarni ključ** : ReviewId
   - **Časovni žig** : Datum pregleda
   - **Dejavnost dogodka** : ActivityTypeDisplay
   - **Dodatne podrobnosti** : ReviewRating
   - **Vrsta dejavnosti** : Pregled

1. Izvedite dejavnost.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>4. naloga – Konfiguriranje predvidevanja vrednosti življenjske dobe stranke

Z vzpostavljenimi poenotenimi profili strank in ustvarjeno dejavnostjo zaženite življenjsko vrednost stranke (CLV) predvidevanje. Za podrobne korake glejte [Življenjska vrednost stranke predvidevanje](predict-customer-lifetime-value.md).

1. Pojdi do **Inteligenca** > **Napovedi**.

1. Na **Ustvari** zavihek izberite **Uporabite model** na **Življenjska vrednost stranke** ploščica.

1. Izberite **Začetek**.

1. Model poimenujte **Predvidevanje CLV OOB eCommerce**, izhodno entiteto pa **OOBeCommerceCLVPrediction**.

1. Določite nastavitve modela:
   - **predvidevanje časovno obdobje** :**12 mesecev ali 1 leto** za določitev, kako daleč v prihodnost napovedati CLV.
   - **Aktivne stranke** :**Naj model izračuna interval nakupa** ki je časovni okvir, v katerem mora imeti stranka vsaj eno transakcijo, da se šteje za aktivno.
   - **Stranka visoke vrednosti** : ročno definirajte stranke z visoko vrednostjo kot **najboljših 30 % aktivnih strank**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Korak nastavitev v vodeni izkušnji za model CLV.":::

1. Izberite **Naprej**.

1. V koraku **Zahtevani podatki** izberite **Dodajanje podatkov**, da zagotovite podatke o zgodovini transakcij.

    :::image type="content" source="media/clv-model-required.png" alt-text="Dodajte zahtevani podatkovni korak v vodeni izkušnji za model CLV.":::

1. Izberite **SalesOrderLine** in entiteto eCommercePurchases ter izberite **Naslednji**. Zahtevani podatki se samodejno izpolnijo iz aktivnosti. Izberite **Shrani** in potem **Naslednji**.

1. The **Dodatni podatki (neobvezno)** korak vam omogoča, da dodate več podatkov o dejavnosti strank, da dobite več vpogledov v interakcije s strankami. Za ta primer izberite **Dodajte podatke** in dodajte dejavnost spletnega pregleda.

1. Izberite **Naprej**.

1. V **Posodobitve podatkov** korak, izberite **Mesečno** za modelni urnik.

1. Izberite **Naprej**.

1. Po pregledu vseh podrobnosti izberite **Shrani in zaženi**.

## <a name="task-5---review-model-results-and-explanations"></a>5. opravilo – preglejte rezultate modela in razlage

Model naj dokonča usposabljanje in ocenjevanje podatkov. Preglejte [Rezultati modela CLV in razlage](predict-customer-lifetime-value.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-value-customers"></a>6. naloga – Ustvarite segment strank z visoko vrednostjo

Z zagonom modela boste ustvarili novo entiteto, ki je navedena na zavihku **Podatki** > **Entitete**. Na podlagi entitete, ki jo je ustvaril model, lahko ustvarite nov segment za stranko.

1. Na strani z rezultati izberite **Ustvari segment**.

1. Ustvarite pravilo z uporabo **OOBeCommerceCLVPeriction** entiteto in definirajte segment:
   - **Polje** : CLVScore
   - **Operater** : večji kot
   - **Vrednost** : 1500

1. Izberite **Shrani** in **Teči** segment.

Zdaj imate segment, ki določa stranke, ki naj bi v naslednjih 12 mesecih ustvarile več kot 1500 $ prihodka. Ta segment se dinamično posodablja, če je vnesenih več podatkov. Za več informacij glejte [Ustvarjanje in upravljanje segmentov](segments.md).

> [!TIP]
> Ustvarite lahko tudi segment za model predvidevanje iz **Segmenti** stran z izbiro **Novo** in izbiranje **Ustvari iz** > **Inteligenca**. Za več informacij glejte [Ustvarite nov segment s hitrimi segmenti](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
