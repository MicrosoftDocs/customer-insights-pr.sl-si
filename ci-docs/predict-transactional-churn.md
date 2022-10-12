---
title: Odliv transakcij predvidevanje (vsebuje video)
description: Predvidite, ali za stranko obstaja tveganje, da ne bo več kupovala izdelkov ali storitev vašega podjetja.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: fd8df0f0a168ddfab9e8ad3af9e1f1fc0bc1b7a2
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610532"
---
# <a name="predict-transaction-churn"></a>Predvidevanje izgube transakcij

Predvidevanje izgub glede transakcij pomaga predvideti, ali stranka v določenem časovnem obdobju ne bo več kupovala vaših izdelkov ali storitev.

Imeti morate poslovno znanje, da razumete, kaj odliv pomeni za vaše podjetje. Podpiramo časovne opredelitve izgub, kar pomeni, da se za izgubo stranke šteje, če določeno obdobje ni opravila nakupov.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Za okolja, ki temeljijo na poslovnih računih, lahko predvidimo izgubo transakcij za račun in tudi kombinacijo računa in druge ravni informacij, kot je kategorija izdelkov. Na primer, dodajanje razsežnosti lahko pomaga določiti, kako verjetno je, da bo račun "Contoso" prenehal kupovati kategorijo izdelkov "pisarniški material". Poleg tega lahko za poslovne račune uporabimo tudi umetno inteligenco za ustvarjanje seznama možnih vzrokov, zakaj se bo račun verjetno izgubil za kategorijo podatkov sekundarne ravni.

