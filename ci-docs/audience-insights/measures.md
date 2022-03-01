---
title: Ustvarjanje in urejanje mer
description: Določite mere, povezane s strankami, za analizo in odraz uspešnosti določenih poslovnih področij.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406990"
---
# <a name="define-and-manage-measures"></a>Določanje in upravljanje mer

**Mere** predstavljajo ključne kazalnike uspešnosti (KPI), ki odražajo uspešnost in stanje določenih poslovnih področij. Vpogledi v občinstvo ponujajo intuitivno izkušnjo za ustvarjanje različnih vrst mer z uporabo graditelja poizvedb, ki ne zahteva ročnega kodiranja ali preverjanja veljavnosti mer. Na strani **Osnovno** lahko spremljate svoje poslovne mere, na strani **Kartica stranke** si lahko ogledate mere za določeno stranko, na strani **Segmenti** pa lahko uporabite mere za opredelitev segmentov stranke.

## <a name="create-a-measure"></a>Ustvarjanje mere

V tem razdelku so navodila za ustvarjanje mere povsem od začetka. Mere lahko ustvarite s podatki iz več virov podatkov, ki so povezani prek entitete stranke. Veljajo nekatere [omejitve storitev](service-limits.md).

1. Pri vpogledih v občinstvo izberite **Mere**.

2. Izberite **Nova mera**.

3. Izberite **vrsto** mere:

   - **Atribut stranke**: eno polje na stranko, ki odraža rezultat, vrednost ali stanje za stranko. Atributi strank so ustvarjeni kot atributi v novi sistemski entiteti, imenovani **Customer_Measure**.

   - **Mera stranke**: vpogledi v vedenje stranke z razčlenitvijo po izbranih dimenzijah. Za vsako mero se ustvari nova entiteta, lahko tudi z več zapisi na stranko.

   - **Poslovna mera**: spremlja poslovno uspešnost in stanje poslovanja. Poslovne mere imajo lahko dva različna rezultata: številski rezultat, ki je prikazan na strani **Osnovno**, ali novo entiteto, ki jo najdete na strani **Entitete**.

4. Vnesite **ime** in po želji še **Prikazno ime** ter izberite **Naprej**.

5. Na spustnem seznamu v razdelku **Entitete** izberite prvo entiteto. Na tej točki se morate odločiti, ali so v okviru vaše opredelitve mere potrebne dodatne entitete.

   > [!div class="mx-imgBorder"]
   > ![Definicija mere](media/measure-definition.png "Definicija mere")

   Če želite dodati več entitet, izberite **Dodaj entiteto** in izberite entitete, ki jih želite uporabiti za mero.

   > [!NOTE]
   > Izberite lahko samo entitete, ki imajo odnos z vašo začetno entiteto. Če želite več informacij o opredelitvi odnosov, glejte [Odnosi](relationships.md).

6. Po želji lahko konfigurirate spremenljivke. V razdelku **Spremenljivke** izberite **Nova spremenljivka**.

   Spremenljivke so izračuni, ki so narejeni na vsakem od vaših izbranih zapisov. Na primer povzetek prodaje na prodajnem mestu (POS) in v spletu za vsakega od zapisov vaše stranke.

7. Vnesite **ime** za spremenljivko.

8. V območju **Izraz** izberite polje, s katerim boste začeli izračun.

9. Vnesite izraz v območje **Izraz** in izberite več polj, ki bodo vključena v vaš izračun.

   > [!NOTE]
   > Trenutno so podprti samo aritmetični izrazi. Poleg tega izračun spremenljivk ni podprt za entitete z različnih [poti entitet](relationships.md).

10. Izberite **Dokončano**.

11. V razdelku **Opredelitev mere** določite, kako so izbrane entitete in izračunane spremenljivke združene v novi entiteti ali atributu mere.

