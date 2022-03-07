---
title: Izvoz podatkov iz storitve Customer Insights
description: Upravljajte izvoze za skupno rabo podatkov.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: 33f59c62565560517c480be63e581465605c5f7b
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354345"
---
# <a name="exports-preview-overview"></a>Pregled izvozov (predogledna različica)

Na strani **Izvozi** so prikazani vsi konfigurirani izvozi. Izvozi dajo specifične podatke v skupno rabo z različnimi aplikacijami. Vključujejo lahko profile strank, entitete, sheme in podrobnosti preslikave. Za vsak izvoz je potrebna [povezava, ki jo nastavi skrbnik, za upravljanje preverjanja pristnosti in dostopa](connections.md).

Pojdite na **Podatki** > **Izvozi** za ogled strani z izvozi. Konfigurirani izvozi so za ogled na voljo vsem uporabniškim vlogam. S pomočjo iskalnega polja v ukazni vrstici poiščite izvoze glede na njihovo poimenovanje, ime povezave ali vrsto povezave.

## <a name="export-types"></a>Vrste izvoza

Obstajata dve glavni vrsti izvoza:  

- **Podatkovni izvoz** omogoča izvoz vseh vrst entitet, ki so na voljo v vpogledih v občinstvo. Entitete, ki jih izberete za izvoz, se izvozijo z vsemi podatkovnimi polji, metapodatki, shemami in podrobnostmi preslikave. 
- **Izvoz segmenta** omogoča izvoz izvoženih segmentov iz vpogledov v občinstvo. Segmenti predstavljajo seznam profilov strank. Pri konfiguriranju izvoza izberete vključena podatkovna polja, odvisno od ciljnega sistema, v katerega izvozite podatke. 

### <a name="export-segments"></a>Izvoz segmentov

**Izvoz segmentov v okolja za poslovne kupce (podjetja podjetjem) ali posamezne potrošnike (prodaja strankam)**  
Večina možnosti izvoza podpira obe vrsti okolij. Izvoz segmentov v različne ciljne sisteme ima posebne zahteve. Na splošno član segmenta, profil stranke, vsebuje podatke za stik. Čeprav to običajno velja za segmente, ki temeljijo na posameznih potrošnikih (prodaja strankam), to ne velja nujno za segmente, ki temeljijo na poslovnih kupcih (podjetja podjetjem). 

**Izvozi segmenta v okoljih za poslovne kupce (podjetja podjetjem)**  
- Segmenti v kontekstu okolij za poslovne račune temeljijo na entiteti *računa*. Če želite izvoziti segmente računov takšne, kot so, mora ciljni sistem podpirati čiste segmente računov. To velja za [LinkedIn](export-linkedin-ads.md), ko izberete možnost **podjetje** pri definiranju izvoza.
- Vsi drugi ciljni sistemi zahtevajo polja iz entitete stika. Če želite zagotoviti, da lahko segmenti računa pridobivajo podatke iz povezanih stikov, mora vaša definicija segmenta projicirati atribute entitete stika. Preberite več o tem, kako [konfigurirati segmente in atribute projekta](segment-builder.md).

**Izvozi segmenta v okoljih za posamezne potrošnike (prodaja strankam)**  
- Segmenti v kontekstu okolij za posamezne stranke temeljijo na entiteti *poenotenega profila stranke*. Izvoziti je mogoče vsak segment, ki izpolnjuje zahteve ciljnih sistemov (na primer e-poštni naslov).

**Omejitve pri izvozu segmentov**  
- Ciljni sistemi neodvisnih izdelovalcev lahko omejijo število profilov strank, ki jih lahko izvozite. 
- Za posamezne stranke boste ob izbiri segmenta za izvoz videli dejansko število članov segmenta. Če je segment prevelik, boste prejeli opozorilo. 
- Pri poslovnih računih boste videli število računov v segmentu; vendar se število projiciranih stikov ne prikaže. V nekaterih primerih bi to lahko pripeljalo do tega, da izvoženi segment dejansko vsebuje več profilov strank, kot jih ciljni sistem sprejme. Preseganje omejitev rezultatov ciljnih sistemov bo preskočilo izvoz. 

