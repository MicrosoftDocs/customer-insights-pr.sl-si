---
title: Predvidi odliv naročnin (vsebuje video)
description: Predvidite, ali za stranko obstaja tveganje, da ne bo več uporabljala izdelkov ali storitev naročnine vašega podjetja.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 7464707864c418bfcc625ddfd245622131434b33
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610256"
---
# <a name="predict-subscription-churn"></a>Predvidevanje izgube naročnine

Predvidite, ali za stranko obstaja tveganje, da ne bo več uporabljala izdelkov ali storitev naročnine vašega podjetja. Podatki o naročninah vključujejo aktivne in neaktivne naročnine za vsako stranko, tako da obstaja več vnosov na ID stranke.

Imeti morate poslovno znanje, da razumete, kaj odliv pomeni za vaše podjetje. Podpiramo definicije opuščanja na podlagi časa, kar pomeni, da se šteje, da je stranka opustila nekaj časa po koncu naročnine.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Preizkusite odliv naročnin predvidevanje z uporabo vzorčnih podatkov: [Odliv naročnin predvidevanje vzorčni vodnik](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Zahteve

- Vsaj [dovoljenja sodelujočega](permissions.md).
- Vsaj 10 profilov strank, po možnosti več kot 1000 edinstvenih strank.
- Identifikator stranke, enolični identifikator za povezovanje naročnin z vašimi strankami.
- Naročniški podatki za najmanj dvojno izbrano časovno okno. Po možnosti dve do tri leta naročniških podatkov. Zgodovina naročnin mora vsebovati:
  - **ID naročnine:** Enolični identifikator naročnine.
  - **Končni datum naročnine:** Datum, ko stranki poteče naročnina.
  - **Datum začetka naročnine:** Datum začetka naročnine za stranko.
  - **Datum transakcije:** Datum spremembe naročnine. Primer: stranka kupi ali prekliče naročnino.
  - **Ali gre za ponavljajočo se naročnino:** Logično polje true/false, ki določa, ali se bo naročnina obnovila z istim ID-jem naročnine brez posredovanja stranke.
  - **Pogostost ponovitev (v mesecih):** Za ponavljajoče se naročnine mesec, v katerem se bo naročnina obnovila. Primer: letna naročnina, ki se za stranko vsako leto samodejno podaljša za dodatno leto, ima vrednost 12.
  - **Znesek naročnine** : Znesek valute, ki ga stranka plača za podaljšanje naročnine. Pomaga lahko prepoznati vzorce za različne ravni naročnin.
- Vsaj dva zapisa dejavnosti za 50 % strank, za katere želite izračunati odliv. Dejavnosti stranke morajo vključevati:
  - **Primarni ključ:** Enolični identifikator za dejavnost. Primer: obisk spletnega mesta ali zapis o uporabi, ki prikazuje, da si je stranka ogledala epizodo TV-oddaje.
  - **Časovni žig:** Datum in čas dogodka, določen s primarnim ključem.
  - **dogodek:** Ime dogodka, ki ga želite uporabiti. Primer: polje, imenovano »UserAction«, v storitvi pretakanja videov ima lahko vrednost »Ogledano«.
  - **Podrobnosti:** podrobni podatki o dogodku. Primer: polje, imenovano »ShowTitle«, v storitvi pretakanja videov ima lahko vrednost videoposnetka, ki si ga je stranka ogledala.
- Manj kot 20 % manjkajočih vrednosti v podatkovnem polju posredovane entitete.

## <a name="create-a-subscription-churn-prediction"></a>Ustvarjanje predvidevanja izgube naročnine

Izberite **Shrani osnutek** kadar koli shranite predvidevanje kot osnutek. Osnutek predvidevanje se prikaže v **Moje napovedi** zavihek.

1. Pojdi do **Inteligenca** > **Napovedi**.

1. Na **Ustvari** zavihek izberite **Uporabite model** na **Model odliva strank** ploščica.

1. Izberite **Naročnina** za vrsto odtoka in nato **Začeti**.

1. **Poimenujte ta model** in **izhodno ime entitete**, da jih ločite od drugih modelov ali entitet.

1. Izberite **Naprej**.

### <a name="define-customer-churn"></a>Določitev izgube stranke

1. Vnesite število za možnost **Dnevi od konca naročnine**, da lahko vaše podjetje šteje, da je stranka v stanju izgube. To obdobje je običajno povezano s poslovnimi dejavnostmi, kot so ponudbe ali druga tržna prizadevanja, ki poskušajo preprečiti izgubo stranke.

1. Vnesite številko **Dnevi za raziskovanje prihodnosti za napovedovanje odliva**. Na primer, v naslednjih 90 dneh predvidite tveganje za izgubo strank, da temu prilagodite vaša prizadevanja za uspešno trženje. Napovedovanje tveganja izgube za daljša ali krajša obdobja lahko oteži obravnavo dejavnikov v vašem profilu tveganja izgube, odvisno od vaših poslovnih potreb.

1. Izberite **Naprej**.

### <a name="add-required-data"></a>Dodajanje zahtevanih podatkov

1. Izberite **Dodajte podatke** za **Zgodovina naročnin**.

1. Izberite vrsto semantične dejavnosti **Naročnina** ki vsebuje potrebne podatke o zgodovini naročnin. Če dejavnost ni nastavljena, izberite **tukaj** in ga ustvarite.

1. Spodaj **dejavnosti**, če so bili atributi dejavnosti semantično preslikani, ko je bila dejavnost ustvarjena, izberite določene atribute ali entiteto, na katero želite, da se osredotoči izračun. Če do semantične preslikave ni prišlo, izberite **Uredi** in preslikajte svoje podatke.
  
   :::image type="content" source="media/subscription-churn-required.png" alt-text="Dodajte zahtevane podatke za model opuščanja naročnine":::

1. Izberite **Naslednji** in preglejte atribute, potrebne za ta model.

1. Izberite **Shrani**.

1. Izberite **Dodajte podatke** za **Aktivnosti strank**.

1. Izberite semantično vrsto dejavnosti, ki zagotavlja informacije o dejavnosti stranke. Če dejavnost ni nastavljena, izberite **tukaj** in ga ustvarite.

1. Spodaj **dejavnosti**, če so bili atributi dejavnosti semantično preslikani, ko je bila dejavnost ustvarjena, izberite določene atribute ali entiteto, na katero želite, da se osredotoči izračun. Če do semantične preslikave ni prišlo, izberite **Uredi** in preslikajte svoje podatke.

1. Izberite **Naslednji** in preglejte atribute, potrebne za ta model.

1. Izberite **Shrani**.

1. Dodajte več dejavnosti ali izberite **Naslednji**.

### <a name="set-update-schedule"></a>Nastavitev urnika posodobitev

1. Izberite pogostost za ponovno usposabljanje vašega modela. Ta nastavitev je pomembna za posodobitev točnosti napovedi, ko se v Customer Insights vnesejo novi podatki. Večina podjetij se lahko prekvalificira enkrat na mesec in pridobi dobro natančnost svojih predvidevanj.

1. Izberite **Naprej**.

### <a name="review-and-run-the-model-configuration"></a>Pregled in zagon konfiguracije modela

The **Pregled in zagon** korak prikazuje povzetek konfiguracije in nudi možnost spreminjanja, preden ustvarite predvidevanje.

1. Izberite **Uredi** na katerem koli od korakov za pregled in morebitne spremembe.

1. Če ste zadovoljni s svojo izbiro, izberite **Shrani in zaženi** da začnete izvajati model. Izberite **Dokončano**. The **Moje napovedi** zavihek se prikaže med ustvarjanjem predvidevanje. Postopek lahko traja več ur, odvisno od količine podatkov, uporabljenih v predvidevanju.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Oglejte si predvidevanje rezultate

1. Pojdi do **Inteligenca** > **Napovedi**.

1. V **Moje napovedi** izberite predvidevanje, ki si ga želite ogledati.

Na strani z rezultati so trije primarni razdelki podatkov:

- **Učinkovitost modela usposabljanja** : Ocene A, B ali C označujejo uspešnost predvidevanje in vam lahko pomagajo pri odločitvi za uporabo rezultatov, shranjenih v izhodni entiteti.
  
  :::image type="content" source="media/subscription-churn-modelperformance.PNG" alt-text="Slika polja s podatki o oceni modela z oceno A":::

  Ocene so določene na podlagi naslednjih pravil:
  - **A** ko je model natančno predvidel vsaj 50 % vseh napovedi in ko je odstotek točnih napovedi za stranke, ki so odpadle, večji od zgodovinske povprečne stopnje odliva za vsaj 10 %.
  - **B** ko je model natančno predvidel vsaj 50 % skupnih napovedi in ko je odstotek točnih napovedi za stranke, ki so odpadle, do 10 % večji od zgodovinske povprečne stopnje odpovedi.
  - **C** ko je model natančno predvidel manj kot 50 % skupnih napovedi ali ko je odstotek točnih napovedi za stranke, ki so odpadle, manjši od zgodovinske povprečne stopnje odliva.
  
- **Verjetnost izgube (število strank)**: skupine strank na podlagi predvidenega tveganja za izgubo. Po želji, [ustvarite segmente strank](prediction-based-segment.md) z velikim tveganjem odliva. Takšni segmenti vam pomagajo razumeti, kako mora biti nastavljena vaša prekinitev za članstvo v segmentu.  

  :::image type="content" source="media/subscription-churn-resultdistribution.PNG" alt-text="Graf, ki prikazuje porazdelitev rezultatov izgube, razdeljen na obsege od 0 % do 100 %":::

- **Najvplivnejši dejavniki:** ob ustvarjanju predvidevanja se upošteva veliko dejavnikov. Vsak od dejavnikov ima svoj pomen, izračunan za združena predvidevanja, ki jih ustvari model. Uporabite te dejavnike za pomoč pri potrditvi rezultatov predvidevanje. Ali pa te informacije uporabite pozneje za [ustvarjanje segmentov](.//prediction-based-segment.md) ki bi lahko pomagali vplivati na tveganje odliva strank.

  :::image type="content" source="media/subscription-churn-influentialfactors.PNG" alt-text="Seznam, ki prikazuje vplivne dejavnike in njihov pomen za napovedovanje rezultata izgube.":::

> [!NOTE]
> V izhodni entiteti za ta model *ChurnScore* je predvidena verjetnost odliva in *IsChurn* je binarna oznaka, ki temelji na *ChurnScore* s pragom 0,5. Če ta privzeti prag ne deluje za vaš scenarij, [ustvarite nov segment](segments.md) z vašim želenim pragom. Če si želite ogledati rezultat odliva, pojdite na **podatki** > **Entitete** in si oglejte podatkovni zavihek za izhodno entiteto, ki ste jo definirali za ta model.

[!INCLUDE [footer-include](includes/footer-banner.md)]
