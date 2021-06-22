---
title: Izvoz podatkov iz storitve Customer Insights
description: Upravljajte izvoze za skupno rabo podatkov.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253060"
---
# <a name="exports-preview-overview"></a>Pregled izvozov (predogledna različica)

Na strani **Izvozi** so prikazani vsi konfigurirani izvozi. Izvozi dajo specifične podatke v skupno rabo z različnimi aplikacijami. Vključujejo lahko profile strank ali entitete, sheme in podrobnosti o preslikavi. Za vsak izvoz je potrebna [povezava, ki jo nastavi skrbnik, za upravljanje preverjanja pristnosti in dostopa](connections.md).

Pojdite na **Podatki** > **Izvozi** za ogled strani z izvozi. Vse uporabniške vloge imajo dostop za ogled konfiguriranih izvozov. Uporabite polje za iskanje v ukazni vrstici, da najdete izvoze po njihovem imenu, imenu povezave in vrsti povezave.

## <a name="set-up-a-new-export"></a>Nastavitev novega izvoza

Če želite nastaviti ali urediti izvoz, morate imeti na voljo povezave. Povezave so odvisne od vaše [uporabniške vloge](permissions.md):
- Skrbniki imajo dostop do vseh povezav. Pri nastavitvi izvoza lahko ustvarijo tudi nove povezave.
- Udeleženci lahko imajo dostop do določenih povezav. Pri konfiguriranju in skupni rabi povezav so odvisni od skrbnikov. Seznam izvozov sodelavcem prikazuje, ali lahko urejajo ali samo ogledujejo izvoz v stolpcu **Vaša dovoljenja**. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Gledalci si lahko ogledajo samo obstoječe izvoze, vendar jih ne morejo ustvariti.

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

1. Uporabniki brez dovoljenj za urejanje izberejo **Ogled** namesto **Urejanje** za prikaz podrobnosti izvoza.

1. V stranskem podoknu je prikazana konfiguracija izvoza. Brez dovoljenj za urejanje ne morete spreminjati vrednosti. Izberite **Zapri**, da se vrnete na stran z izvozi.

## <a name="schedule-and-run-exports"></a>Načrtovanje in zagon izvozov

Vsak izvoz, ki ga konfigurirate, ima urnik osveževanja. Med osveževanjem sistem išče nove ali posodobljene podatke, ki jih bo vključil v izvoz. Izvozi se privzeto izvajajo kot del vsakega [načrtovanega osveževanja sistema](system.md#schedule-tab). Za ročni zagon izvozov lahko prilagodite urnik osveževanja ali ga izklopite.

Urniki izvoza so odvisni od stanja vašega okolja. Če potekajo posodobitve [odvisnosti](system.md#refresh-policies), ko naj bi se začel načrtovani izvoz, bo sistem najprej dokončal odvisnosti in nato zagnal izvoz. V stolpcu **Osveženo** lahko vidite, kdaj je bil izvoz nazadnje osvežen.

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
