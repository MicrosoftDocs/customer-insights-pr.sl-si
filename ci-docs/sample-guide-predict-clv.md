---
title: Vzorčni priročnik za predvidevanje vrednosti življenjske dobe stranke (CLV)
description: Uporabite ta vzorčni priročnik, da preizkusite model za predvidevanje vrednosti življenjske dobe stranke.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 2013533ed225a396d21e51e63297d7608ce58ac6
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051657"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Vzorčni priročnik za predvidevanje vrednosti življenjske dobe stranke (CLV)

Ta priročnik vam bo z vzorčnimi podatki v celoti razložil primer predvidevanja vrednosti življenjske dobe stranke (CLV) v Customer Insights.

## <a name="scenario"></a>Scenarij

Contoso je podjetje, ki proizvaja visokokakovostne aparate za kavo in kavo. Izdelke prodajajo prek svoje spletne strani Contoso Coffee. Podjetje želi predvideti vrednost (prihodek), ki jo lahko njihove stranke ustvarijo v naslednjih 12 mesecih. Poznavanje pričakovane vrednosti njihovih strank v naslednjih 12 mesecih jim pomaga usmeriti svoja tržna prizadevanja na stranke z visoko vrednostjo.

## <a name="prerequisites"></a>Zahteve

- Vsaj [dovoljenja sodelavcev](permissions.md) v storitvi Customer Insights.
- Priporočamo, da izvedete naslednje korake [v novem okolju](manage-environments.md).

## <a name="task-1---ingest-data"></a>1. opravilo – vnos podatkov

Preglejte članke [o zaužitju podatkov](data-sources.md) in [uvoz podatkovnih virov z uporabo Power Query konektorji](connect-power-query.md). Z naslednjimi informacijami domnevamo, da ste na splošno seznanjeni z vnosom podatkov.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Vnos podatkov o strankah s platforme elektronskega poslovanja

1. Ustvarite vir podatkov z imenom **eCommerce**, izberite možnost uvoza in izberite povezovalnik **Besedilo/CSV**.