12. Izberite **Nova dimenzija**. Dimenzijo si lahko predstavljate kot funkcijo *združi po*. Rezultati podatkov entitete ali atributa mere bodo združeni po vseh vaših opredeljenih dimenzijah.

    > [!div class="mx-imgBorder"]
    > ![Izbira cikla združevanja](media/measures-businessreport-measure-definition2.png "Izbira cikla združevanja")

    Kot del definicije dimenzije izberite ali vnesite te podatke:

    - **Entiteta**: če določite entiteto mere, mora vključevati vsaj en atribut. Če določite atribut mere, bo privzeto vseboval le en atribut. Pri tem izboru gre za izbiro entitete, ki vključuje ta atribut.
    - **Polje**: izberite atribut, ki bo vključen v entiteto ali atribut mere.
    - **Vedro**: izberite, ali želite združiti podatke na dnevni, mesečni ali letni osnovi. Ta izbira je obvezna le, če ste izbrali atribut vrste datuma.
    - **Kot**: določa ime vašega novega polja.
    - **Prikazno ime**: določa prikazno ime vašega polja.

    > [!NOTE]
    > Vaša poslovna mera bo shranjena kot entiteta z eno številko in bo prikazana na strani **Osnovno**, razen če v mero dodate več dimenzij. Ko dodate več dimenzij, mera *ni* prikazana na strani **Domov**.

13. Po želji dodajte funkcije združevanja. Vsako združevanje, ki ga ustvarite, ustvari novo vrednost v entiteti ali atributu »Mere«. Podprte funkcije združevanja so: **Min.**, **Maks.**, **Povprečno**, **Mediana**, **Vsota**, **Št. enoličnih**, **Prvi** (uporabi prvi zapis vrednosti dimenzije) in **Zadnji** (uporabi zadnji zapis, dodan v vrednost dimenzije).

14. Izberite **Shrani**, da uporabite spremembe v meri.

## <a name="manage-your-measures"></a>Upravljajte svoje mere

Ko ustvarite vsaj eno mero, boste na strani **Mere** videli seznam mer.

Na voljo so informacije o vrsti mere, ustvarjalcu, datumu in času nastanka, datumu in času zadnjega urejanja, stanju (ali je mera dejavna, nedejavna ali neuspešna) in datumu in času zadnjega osveževanja. Ko s seznama izberete mero, si lahko ogledate njen predogled.

Če želite hkrati osvežiti vse svoje mere, izberite **Osveži vse**, ne da bi izbrali posamezno mero.

> [!div class="mx-imgBorder"]
> ![Dejanja za upravljanje posameznih mer](media/measure-actions.png "Dejanja za upravljanje posameznih mer")

S seznama lahko tudi izberete mero in opravite enega od naslednjih dejanj:

- Za prikaz podrobnosti izberite ime mere.
- Izberete lahko možnost **Uredi** in uredite konfiguracijo mere.
- Mero lahko preimenujete prek možnosti **Preimenuj**.
- Za brisanje mere je na voljo **Izbriši**.
- Izberite tri pike (...) in nato **Osveži**, da začnete postopek osveževanja za mero.
- Izberite tri pike (...) in nato **Prenesi**, če želite pridobiti datoteko .CSV mere.

> [!TIP]
> Na voljo je [šest vrst stanja](system.md#status-types) za opravila/postopke. Poleg tega je večina postopkov [odvisna od drugih nadaljnjih postopkov](system.md#refresh-policies). Izberete lahko stanje postopka in si ogledate podrobnosti o poteku celotnega posla. Ko za enega izmed poslov izberete **Prikaži podrobnosti**, se prikažejo dodatne informacije: čas obdelave, zadnji datum obdelave ter vse napake in opozorila, povezana z opravilom.

## <a name="next-step"></a>Naslednji korak

Obstoječe mere lahko uporabite za ustvarjanje prvega segmenta stranke na strani **Segmenti**. Če želite več informacij, glejte [Segmenti](segments.md).
