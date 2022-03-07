---
title: Vzorčni vodnik za predvidevanje priporočil za izdelke
description: Uporabite ta vzorčni vodnik, da preskusite model predvidevanja priporočil za vnaprej pripravljene izdelke.
ms.date: 02/10/2021
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
ms.openlocfilehash: 8ba54cfd466049c8df99c15f34626ab1914234f1
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354667"
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

1. Vnesite URL za stike za elektronsko poslovanje https://aka.ms/ciadclasscontacts.

1. Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:
   - **DateOfBirth**: datum
   - **CreatedOn**: datum/čas/časovni pas

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pretvorite datum rojstva v datum.":::

5. V polju »Ime« v desnem podoknu preimenujte vir podatkov iz **Poizvedba** v **StikiEPoslovanja**.

6. **Shranite** vir podatkov.

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

## <a name="task-2---data-unification"></a>2. opravilo – poenotenje podatkov

Po uvozu podatkov se začne postopek poenotenja podatkov za ustvarjanje enotnega profila stranke. Če želite več informacij, glejte [Poenotenje podatkov](data-unification.md).

### <a name="map"></a>Preslikava

1. Po vnosu podatkov preslikajte stike iz podatkov o elektronskem poslovanju in zvestobi v običajne vrste podatkov. Izberite **Podatki** > **Poenotenje** > **Preslikava**.

2. Izberite entitete, ki predstavljajo profil stranke – **StikiEPoslovanja** in **zvesteStranke**.

   ![Poenotenje virov podatkov o elektronskem poslovanju in zvestobi.](media/unify-ecommerce-loyalty.png)

3. Izberite **IDstika** kot primarni ključ za **StikiEPoslovanja** in **ID zvestobe** kot primarni ključ za **zvesteStranke**.

   ![Poenotite IDzvestobe kot primarni ključ.](media/unify-loyaltyid.png)

### <a name="match"></a>Povezovanje

1. Izberite zavihek **Ujemanje** in izberite **Nastavi vrstni red**.

2. Na spustnem seznamu izberite možnost **Primarni** ter za primarni vir določite **eCommerceContacts: eCommerce** in vključite vse zapise.

3. Na spustnem seznamu izberite možnost **Entiteta 2**, nato pa **loyCustomers: LoyaltyScheme** in vključite vse zapise.

   ![Poenotenje ujemanja elektronskega poslovanja in zvestobe.](media/unify-match-order.png)

4. Izberite **Ustvarjanje novega pravila**.

5. Dodajte svoj prvi pogoj z možnostjo FullName.

   - Za entiteto StikiEPoslovanja na spustnem seznamu izberite **FullName**.
   - Za entiteto zvesteStranke na spustnem seznamu izberite **FullName**.
   - Izberite spustni meni **Normaliziraj** in izberite **Vrsta (telefon, ime, naslov, ...)**.
   - Nastavite **Raven natančnosti**: **Osnovno** in **Vrednost**: **Visoko**.

6. Vnesite ime **FullName, Email** za novo pravilo.

   - Dodajte drugi pogoj za e-poštni naslov tako, da izberete **Dodaj pogoj**.
   - Za entiteto StikiEPoslovanja na spustnem seznamu izberite možnost **E-pošta**.
   - Za entiteto zvesteStranke na spustnem seznamu izberite možnost **E-pošta**.
   - Pustite polje Normaliziraj prazno.
   - Nastavite **Raven natančnosti**: **Osnovno** in **Vrednost**: **Visoko**.

   ![Poenotenje pravila ujemanja za ime in e-pošto.](media/unify-match-rule.png)

7. Izberite **Shrani** in **Zaženi**.

### <a name="merge"></a>Spajanje

1. Odprite zavihek **Spajanje**.

1. Pri **IDstranke** za entiteto **zvesteStranke** spremenite prikazno ime v **ZVESTOBAIDstranke**, da se razlikuje od ostalih vnesenih ID-jev.

   ![Preimenujte ID stika iz ID-ja zvestobe.](media/unify-merge-contactid.png)

1. Izberite **Shrani** in **Zaženi**, da začnete postopek spajanja.

## <a name="task-3---configure-product-recommendation-prediction"></a>3. opravilo – konfiguracija predvidevanja priporočil za izdelke

Z vzpostavljenimi poenotenimi profili strank lahko zdaj zaženemo predvidevanje izgube naročnin.

1. V razdelku **Obveščanje** > **Predvidevanje** izberite **Priporočilo za izdelke**.

1. Izberite **Začetek**.

1. Poimenujte model **Model predvidevanja priporočil za vnaprej pripravljene izdelke** in izhodno entiteto **ModelPredvidevanjaPriporočilZaVnaprejPripravljeneIzdelke**.

1. Določite tri pogoje za model:

   - **Število izdelkov**: nastavite to vrednost na **5**. Ta nastavitev določi, koliko izdelkov želite priporočiti svojim strankam.

   - **Pričakovani ponovljeni nakupi**: izberite **Da**, če želite izdelke vključiti v priporočilo izdelkov, ki so jih vaše stranke že kupile.

   - **Obdobje zajema podatkov:** izberite vsaj **365 dni**. Ta nastavitev določa obdobje zajema podatkov strankine dejavnosti, ki ga bo model upošteval pri vnosu priporočil.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Oblikujte nastavitve za model s priporočili za izdelke.":::

1. Za zgodovino nakupov izberite **Zahtevani podatki** in nato **Dodajanje podatkov**.

1. Dodajte entiteto **NakupiEPoslovanja: EPoslovanje** in preslikajte polja iz elektronskega poslovanja v ustrezna polja, ki jih zahteva model.

1. Pridružite entiteto **NakupiEPoslovanja: EPoslovanje** z entiteto **StikiEPoslovanja: EPoslovanje**.

   ![Pridružite se entitetam elektronskega poslovanja.](media/model-purchase-join.png)

1. Izberite **Naprej** za nastavitev urnika modela.

   Model se mora redno usposabljati, da se nauči novih vzorcev, ko vnese nove podatke. V tem primeru izberite **Mesečno**.

1. Po pregledu vseh podrobnosti izberite **Shrani in zaženi**.


## <a name="task-4---review-model-results-and-explanations"></a>4. opravilo – preglejte rezultate modela in razlage

Model naj dokonča usposabljanje in ocenjevanje podatkov. Zdaj lahko pregledate pojasnila modela s priporočili za izdelke. Za več informacij glejte [Pregled stanja in rezultatov predvidevanja](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>5. opravilo – ustvarjanje segmenta najbolj prodajanih izdelkov

Z zagonom produkcijskega modela ustvarite novo entiteto, ki jo lahko vidite v razdelku **Podatki** > **Entitete**.

Na podlagi entitete, ki jo je ustvaril model, lahko ustvarite nov segment.

1. Izberite **Segmenti**. Izberite **Novo** in izberite **Ustvari iz** > **Obveščanje**.

   ![Ustvarjanje segmenta z izhodnimi podatki modela.](media/segment-intelligence.png)

1. Izberite končno točko **ModelPredvidevanjaPriporočilZaVnaprejPripravljeneIzdelke** in določite segment:

   - Polje: IDIzdelka
   - Operator: vrednost
   - Vrednost: izberite najboljše tri ID-je izdelka

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Ustvarite segment iz rezultatov modela.":::

Sedaj imate dinamično posodobljen segment, ki prepozna stranke, ki so bolj pripravljene kupiti tri najbolj priporočene izdelke. 

Za več informacij glejte [Ustvarjanje in upravljanje segmentov](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
