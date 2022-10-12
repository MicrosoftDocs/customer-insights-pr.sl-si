---
title: Vzorčni vodnik za predvidevanje izgube naročnin
description: S tem vzorčnim vodnikom preizkusite vnaprej pripravljeni model za predvidevanje izgube naročnin.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610026"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Vzorčni vodnik za predvidevanje izgube naročnin

Ta vodnik vam bo razložil primer od konca do konca odliva naročnin predvidevanje z uporabo vzorčnih podatkov. Priporočamo, da preizkusite to predvidevanje [v novem okolju](manage-environments.md).

## <a name="scenario"></a>Scenarij

Contoso je podjetje, ki proizvaja visokokakovostno kavo in kavne aparate. Izdelke prodajajo prek spletnega mesta Contoso Coffee. Pred kratkim so začeli naročniško dejavnost, s katero so stranke redno dobivale kavo. Njihov cilj je razumeti, katere naročene stranke bi lahko preklicale naročnino v naslednjih nekaj mesecih. Vedeti, katera od njihovih strank je **verjetno, da bo nastal** jim lahko pomaga prihraniti tržna prizadevanja tako, da se osredotoči na njihovo ohranitev.

## <a name="prerequisites"></a>Zahteve

- Vsaj [dovoljenja sodelavcev](permissions.md) v storitvi Customer Insights.

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

1. Shranite vir podatkov.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Vnos podatkov o strankah iz sheme za zvestobo

1. Ustvari vir podatkov z imenom **Shema zvestobe** in izberite **Besedilo/CSV** priključek.

1. Vnesite URL za stranke zvestobe https://aka.ms/ciadclasscustomerloyalty.

1. Med urejanjem podatkov izberite **Preobrazba** in potem **Prvo vrstico uporabite kot glave**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:
   - **DateOfBirth**: datum
   - **RewardsPoints**: celo število
   - **CreatedOn**: datum/čas

1. V **Ime** polje v desnem podoknu preimenujte vir podatkov v **loyCustomers**.

1. Shranite vir podatkov.

### <a name="ingest-subscription-information"></a>Vnos podatkov o naročnini

1. Ustvari vir podatkov z imenom **Zgodovina naročnine** in izberite **Besedilo/CSV** priključek.

1. Vnesite URL za naročnine https://aka.ms/ciadchurnsubscriptionhistory.

1. Med urejanjem podatkov izberite **Preobrazba** in potem **Prvo vrstico uporabite kot glave**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:
   - **SubscriptionID**: celo število
   - **SubscriptionAmount**: valuta
   - **SubscriptionEndDate**: datum/čas
   - **SubscriptionStartDate**: datum/čas
   - **TransactionDate**: datum/čas
   - **IsRecurring**: True/False
   - **Is_auto_renew**: True/False
   - **RecurringFrequencyInMonths**: celo število

1. V **Ime** polje v desnem podoknu preimenujte vir podatkov v **Zgodovina naročnine**.

1. Shranite vir podatkov.

### <a name="ingest-customer-data-from-website-reviews"></a>Vnesite podatke o strankah iz ocen spletnih mest

1. Ustvari vir podatkov z imenom **Spletna stran** in izberite **Besedilo/CSV** priključek.

1. Vnesite URL za ocene spletnega mesta https://aka.ms/ciadclasswebsite.

1. Med urejanjem podatkov izberite **Preobrazba** in potem **Prvo vrstico uporabite kot glave**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:
   - **ReviewRating**: celo število
   - **ReviewDate**: datum

1. V **Ime** polje v desnem podoknu preimenujte vir podatkov v **webReviews**.

## <a name="task-2---data-unification"></a>2. opravilo – poenotenje podatkov

Preglejte članek [o poenotenju podatkov](data-unification.md). Naslednje informacije predvidevajo, da poznate poenotenje podatkov na splošno.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Naloga 3 - Ustvarite dejavnost zgodovine transakcij

Preglejte članek [o dejavnostih strank](activities.md). Naslednje informacije predvidevajo, da ste seznanjeni z ustvarjanjem dejavnosti na splošno.

1. Ustvarite dejavnost, imenovano **Zgodovina naročnine** z *Naročnina* entiteta in njen primarni ključ, **Identifikacijska številka stranke**.