1. Vnesite URL za stike eCommerce [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Med urejanjem podatkov izberite **Pretvori** in nato **Uporabi prvo vrstico kot glavo**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:
   - **DateOfBirth**: datum
   - **CreatedOn**: datum/čas/časovni pas

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pretvorite datum rojstva v datum.":::

1. V polju »Ime« v desnem podoknu preimenujte vir podatkov iz **Poizvedba** v **StikiEPoslovanja**.

1. **Shranite** vir podatkov.

### <a name="ingest-online-purchase-data"></a>Vnos podatkov o spletnem nakupu

1. Dodajte še nabor podatkov z istega vira podatkov **EPoslovanje**. Znova izberite povezovalnik **Besedilo/CSV**.

1. Vnesite URL za podatke **Spletni nakupi** https://aka.ms/ciadclassonline.

1. Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:
   - **PurchasedOn**: datum/čas
   - **TotalPrice**: valuta

1. V stranskem podoknu v polju **Ime** preimenujte svoj vir podatkov iz **Poizvedba** v **NakupiEPoslovanja**.

1. **Shranite** vir podatkov.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Vnos podatkov o strankah iz sheme za zvestobo

1. Ustvarite vir podatkov z imenom **ShemaZvestobe**, izberite možnost uvoza in izberite povezovalnik **Besedilo/CSV**.

1. Vnesite URL za stike za elektronsko poslovanje https://aka.ms/ciadclasscustomerloyalty.

1. Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:
   - **DateOfBirth**: datum
   - **RewardsPoints**: celo število
   - **CreatedOn**: datum/čas

1. V desnem podoknu v polju **Ime** preimenujte svoj vir podatkov iz **Poizvedba** v **zvesteStranke**.

1. **Shranite** vir podatkov.

### <a name="ingest-customer-data-from-website-reviews"></a>Vnesite podatke o strankah iz ocen spletnih mest

1. Ustvarite vir podatkov z imenom **Spletno mesto**, izberite možnost uvoza in izberite povezovalnik **Besedilo/CSV**.

1. Vnesite URL za stike za elektronsko poslovanje https://aka.ms/CI-ILT/WebReviews.

1. Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:

   - **ReviewRating**: decimalno število
   - **ReviewDate**: datum

1. V polju »Ime« v desnem podoknu preimenujte vir podatkov iz **Poizvedba** na **Ocene**.

1. **Shranite** vir podatkov.

## <a name="task-2---data-unification"></a>2. opravilo – poenotenje podatkov

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>3. naloga – Konfiguriranje predvidevanja vrednosti življenjske dobe stranke

Z vzpostavljenimi poenotenimi profili strank lahko zaženemo predvidevanje vrednosti življenjske dobe stranke. Za podrobne korake glejte [Življenjska vrednost stranke predvidevanje](predict-customer-lifetime-value.md).

1. Odprite **Obveščanje**  > **Napovedi** in izberite **Model za izračun vrednosti življenjske dobe stranke**.

1. Preglejte informacije v stranskem podoknu in izberite **Začetek**.

1. Model poimenujte **Predvidevanje CLV OOB eCommerce**, izhodno entiteto pa **OOBeCommerceCLVPrediction**.

1. Določite nastavitve modela za model CLV:
   - **Časovno obdobje predvidevanja**: **12 mesecev ali 1 leto**. Ta nastavitev določa, kako daleč v prihodnost lahko napovemo vrednost življenjske dobe stranke.
   - **Dejavne stranke**: navedite, kaj dejavne stranke pomenijo vašemu podjetju. Nastavite zgodovinski časovni okvir, v katerem je morala stranka imeti vsaj eno transakcijo, da se je štela za dejavno. Model bo življenjsko vrednost stranke napovedal samo za aktivne stranke. Izberite možnost, po kateri model izračuna časovno obdobje na podlagi preteklih podatkov o transakcijah, ali pa določite časovni okvir V tem vzorčnem priročniku smo izbrali, **naj model izračuna interval nakupov**, kar je privzeta možnost.
   - **Stranke z visoko vrednostjo**: stranke z visoko vrednostjo opredelite kot percentil strank, ki največ zapravijo. Model uporablja te vhodne podatke za zagotavljanje rezultatov, ki ustrezajo vaši poslovni definiciji strank z visoko vrednostjo. Izberete lahko, naj model določi stranke z visoko vrednostjo. Pri tem je uporabljeno hevristično pravilo, ki izpelje percentil. Stranke z visoko vrednostjo lahko opredelite tudi kot percentil strank, ki bodo največ zapravile. V tem vzorčnem priročniku ročno definiramo stranke z visoko vrednostjo kot **zgornjih 30 % dejavnih strank, ki največ zapravijo** in izberite **Naprej**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Korak nastavitev v vodeni izkušnji za model CLV.":::

1. V koraku **Zahtevani podatki** izberite **Dodajanje podatkov**, da zagotovite podatke o zgodovini transakcij.

1. Dodajte entiteto **eCommercePurchases : eCommerce** in preslikajte atribute, ki jih zahteva model:
   - ID transakcije: eCommerce.eCommercePurchases.PurchaseId
   - Datum transakcije: eCommerce.eCommercePurchases.PurchasedOn
   - Znesek transakcije: eCommerce.eCommercePurchases.TotalPrice
   - ID izdelka: eCommerce.eCommercePurchases.ProductId

1. Izberite **Naprej**.

1. Nastavitev odnosa med entiteto **eCommercePurchases : eCommerce** in **eCommerceContacts : eCommerce**.

1. V koraku **Dodatni podatki (izbirno)** lahko dodate več podatkov o dejavnosti stranke. Ti podatki vam lahko pomagajo pridobiti več vpogledov v interakcije strank z vašim podjetjem, kar lahko prispeva k CLV. Z dodajanjem ključnih interakcij strank, kot so spletni dnevniki, dnevniki storitev za stranke ali zgodovina podeljevanja nagrad, lahko izboljšate natančnost predvidevanja. Izberite **Dodajanje podatkov**, da vključite več podatkov o dejavnostih strank.

1. Dodajte entiteto dejavnosti stranke in preslikajte imena polj v ustrezna polja, ki jih zahteva model:
   - Entiteta dejavnosti stranke: Reviews:Website
   - Primarni ključ: Website.Reviews.ReviewId
   - Časovni žig: Website.Reviews.ReviewDate
   - Dogodek (ime dejavnosti): Website.Reviews.ActivityTypeDisplay
   - Podrobnosti (znesek ali vrednost): Website.Reviews.ReviewRating

1. Izberite **Naprej** in konfigurirajte dejavnost in odnos med podatki o transakciji in podatki o stranki:  
   - Vrsta dejavnosti: izberite obstoječo
   - Oznaka dejavnosti: Pregled
   - Ustrezna nalepka: Website.Reviews.UserID
   - Entiteta stranke: eCommerceContacts:eCommerce
   - Odnos: WebsiteReviews

1. Izberite **Naprej** za nastavitev urnika modela.

   Model mora redno trenirati, da se nauči novih vzorcev, ko so vneseni novi podatki. Za ta primer izberite **Mesečno**.

1. Po pregledu vseh podrobnosti izberite **Shrani in zaženi**.

## <a name="task-4---review-model-results-and-explanations"></a>4. opravilo – preglejte rezultate modela in razlage

Model naj dokonča usposabljanje in ocenjevanje podatkov. Nato lahko pregledate rezultate in razlage modela CLV. Za več informacij glejte [Pregled stanja in rezultatov predvidevanja](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>5. naloga – Ustvarite segment strank z visoko vrednostjo

Z zagonom modela boste ustvarili novo entiteto, ki je navedena na zavihku **Podatki** > **Entitete**. Na podlagi entitete, ki jo je ustvaril model, lahko ustvarite nov segment za stranko.

1. Izberite **Segmenti**. 

1. Izberite **Novo** in izberite **Ustvari iz** > **Obveščanje**.

   ![Ustvarjanje segmenta z izhodnimi podatki modela.](media/segment-intelligence.png)

1. Izberite entiteto **OOBeCommerceCLVPrediction** in definirajte segment:
  - Polje: CLVScore
  - Operator: večje kot
  - Vrednost: 1500

1. Izberite **Pregled** in **Shrani**, da shranite segment.

Zdaj imate segment, ki določa stranke, ki naj bi v naslednjih 12 mesecih ustvarile več kot 1500 $ prihodka. Ta segment se dinamično posodablja, če je vnesenih več podatkov.

Za več informacij glejte [Ustvarjanje in upravljanje segmentov](segments.md).