## <a name="set-up-a-new-export"></a>Nastavitev novega izvoza  
Če želite nastaviti ali urediti izvoz, morate imeti na voljo povezave. Povezave so odvisne od vaše [uporabniške vloge](permissions.md):
- **Skrbniki** imajo dostop do vseh povezav. Pri nastavitvi izvoza lahko ustvarijo tudi nove povezave.
- **Udeleženci** lahko imajo dostop do določenih povezav. Pri konfiguriranju in skupni rabi povezav so odvisni od skrbnikov. Seznam izvozov sodelavcem prikazuje, ali lahko urejajo ali samo ogledujejo izvoz v stolpcu **Vaša dovoljenja**. Za več informacij odprite razdelek [Omogočanje sodelujočim, da uporabljajo povezavo za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Gledalci** si lahko ogledajo samo obstoječe izvoze, ne morejo pa jih ustvariti.

### <a name="define-a-new-export"></a>Določitev novega izvoza

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite možnost **Dodaj izvoz**, da ustvarite nov izvoz.

1. V podoknu **Nastavitev izvoza** izberite, katero povezavo uporabiti. [Povezave](connections.md) upravljajo skrbniki. 

1. Navedite zahtevane podrobnosti in izberite **Shrani**, da ustvarite izvoz.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Določitev novega izvoza na podlagi obstoječega izvoza

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Na seznamu izvozov izberite izvoz, ki ga želite podvojiti.

1. Izberite **Ustvari dvojnik** v ukazni vrstici, da odprete podokno **Nastavi izvoz** s podrobnostmi izbranega izvoza.

1. Preglejte in prilagodite izvoz ter izberite **Shrani**, da ustvarite nov izvoz.

### <a name="edit-an-export"></a>Urejanje izvoza

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Na seznamu izvozov izberite izvoz, ki ga želite urediti.

1. V ukazni vrstici izberite **Uredi**.

1. Spremenite vrednosti, ki jih želite posodobiti, in izberite **Shrani**.

## <a name="view-exports-and-export-details"></a>Ogled izvozov in podrobnosti izvozov

Po ustvarjanju ciljev za izvoz so ti navedeni na **Podatki** > **Izvozi**. Vsi uporabniki lahko vidijo, kateri podatki so v skupni rabi in njihovo zadnje stanje.

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Uporabniki brez dovoljenja za urejanje naj za ogled podrobnosti o izvozu izberejo možnost **Pogled**, ne pa možnosti **Uredi**.

1. V stranskem podoknu je prikazana konfiguracija izvoza. Brez dovoljenj za urejanje ne morete spreminjati vrednosti. Izberite **Zapri**, da se vrnete na stran z izvozi.

## <a name="schedule-and-run-exports"></a>Načrtovanje in zagon izvozov

Vsak izvoz, ki ga konfigurirate, ima urnik osveževanja. Med osveževanjem sistem išče nove ali posodobljene podatke, ki jih bo vključil v izvoz. Izvozi se privzeto izvajajo kot del vsakega [načrtovanega osveževanja sistema](system.md#schedule-tab). Za ročni zagon izvozov lahko prilagodite urnik osveževanja ali ga izklopite.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

Urniki izvoza so odvisni od stanja vašega okolja. Če so posodobitve v teku v [odvisnostih](system.md#refresh-processes), ko bi se moral načrtovani izvoz začeti, bo sistem najprej dokončal posodobitve, šele nato pa začel z izvozom. V stolpcu **Osveženo** lahko vidite, kdaj je bil izvoz nazadnje osvežen.

### <a name="schedule-exports"></a>Načrtovanje izvozov

Določite lahko urnike osveževanja po meri za posamezen izvoz ali več izvozov hkrati. Trenutno določen urnik je naveden v stolpcu **Načrtovanje** na seznamu izvoza. Dovoljenje za spremembo urnika je enako kot za [urejanje in določanje izvozov](export-destinations.md#set-up-a-new-export). 

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite izvoz, ki ga želite načrtovati.

1. V ukazni vrstici izberite **Načrtovanje**.

1. V podoknu **Načrtovanje izvoza** nastavite **Zagon načrtovanja** na **Vklopljeno**, da samodejno zaženete izvoz. Nastavite ga na **Izklopljeno**, da ga ročno osvežite.

1. Za samodejno osvežene izvoze izberite vrednost **Ponovitev** in določite podrobnosti zanjo. Opredeljeni čas velja za vse primerke ponovitev. To je čas, ko bi se izvoz moral začeti osveževati.

1. Svoje spremembe uveljavite in aktivirajte tako, da izberete **Shrani**.

Pri urejanju urnika za več izvozov morate izbrati eno od možnosti v razdelku **Obdržite ali preglasite razporede**:
- **Obdržite posamezne razporede**: obdržite predhodno določeni urnik za izbrane izvoze in jih le onemogočite ali omogočite.
- **Določite nov urnik za vse izbrane izvoze**: preglasite obstoječe urnike izbranih izvozov.

### <a name="run-exports-on-demand"></a>Zaženi izvoze na zahtevo

Za izvoz podatkov brez čakanja na načrtovano osvežitev, pojdite na **Podatki** > **Izvozi**.

- Če želite zagnati vse izvoze, izberite **Zaženi vse** v ukazni vrstici. S tem dejanjem se bodo zagnali samo izvozi z aktivnim urnikom.
- Če želite zagnati en izvoz, ga izberite na seznamu in kliknite **Zaženi** v ukazni vrstici. Tako boste zagnali izvoze brez aktivnega urnika. 

## <a name="remove-an-export"></a>Odstranjevanje izvoza

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite izvoz, ki ga želite odstraniti.

1. V ukazni vrstici izberite **Odstrani**.

1. Odstranjevanje potrdite tako, da na potrditvenem zaslonu izberete **Odstrani**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