1. Ustvarite razmerje med *Zgodovina naročnine: Naročnina* in *eCommerceContacts:eCommerce* z **Identifikacijska številka stranke** kot tuji ključ za povezavo obeh entitet.

1. Izberite **SubscriptionType** za **EventActivity** in **Končni datum naročnine** za **Časovni žig**.

1. Izberite **Naročnina** za **Vrsta dejavnosti** in semantično preslika podatke o dejavnosti.

1. Izvedite dejavnost.

1. Dodajte drugo dejavnost in preslikajte imena njenih polj v ustrezna polja:
   - Entiteta dejavnosti stranke: Reviews:Website
   - Primarni ključ: Website.Reviews.ReviewId
   - Časovni žig: Website.Reviews.ReviewDate
   - Dogodek (ime dejavnosti): Website.Reviews.ActivityTypeDisplay
   - Podrobnosti (znesek ali vrednost): Website.Reviews.ReviewRating

1. Izvedite dejavnost.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>4. opravilo – konfiguracija predvidevanja izgube naročnin

Z vzpostavljenimi poenotenimi profili strank in ustvarjeno dejavnostjo zaženite odliv naročnin predvidevanje. Za podrobne korake glejte [Odliv naročnin predvidevanje](predict-subscription-churn.md).

1. Pojdi do **Inteligenca** > **Napovedi**.

1. Na **Ustvari** zavihek izberite **Uporabite model** na **Model odliva strank** ploščica.

1. Izberite **Naročnina** za vrsto odtoka in nato **Začeti**.

1. Poimenujte model **Predvidevanje izgube naročnine OOB** in izhodno entiteto **PredvidevanjeIzgubeNaročnineOOB**.

1. Določite nastavitve modela:
   - **Število dni od konca naročnine** :**60** dni, da se stranka šteje za odpuščeno, če ne obnovi naročnine v tem obdobju po koncu naročnine.
   - **Dnevi za raziskovanje prihodnosti za napovedovanje odliva** :**93** dni, kar je trajanje, za katerega model predvideva, katere stranke bi lahko odpadle. Bolj kot gledate v prihodnost, manj natančni so rezultati.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="Izberite nastavitve modela in definicijo odliva.":::

1. Izberite **Naprej**.

1. V **Zahtevani podatki** korak, izberite **Dodajte podatke** za zagotavljanje zgodovine naročnin.

1. Izberite **Naročnina** in entiteto SubscriptionHistory ter izberite **Naslednji**. Zahtevani podatki se samodejno izpolnijo iz aktivnosti. Izberite **Shrani**.

1. V razdelku Dejavnosti strank izberite **Dodajte podatke**.

1. Za ta primer dodajte dejavnost spletnega pregleda.

1. Izberite **Naprej**.

1. V **Posodobitve podatkov** korak, izberite **Mesečno** za modelni urnik.

1. Po pregledu vseh podrobnosti izberite **Shrani in zaženi**.

## <a name="task-5---review-model-results-and-explanations"></a>5. opravilo – preglejte rezultate modela in razlage

Model naj dokonča usposabljanje in ocenjevanje podatkov. Preglejte razlage modela odliva naročnine. Za več informacij glejte [Oglejte si predvidevanje rezultate](predict-subscription-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>6. opravilo – ustvarjanje segmenta strank z visokim tveganjem izgube

Z zagonom modela boste ustvarili novo entiteto, ki je navedena na zavihku **Podatki** > **Entitete**. Na podlagi entitete, ki jo je ustvaril model, lahko ustvarite nov segment.

1. Na strani z rezultati izberite **Ustvari segment**.

1. Ustvarite pravilo z uporabo **OOBSubscriptionChurnPrediction** entiteto in definirajte segment:
   - **Polje** : ChurnScore
   - **Operater** : večji kot
   - **Vrednost** : 0,6

1. Izberite **Shrani** in **Teči** segment.

Zdaj imate segment, ki se dinamično posodablja, v katerem so prepoznane stranke z visokim tveganjem izgube za to naročniško dejavnost. Za več informacij glejte [Ustvarjanje in upravljanje segmentov](segments.md).

> [!TIP]
> Ustvarite lahko tudi segment za model predvidevanje iz **Segmenti** stran z izbiro **Novo** in izbiranje **Ustvari iz** > **Inteligenca**. Za več informacij glejte [Ustvarite nov segment s hitrimi segmenti](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
