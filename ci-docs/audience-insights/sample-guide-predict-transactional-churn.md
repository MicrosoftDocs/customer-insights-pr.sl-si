---
title: Vzorčni vodnik za predvidevanje izgube glede transakcij
description: S tem vzorčnim vodnikom preizkusite vnaprej pripravljeni model za predvidevanje izgube glede transakcij.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 93841358d110bd16c7b7f8beb079bed704b22260
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354621"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Vzorčni vodnik za predvidevanje izgube glede transakcij

S spodnjimi podatki vam bomo v tem vodniku razložili celovit primer predvidevanja izgube glede transakcij v storitvi Customer Insights. Vsi podatki, uporabljeni v tem priročniku, niso resnični podatki o strankah in so del nabora podatkov Contoso, ki ga najdemo v *predstavitvenem* okolju v okviru naročnine Customer Insights.

## <a name="scenario"></a>Scenarij

Contoso je podjetje, ki proizvaja visokokakovostno kavo in kavne avtomate, ki jih prodaja prek njihovega spletnega mesta Contoso Coffee. Njihov cilj je vedeti, katere stranke, ki običajno redno kupujejo njihove izdelke, ne bodo več aktivne stranke v naslednjih 60 dneh. Znanje o tem, katere stranke se bodo **verjetno izgubile**, jim lahko pomaga, da bolje izkoristijo tržna prizadevanja tako, da se osredotočijo na njihovo ohranitev.

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

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Spremeni datum rojstva v datum.":::

1. V polju **Ime** v desnem podoknu preimenujte vir podatkov iz **Poizvedba** v **StikiEPoslovanja**

1. Shranite vir podatkov.

### <a name="ingest-online-purchase-data"></a>Vnos podatkov o spletnem nakupu

1. Dodajte še nabor podatkov z istega vira podatkov **EPoslovanje**. Znova izberite povezovalnik **Besedilo/CSV**.

1. Vnesite URL za podatke **Spletni nakupi** https://aka.ms/ciadclassonline.

1. Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:

   - **PurchasedOn**: datum/čas
   - **TotalPrice**: valuta
   
1. V desnem podoknu v polju **Ime** preimenujte svoj vir podatkov iz **Poizvedba** v **NakupiEPoslovanja**.

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


## <a name="task-2---data-unification"></a>2. opravilo – poenotenje podatkov

Po vnosu podatkov začnemo s postopkom **Preslikava/ujemanje/spajanje** za izdelavo poenotenega profila stranke. Če želite več informacij, glejte [Poenotenje podatkov](data-unification.md).

### <a name="map"></a>Preslikava

1. Po vnosu podatkov preslikajte stike iz podatkov o elektronskem poslovanju in zvestobi v običajne vrste podatkov. Izberite **Podatki** > **Poenotenje** > **Preslikava**.

1. Izberite entitete, ki predstavljajo profil stranke – **StikiEPoslovanja** in **zvesteStranke**. 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="Poenotenje virov podatkov o elektronskem poslovanju in zvestobi.":::

1. Izberite **IDstika** kot primarni ključ za **StikiEPoslovanja** in **ID zvestobe** kot primarni ključ za **zvesteStranke**.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Poenotite IDzvestobe kot primarni ključ.":::

### <a name="match"></a>Povezovanje

1. Izberite zavihek **Ujemanje** in izberite **Nastavi vrstni red**.

1. Na spustnem seznamu izberite možnost **Primarni** ter za primarni vir določite **eCommerceContacts: eCommerce** in vključite vse zapise.

1. Na spustnem seznamu izberite možnost **Entiteta 2**, nato pa **loyCustomers: LoyaltyScheme** in vključite vse zapise.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Poenotenje ujemanja elektronskega poslovanja in zvestobe.":::

1. Izberite **Ustvarjanje novega pravila**.

1. Dodajte svoj prvi pogoj z možnostjo FullName.

   * Za entiteto StikiEPoslovanja na spustnem seznamu izberite **FullName**.
   * Za entiteto zvesteStranke na spustnem seznamu izberite **FullName**.
   * Izberite spustni meni **Normaliziraj** in izberite **Vrsta (telefon, ime, naslov, ...)**.
   * Nastavite **Raven natančnosti**: **Osnovno** in **Vrednost**: **Visoko**.

1. Vnesite ime **FullName, Email** za novo pravilo.

   * Dodajte drugi pogoj za e-poštni naslov tako, da izberete **Dodaj pogoj**.
   * Za entiteto StikiEPoslovanja na spustnem seznamu izberite možnost **E-pošta**.
   * Za entiteto zvesteStranke na spustnem seznamu izberite možnost **E-pošta**. 
   * Pustite polje Normaliziraj prazno. 
   * Nastavite **Raven natančnosti**: **Osnovno** in **Vrednost**: **Visoko**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Poenotenje pravila ujemanja za ime in e-pošto.":::

7. Izberite **Shrani** in **Zaženi**.

### <a name="merge"></a>Spajanje

1. Odprite zavihek **Spajanje**.

1. Pri **IDstranke** za entiteto **zvesteStranke** spremenite prikazno ime v **ZVESTOBAIDstranke**, da se razlikuje od ostalih vnesenih ID-jev.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Preimenujte ID stika iz ID-ja zvestobe.":::

1. Izberite **Shrani** in **Zaženi**, da začnete postopek spajanja.



## <a name="task-3---configure-transaction-churn-prediction"></a>3. opravilo – konfiguracija predvidevanja izgube glede transakcij

Z vzpostavljenimi poenotenimi profili strank lahko zdaj zaženemo predvidevanje izgube naročnin. Za podrobne korake glejte [Odliv naročnin predvidevanje](predict-subscription-churn.md) Članek. 

1. Odprite **Obveščanje** > **Odkrivanje** in izberite uporabo možnosti **Model izgube strank**.

1. Izberite možnost **Transakcijsko** in izberite **Začetek**.

1. Poimenujte model **Predvidevanje izgube glede transakcij elektronskega poslovanja OOB** in izhodno entiteto **PredvidevanjeIzgubeElektronskegaPoslovanjaOOB**.

1. Določite dva pogoja za model izgube:

   * **Okno za predvidevanja**: **vsaj 60** dni. Ta nastavitev določa, kako daleč v prihodnost želimo predvideti izgubo stranke.

   * **Opredelitev izgube**: **vsaj 60** dni. Trajanje brez nakupa, po katerem se šteje, da je stranka izgubljena.

     :::image type="content" source="media/model-levers.PNG" alt-text="Izberite časovno obdobje za predvidevanje modela in opredelitev izgube.":::

1. Za zgodovino nakupov izberite **Zgodovina nakupov (priporočeno)** in nato **Dodajanje podatkov**.

1. Dodajte entiteto **NakupiEPoslovanja: EPoslovanje** in preslikajte polja iz elektronskega poslovanja v ustrezna polja, ki jih zahteva model.

1. Pridružite entiteto **NakupiEPoslovanja: EPoslovanje** z entiteto **StikiEPoslovanja: EPoslovanje**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Pridružite se entitetam elektronskega poslovanja.":::

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
