---
title: Delne podatke dopolnite s predvidevanji
description: Z predvidevanji izpolnite nepopolne podatke o strankah.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-predictions
- ci-custom-models
- customerInsights
ms.openlocfilehash: 7e93670007db27d13b84d7516f56830988da083e
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082522"
---
# <a name="complete-your-partial-data-with-predictions-deprecated"></a>Dopolnite svoje delne podatke s predvidevanji (opuščeno)

> [!IMPORTANT]
> Ta funkcija bo **zastarel** od **5. november 2021**. Trenutne izvedbe bodo še naprej delovale, dokler funkcija ne bo odstranjena, vendar ne boste mogli ustvariti novih integracij z uporabo spodnjih navodil.

Predvidevanja omogočajo preprosto ustvarjanje predvidenih vrednosti, ki okrepijo vaše razumevanje stranke. Na strani **Obveščanje** > **Predvidevanja** lahko izberete **Moja predvidevanja** in si ogledate predvidevanja, ki ste jih konfigurirali v drugih delih aplikacije Customer Insights, ter jih nadalje prilagodite.

> [!NOTE]
> Te funkcije ne morete uporabljati, če vaše okolje uporablja prostor za shranjevanje Azure Data Lake Gen 2.
>
> Funkcija predvidevanj uporablja avtomatizirana sredstva za ocenjevanje podatkov in pripravo predvidevanj na podlagi teh podatkov, torej ima zmogljivost za uporabo kot način profiliranja, kakor je izraz opredeljen v Splošni uredbi o varstvu podatkov (»GDPR«). Za strankino uporabo te funkcije za obdelavo podatkov lahko velja GDPR ali drugi zakoni ali predpisi. Sami ste odgovorni za to, da je vaša uporaba storitve Dynamics 365 Customer Insights, vključno s predvidevanji, v skladu z vsemi veljavnimi zakoni in predpisi, vključno z zakoni v zvezi z zasebnostjo, osebnimi podatki, biometričnimi podatki, varstvom podatkov in zaupnostjo komunikacij.

## <a name="prerequisites"></a>Zahteve

Preden lahko vaša organizacija uporablja funkcijo predvidevanj, morajo biti izpolnjeni naslednji predpogoji:

1. Vaša organizacija ima primerek, [nastavljen v Microsoft Dataverse](/ai-builder/build-model#prerequisites), ki je v isti organizaciji kot Customer Insights.

2. Vaše okolje Customer Insights je pripeto v vaš primerek Dataverse.

Za več informacij glejte [Ustvarjanje novega okolja](create-environment.md).

## <a name="create-a-prediction-in-the-customer-entity"></a>Ustvarjanje predvidevanja v entiteti stranke

1. Pojdi do **Podatki** > **Entitete**.

2. Izberite entiteto **Stranka**.

3. V entiteti **Customer: CustomerInsights** izberite zavihek **Polja**.

4. Poiščite ima atributa, za katerega želite napovedati vrednosti, nato izberite ikono **Pregled** v stolpcu **Povzetek**.
   > [!div class="mx-imgBorder"]
   > ![Ikona pregleda.](media/intelligence-overviewicon.png "Ikona pregleda")

5. V primeru visoke stopnje manjkajočih vrednosti za atribut izberite **Predvidi manjkajoče vrednosti** za nadaljevanje s predvidevanjem.
   > [!div class="mx-imgBorder"]
   > ![Stanje pregleda s prikazanim gumbom za predvidevanje manjkajočih vrednosti.](media/intelligence-overviewpredictmissingvalues.png "Stanje pregleda s prikazanim gumbom za predvidevanje manjkajočih vrednosti")

6. Zagotovite **Prikazno ime** in **Ime izhodne entitete** za rezultate predvidevanja.

7. Prikazal se bo vnaprej izpolnjen seznam možnosti, kjer lahko preslikate vrednosti v predvideno kategorijo. V tem primeru sta edini možnosti kategorije 0 ali 1, saj preslikava poteka na true/false ali binarno naravo predvidevanja. V stolpcu kategorije preslikajte vrednosti polj, za katera želite, da so razvrščena kot »0«, v končno predvidevanje na »0« in elemente, za katere želite, da so razvrščeni kot »1«, v končno predvidevanje na »1«.
   > [!div class="mx-imgBorder"]
   > ![Primer, ki prikazuje preslikane vrednosti polj v kategorije.](media/intelligence-categorymapping.png "Primer, ki prikazuje preslikane vrednosti polj v kategorije")

8. Izberite **Dokončano** in predvidevanje bo obdelano. Obdelava traja nekaj časa, odvisno od velikosti in zapletenosti podatkov. Rezultati bodo na voljo v novi entiteti, ki temelji na možnosti **Ime izhodne entitete**, predvidevanja, ki ste ga ustvarili.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="create-a-prediction-while-creating-a-segment"></a>Ustvarjanje predvidevanja med ustvarjanjem segmenta

Predvidevanje manjkajočih vrednosti za določene atribute po izbiri je mogoče tudi pri ustvarjanju segmenta. Natančneje, ko hitro ustvarite segment na podlagi bodisi poenotene entitete stranke ali entitete Customer_Measure.

Kot del tega poteka izberete določen atribut, na katerem utemeljite segment, kot je zadovoljstvo strank ali znesek nakupa. Ob ustvarjanju segmenta bo sistem predlagal način predvidevanja za vse manjkajoče vrednosti za ta atribut.

1. Pojdi do **segmenti** in izberite **Profili** ploščice.

2. Izberite **Polje**, v katerem ustvarite segment, in izberite **Operator**, nato izberite **Pregled**.

3. Navedite **Ime** in **Prikazno ime** za segment.

4. Izberite **Shrani**.

5. Če ima segment, ki ste ga ustvarili, manjkajoče podatke v izvornem polju, lahko izberete predvidevanje manjkajočih vrednosti.
   > [!div class="mx-imgBorder"]
   > ![Gumb za predvidevanje.](media/segments-predictoption.png "Gumb za predvidevanje")

6. Zagotovite **Prikazno ime** in **Ime izhodne entitete** za rezultate predvidevanja.

7. Izberite **Dokončano**. Vaše predvidevanje bo kmalu ustvarjeno v novi entiteti z imenom, ki ste ga navedli za **Ime izhodne entitete**.

## <a name="view-a-prediction"></a>Ogled predvidevanja

1. Pojdi do **Inteligenca** > **Napovedi** > **Moje napovedi**.

2. Izberite predvidevanje, ki ga želite pregledati.

3. Izberite navpično elipso (&vellip;) v **Dejanja** stolpec in izberite **Ogled**.

4. Videli boste število podatkovnih točk v pogledu predvidevanja.
   > [!div class="mx-imgBorder"]
   > ![Stran predvidevanj.](media/intelligence-predictionsviewpage.png "Stran predvidevanj")

   - **Predvidene vrednosti** prikazuje preslikavo, ustvarjeno med fazo preslikave vrednosti polja v kategorijo. To so vrednosti v naboru podatkov, ki so bile preslikane v določeno kategorijo.
   -**Ključni dejavniki** so dejavniki v naboru podatkov, ki bodo najverjetneje vplivali na zanesljivost predvidevanja za vrednost polja, ki se preslika v določeno kategorijo.
   - **Uspešnost** označuje, kako potekajo predvidevanja. Za več informacij izberite povezavo.
   - **Predogled** prikazuje vzorce izhodnega nabora podatkov iz predvidevanj in verjetnost ali zanesljivost predvidene vrednosti, kjer je 0 negotovo in 1 je gotovo.

## <a name="update-a-prediction"></a>Posodobitev predvidevanja

1. Pojdi do **Inteligenca** > **Napovedi** > **Moje napovedi**.

2. Izberite predvidevanje, ki ga želite posodobiti in izberite ikono **Posodobi**.

3. Predvidevanje bo razporejeno za obdelavo. Čas zadnje posodobitve lahko vidite v stolpcu **Posodobljeno** na strani **Predvidevanja**.

## <a name="edit-a-prediction"></a>Urejanje predvidevanja

Ko ustvarite predvidevanje, lahko prilagodite model v AI Builder povečati učinkovitost vašega modela.  

1. Pojdi do **Inteligenca** > **Napovedi** > **Moje napovedi**.

2. Izberite predvidevanje, ki ga želite urediti.

3. Izberite navpično elipso (&vellip;) v **Dejanja** stolpec in izberite **Ogled**.

4. Izberite **Prilagodite se AI Builder**.

5. Posodobite svoj model v AI Builder. [Preberite več o upravljanju modelov v orodju AI Builder](/ai-builder/manage-model#retrain-and-republish-existing-models).

Ob naslednjem zagonu predvidevanja bo uporabljen ustvarjeni posodobljeni model.

> [!NOTE]
> Novi modeli, ustvarjeni v AI Builder ne bo prikazan v Customer Insights, razen če je bil model ustvarjen iz zgoraj navedenih izkušenj.

## <a name="remove-a-prediction"></a>Odstranjevanje predvidevanja

1. Pojdi do **Inteligenca** > **Napovedi** > **Moje napovedi**.

2. Izberite predvidevanje, ki ga želite izbrisati.

3. Izberite navpično elipso (&vellip;) v **Dejanja** stolpec in izberite **Izbriši**.

4. Potrdite brisanje.

## <a name="troubleshooting"></a>Odpravljanje težav

Če zaradi napake ne morete dokončati priloženega postopka Dataverse, lahko poskusite postopek dokončati ročno. V postopku prilaganja lahko pride do dveh znanih težav:

- Rešitev dodatka za kartice stranke ni nameščena.
    1. Opravite korake iz navodil za [namestitev in konfiguracijo rešitve](customer-card-add-in.md).

- Dovoljenja za aplikacije niso podeljena.
    1. Obiščite spletno mesto [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. Izberite **Okolja**.
    1. Izberite navpično elipso (&vellip;) poleg okolja, v katerega želite dodati dovoljenje, in izberite **Nastavitve**.
    1. Razširite možnost **Uporabniki in dovoljenja** ter izberite možnost **Uporabniki**.
    1. Izberite možnost **+ Novo** in nato **Uporabnik**.
    1. Če možnost **Uporabnik aplikacije** še ni izbrana, jo izberite in vnesite naslednje podatke:
        - **Uporabniško ime:** cihelp@microsoft.com
        - **ID aplikacije:** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **Ime:** stranka
        - **Priimek:** Insights
        - **Primarni e-poštni naslov:** cihelp@microsoft.com
    1. Izberite **Shrani in zapri**.
    1. Izberite uporabnika, ki ste ga pravkar ustvarili.
    1. V zgornji vrstici menija izberite **Upravljanje vlog**.
    1. Izberite **Skrbnik sistema**, nato pa **V redu**.


[!INCLUDE [footer-include](includes/footer-banner.md)]