> [!TIP]
> Preizkusite odliv transakcij predvidevanje z uporabo vzorčnih podatkov: [Odliv transakcij predvidevanje vzorčni vodnik](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Zahteve

- Vsaj [dovoljenja sodelujočega](permissions.md).
- Vsaj 10 profilov strank, po možnosti več kot 1000 edinstvenih strank.
- Identifikator stranke, edinstven identifikator za povezovanje transakcij z vašimi strankami.
- Podatki o transakcijah za vsaj dvojno izbrano časovno okno, na primer dve do tri leta zgodovine transakcij. Idealno vsaj dve transakciji na stranko. Zgodovina transakcij mora vsebovati:
  - **Številka transakcije** : Enolični identifikator nakupa ali transakcije.
  - **Datum transakcije** : Datum nakupa ali transakcije.
  - **Vrednost transakcije** : Valuta ali znesek številčne vrednosti transakcije.
  - **Edinstven ID izdelka** : ID kupljenega izdelka ali storitve, če so vaši podatki na ravni vrstične postavke.
  - **Ali je bila ta transakcija vračilo** : True/false polje, ki identificira, ali je bila transakcija vračilo ali ne. Če je **Vrednost transakcije** je negativen, sklepamo na donos.
- Podatki o dejavnosti stranke:
  - Identifikator stranke, edinstven identifikator za preslikavo dejavnosti vaših strank.
  - **Primarni ključ:** Enolični identifikator za dejavnost. Na primer, obisk spletnega mesta ali zapis uporabe, ki prikazuje, da je stranka preizkusila vzorec vašega izdelka.
  - **Časovni žig:** Datum in čas dogodka, določen s primarnim ključem.
  - **dogodek:** Ime dogodka, ki ga želite uporabiti. Na primer, polje z imenom »UserAction« v trgovini z živili je lahko kupon, ki ga kupec uporabi.
  - **Podrobnosti:** podrobni podatki o dogodku. Na primer, polje z imenom »CouponValue« v trgovini z živili je lahko vrednost valute kupona.
- Manj kot 20 % manjkajočih vrednosti v podatkovnem polju navedenega subjekta

Za poslovne račune (B-to-B) dodajte podatke o strankah, poravnane proti bolj statičnim atributom, da zagotovite najboljše delovanje modela:
- **Identifikacijska številka stranke:** Enolični identifikator za stranko.
- **Datum ustvarjanja:** Datum, ko je bila stranka prvotno dodana.
- **Država ali provinca:** Država ali provinca, kjer je stranka.
- **Država:** Država kupca.
- **Industrija:** Panožni tip stranke. Na primer, polje, imenovano »Industrija« v pražilniku kave, lahko označuje, ali je bila stranka trgovina na drobno.
- **Razvrstitev:** Kategorizacija stranke za vaše podjetje. Na primer, polje, imenovano »ValueSegment« v pražilniku kave, je lahko raven stranke glede na velikost stranke.

> [!NOTE]
> Za podjetja z visoko pogostnostjo nakupov strank (vsakih nekaj tednov) je priporočljivo izbrati krajši časovni okvir predvidevanja in definicijo izgube. Za nizko pogostnost nakupov (vsakih nekaj mesecev ali enkrat na leto) izberite daljši časovni okvir in definicijo izgube.

## <a name="create-a-transaction-churn-prediction"></a>Ustvarjanje predvidevanja izgube transakcij

1. Pojdi do **Inteligenca** > **Napovedi**.

1. Na **Ustvari** zavihek izberite **Uporabite model** na **Model odliva strank** ploščica.

1. Izberite **Transakcija** za vrsto odtoka in nato **Začeti**.

1. **Poimenujte ta model** in **izhodno ime entitete**, da jih ločite od drugih modelov ali entitet.

1. Izberite **Naprej**.

### <a name="define-customer-churn"></a>Določitev izgube stranke

Izberite **Shrani osnutek** kadar koli shranite predvidevanje kot osnutek. Osnutek predvidevanje se prikaže v **Moje napovedi** zavihek.

1. Nastavite **predvidevanje okno**. Na primer, v naslednjih 90 dneh predvidite tveganje za izgubo strank, da temu prilagodite vaša prizadevanja za uspešno trženje. Predvidevanje tveganja izgube za daljše ali krajše časovno obdobje lahko oteži obravnavo dejavnikov v vašem profilu tveganja izgub, vendar je to odvisno od vaših specifičnih poslovnih potreb.

1. Vnesite število dni za določitev odliva v **Opredelitev odliva** polje. Na primer, če stranka ni opravila nakupa v zadnjih 30 dneh, se lahko šteje, da je zapustila vaše podjetje.

1. Izberite **Naprej**.

### <a name="add-purchase-history"></a>Dodajanje zgodovine nakupov

1. Izberite **Dodajte podatke** za **Zgodovina transakcij strank**.

1. Izberite vrsto semantične dejavnosti, **Prodajni nalog** oz **SalesOrderLine**, ki vsebuje informacije o zgodovini transakcij. Če dejavnost ni nastavljena, izberite **tukaj** in ga ustvarite.

1. Spodaj **dejavnosti**, če so bili atributi dejavnosti semantično preslikani, ko je bila dejavnost ustvarjena, izberite določene atribute ali entiteto, na katero želite, da se osredotoči izračun. Če do semantične preslikave ni prišlo, izberite **Uredi** in preslikajte svoje podatke.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Stransko podokno prikazuje izbiro določenih dejavnosti pod semantično vrsto.":::

1. Izberite **Naslednji** in preglejte atribute, potrebne za ta model.

1. Izberite **Shrani**.

1. Dodajte več dejavnosti ali izberite **Naslednji**.

# <a name="individual-consumers-b-to-c"></a>[Posamezni potrošniki (prodaja strankam)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Dodajanje dodatnih podatkov (izbirno)

1. Izberite **Dodajte podatke** za **Aktivnosti strank**.

1. Izberite vrsto semantične dejavnosti, ki vsebuje podatke, ki jih želite uporabiti. Če dejavnost ni nastavljena, izberite **tukaj** in ga ustvarite.

1. Spodaj **dejavnosti**, če so bili atributi dejavnosti semantično preslikani, ko je bila dejavnost ustvarjena, izberite določene atribute ali entiteto, na katero želite, da se osredotoči izračun. Če do semantične preslikave ni prišlo, izberite **Uredi** in preslikajte svoje podatke.

1. Izberite **Naslednji** in preglejte atribute, potrebne za ta model.

1. Izberite **Shrani**.

1. Izberite **Naprej**

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (podjetja podjetjem)](#tab/b2b)

### <a name="select-prediction-level"></a>Izbira ravni predvidevanja

Večina predvidevanj je ustvarjenih na ravni strank. V nekaterih primerih to morda ni dovolj natančno, da bi zadostilo vašim poslovnim potrebam. Uporabite to funkcijo za napovedovanje odliva na primer za podružnico stranke, namesto za stranko kot celoto.

1. Izberite **Izberite entiteto za sekundarno raven**. Če možnost ni na voljo, preverite, ali ste dokončali prejšnji razdelek.

1. Razširite entitete, med katerimi želite izbrati sekundarno raven, ali uporabite polje filtra za iskanje za filtriranje izbranih možnosti.

1. Izberite atribut, ki ga želite uporabiti kot sekundarno raven, nato izberite **Dodaj**.

1. Izberite **Naprej**.

> [!NOTE]
> Entitete, ki so na voljo v tem razdelku, so prikazane, ker imajo odnos z entiteto, ki ste jo izbrali v prejšnjem razdelku. Če ne vidite entitete, ki jo želite dodati, se prepričajte, da ima veljaven odnos v **Odnosi**. Za to konfiguracijo sta veljavna samo odnosa ena proti ena in mnogo proti ena.

### <a name="add-additional-data-optional"></a>Dodajanje dodatnih podatkov (izbirno)

1. Izberite **Dodajte podatke** za **Aktivnosti strank**.

1. Izberite vrsto semantične dejavnosti, ki vsebuje podatke, ki jih želite uporabiti. Če dejavnost ni nastavljena, izberite **tukaj** in ga ustvarite.

1. Spodaj **dejavnosti**, če so bili atributi dejavnosti semantično preslikani, ko je bila dejavnost ustvarjena, izberite določene atribute ali entiteto, na katero želite, da se osredotoči izračun. Če do semantične preslikave ni prišlo, izberite **Uredi** in preslikajte svoje podatke.

1. Izberite **Naslednji** in preglejte atribute, potrebne za ta model.

1. Izberite **Shrani**.

1. Izberite **Naprej**

1. Po želji izberite **Dodaj podatke** za **Podatki o strankah**.

1. Preslikajte semantične atribute v polja v vaših podatkih o strankah kot prepoznana. Podatki v uporabljenih poljih se ne bi smeli pogosto spreminjati, da bi zagotovili najboljšo zmogljivost modela. Na primer, pri izbiri polja za »Razvrstitev«, ki se spreminja vsak mesec, bi bila uporabljena le zadnja vrednost v predvidevanju, čeprav v preteklosti ista vrednost morda ne bi veljala za stranko pri izdelavi vzorcev predvidevanja.

1. Izberite **Naprej**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Navajanje izbirnega seznama referenčnih računov

Dodajte seznam poslovnih strank in računov, ki jih želite uporabiti kot referenčne vrednosti. The [podrobnosti za te primerjalne račune](#view-prediction-results) vključite njihov rezultat odliva in najvplivnejše funkcije, ki so vplivale na njihov odliv predvidevanje.

1. Izberite **+ Dodaj stranke**.

1. Izberite stranke, ki delujejo kot referenčna vrednost.

1. Izberite **Naprej**.

---

### <a name="set-update-schedule"></a>Nastavitev urnika posodobitev

1. Za **Posodobitve podatkov** korak, izberite pogostost za ponovno usposabljanje vašega modela. Ta nastavitev je pomembna za posodobitev točnosti napovedi, ko se v Customer Insights vnesejo novi podatki. Večina podjetij se lahko prekvalificira enkrat na mesec in pridobi dobro natančnost svojih predvidevanj.

1. Izberite **Naprej**.

### <a name="review-and-run-the-model-configuration"></a>Pregled in zagon konfiguracije modela

The **Pregled in zagon** korak prikazuje povzetek konfiguracije in nudi možnost spreminjanja, preden ustvarite predvidevanje.

1. Izberite **Uredi** na katerem koli od korakov za pregled in morebitne spremembe.

1. Če ste zadovoljni s svojo izbiro, izberite **Shrani in zaženi** da začnete izvajati model. Izberite **Dokončano**. The **Moje napovedi** zavihek se prikaže med ustvarjanjem predvidevanje. Postopek lahko traja več ur, odvisno od količine podatkov, uporabljenih v predvidevanju.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Oglejte si predvidevanje rezultate

1. Pojdi do **Inteligenca** > **Napovedi**.

1. V **Moje napovedi** izberite predvidevanje, ki si ga želite ogledati.

# <a name="individual-consumers-b-to-c"></a>[Posamezni potrošniki (prodaja strankam)](#tab/b2c)

Na strani z rezultati so trije primarni razdelki podatkov:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (podjetja podjetjem)](#tab/b2b)

Na strani z rezultati so trije primarni razdelki podatkov:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

An **Vplivna analiza lastnosti** informacijska stran vsebuje štiri razdelke podatkov:

- V desnem podoknu izberite element iz **Vrhunske stranke** oz **Primerjalne stranke**. Oba seznama sta razvrščena po padajoči vrednosti ocene izgube, ne glede na to, ali je ocena samo za stranko ali kombinirana ocena za stranke in kategorijo izdelkov sekundarne ravni. Izbrani element določa vsebino na tej strani.

  - **Najboljše stranke**: seznam 10 strank z največjim tveganjem izgube in najnižjim tveganjem izgube na podlagi njihovih ocen izgube.
  - **Stranke z referenčno vrednostjo**: seznam do 10 strank, ki so bile izbrane med konfiguracijo modela.

- **Ocena izgube:** v desnem podoknu prikaže oceno izgube izbranega elementa.

- **Porazdelitev tveganja opustitve:** Prikazuje porazdelitev tveganja odliva po strankah in percentil, v katerem je izbrana stranka.

- **Glavne funkcije, ki povečujejo in zmanjšujejo tveganje odliva:** V desnem podoknu navede pet najboljših funkcij, ki so povečale ali zmanjšale tveganje odliva za izbrani element. Prikazuje vrednost funkcije za to postavko in njen vpliv na oceno osipa za vsako vplivno funkcijo. Prikazana je tudi povprečna vrednost vsake funkcije v segmentih strank z nizko, srednjo in visoko stopnjo izgube. Pomaga bolje kontekstualizirati vrednosti najboljših vplivnih lastnosti izbranega elementa in jih primerjati z nizko, srednjo in visoko stopnjo izgube v segmentih strank.

  - Nizka: računi ali kombinacije računa in sekundarne ravni z oceno osipa med 0 in 0,33.
  - Srednje: računi ali kombinacije računov in sekundarnih ravni z oceno osipa med 0,33 in 0,66.
  - Visoka: računi ali kombinacije računov in sekundarnih ravni z oceno osipa, večjo od 0,66.

  Ko predvidevate izgubo na ravni računa, se pri izpeljavi povprečnih vrednosti funkcij za segmente izgub upoštevajo vsi računi. Za predvidevanja izgube na sekundarni ravni za vsak račun je izpeljava segmentov izgub odvisna od sekundarne ravni elementa, izbranega v stranskem podoknu. Na primer, če ima artikel sekundarno raven kategorije izdelka (pisarniški material), potem se pri izpeljavi povprečnih vrednosti lastnosti za segmente osipa upoštevajo samo artikli, ki imajo pisarniški material kot kategorijo izdelka. Ta logika se uporablja za zagotovitev zadovoljive primerjave vrednosti funkcij elementa s povprečnimi vrednostmi v segmentih z nizko, srednjo in visoko stopnjo izgube.

  V nekaterih primerih je povprečna vrednost segmentov nizke, srednje ali visoke stopnje izgube prazna ali ni na voljo, ker na podlagi zgornje definicije ni elementov, ki bi pripadali ustreznim segmentom izgub.

  Razlaga vrednosti pod povprečnimi nizkimi, srednjimi in visokimi stolpci je različna za kategorijske značilnosti, kot sta država ali panoga. Ker se pojem »povprečne« vrednosti funkcije ne uporablja za kategorijske značilnosti, so vrednosti v teh stolpcih delež strank v segmentih z nizko, srednjo in visoko stopnjo izgube, ki imajo enako vrednost kategorijskega elementa v primerjavi z izdelkom, izbranim na stranski plošči.

---

 > [!NOTE]
 > V izhodni entiteti za ta model *ChurnScore* prikazuje predvideno verjetnost odliva in *IsChurn* je binarna oznaka, ki temelji na *ChurnScore* s pragom 0,5. Če ta privzeti prag ne deluje za vaš scenarij, [ustvarite nov segment](segments.md#create-a-segment) z vašim želenim pragom. Vse stranke niso nujno tudi dejavne stranke. Nekatere od njih morda že dolgo niso bile dejavne in se na podlagi definicije izgube že štejejo za izgubljene. Predvidevanje tveganja za izgubo za stranke, ki so že izgubile, ni koristno, ker niso občinstvo, ki nas zanima.
>
> Če si želite ogledati rezultat odliva, pojdite na **podatki** > **Entitete** in si oglejte podatkovni zavihek za izhodno entiteto, ki ste jo definirali za ta model.

[!INCLUDE [footer-include](includes/footer-banner.md)]
