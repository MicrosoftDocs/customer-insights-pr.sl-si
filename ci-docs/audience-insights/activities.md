---
title: Dejavnosti stranke
description: Določite dejavnosti stranke in si jih oglejte na časovnici stranke.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1c95cba333266a73959de0a3afe1c8677130a3ec
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667249"
---
# <a name="customer-activities"></a>Dejavnosti stranke

Združite dejavnosti stranke iz [različnih virov podatkov](data-sources.md) v storitvi Dynamics 365 Customer Insights, da ustvarite časovnico stranke, v katerem so njene dejavnosti navedene v kronološkem vrstnem redu. Časovnico lahko vključite v aplikacije Customer Engagement v storitvi Dynamics 365 prek [dodatka za kartico stranke](customer-card-add-in.md) ali v nadzorni plošči Power BI.

## <a name="define-an-activity"></a>Določanje dejavnosti

Vaši viri podatkov vključujejo entitete s transakcijskimi podatki in podatki o dejavnosti iz več virov podatkov. Določite te entitete in izberite časovnice, ki si jih želite ogledati na časovnici stranke. Izberite entiteto, ki vključuje vašo ciljno dejavnost ali dejavnosti.

1. Pri vpogledih v občinstvo izberite **Podatki** > **Dejavnosti**.

1. Izberite **Dodaj dejavnost**.

   > [!NOTE]
   > Entiteta mora imeti vsaj en atribut vrste **Datum**, da je lahko vključena na časovnico stranke, vi pa ne morete dodajati entitet brez polja **Datum**. Ukaz **Dodaj dejavnost** je onemogočen, če take entitete ni mogoče najti.

1. V podoknu **Dodaj dejavnost** nastavite vrednosti za naslednja polja:

   - **Entiteta**: izberite entiteto, ki vključuje transakcijske podatke ali podatke o dejavnosti.
   - **Primarni ključ**: izberite polje, ki edinstveno določi zapis. Ne sme vsebovati podvojenih, praznih ali manjkajočih vrednosti.
   - **Časovni žig**: izberite polje, ki predstavlja začetni čas vaše dejavnosti.
   - **Dogodek**: izberite polje, ki je dogodek za dejavnost.
   - **Spletni naslov**: izberite polje, ki predstavlja URL z dodatnimi informacijami o tej dejavnosti. Na primer transakcijski sistem, ki je vir te dejavnosti. Ta URL je lahko katero koli polje iz vira podatkov, lahko pa je oblikovano kot novo polje s pretvorbo v orodju Power Query. Ti podatki URL-ja bodo shranjeni v entiteti Združene dejavnosti, ki jo je mogoče uporabiti na daljavo z uporabo API-jev.
   - **Podrobnosti**: po želji izberite polje, ki je dodano za dodatne podrobnosti.
   - **Ikona**: po želji izberite ikono, ki predstavlja to dejavnost.
   - **Vrsta dejavnosti**: določite sklic vrste dejavnosti kot Common Data Model, ki najbolje opisuje semantično definicijo dejavnosti.

1. V razdelku **Nastavitev odnosa** konfigurirajte podrobnosti, da podatke o dejavnosti povežete z ustrezno stranko.

   > [!div class="mx-imgBorder"]
   > ![Določanje odnosa entitete](media/activities-entities-define.png "Določanje odnosa entitete")

    - **Polje entitete dejavnosti** : Izberite polje v svoji entiteti dejavnosti, ki bo uporabljeno za vzpostavitev odnosa z drugo entiteto.
    - **Entiteta stranke** : Izberite ustrezno izvorno entiteto stranke, s katero bo vaša entiteta dejavnosti v odnosu. Odnose lahko vzpostavite le s tistimi izvornimi entitetami strank, ki so uporabljene v postopku poenotenja podatkov.
    - **Polje entitete stranke**: V tem polju je prikazan primarni ključ izvorne entitete stranke, ki je bil izbran v postopku preslikave. To polje primarnega ključa v izvorni entiteti stranke se uporablja za vzpostavitev odnosa z entiteto dejavnosti.
    - **Ime**: Če odnos med to entiteto dejavnosti in izbrano izvorno entiteto stranke že obstaja, bo ime odnosa na voljo v načinu samo za branje. Če odnos ne obstaja, se ustvari nov odnos s tukaj navedenim imenom.

1. Če želite uporabiti spremembe, izberite **Shrani**.

1. Na strani **Dejavnosti** izberite **Zaženi**.

> [!TIP]
> Na voljo je [šest vrst stanja](system.md#status-types) za opravila/postopke. Poleg tega je večina postopkov [odvisna od drugih nadaljnjih postopkov](system.md#refresh-policies). Izberete lahko stanje postopka in si ogledate podrobnosti o poteku celotnega posla. Ko za enega izmed poslov izberete **Prikaži podrobnosti**, se prikažejo dodatne informacije: čas obdelave, zadnji datum obdelave ter vse napake in opozorila, povezana z opravilom.

## <a name="edit-an-activity"></a>Urejanje dejavnosti

1. Pri vpogledih v občinstvo izberite **Podatki** > **Dejavnosti**.

2. Izberite entiteto dejavnosti, ki jo želite urediti, in izberite **Uredi**. Lahko pa se s kazalcem miške pomaknete na vrstico entitete in izberete ikono **Uredi**.

3. Kliknite ikono **Uredi**.

4. V podoknu **Uredi dejavnost** posodobite vrednosti in izberite **Shrani**.

5. Na strani **Dejavnosti** izberite **Zaženi**.

## <a name="delete-an-activity"></a>Brisanje dejavnosti

1. Pri vpogledih v občinstvo izberite **Podatki** > **Dejavnosti**.

2. Izberite entiteto dejavnosti, ki jo želite odstraniti, in izberite **Izbriši**. Lahko pa se s kazalcem miške pomaknete na vrstico entitete in izberete ikono **Izbriši**. Poleg tega lahko hkrati izberete več entitet dejavnosti, ki jih želite izbrisati.
   > [!div class="mx-imgBorder"]
   > ![Urejanje ali brisanje odnosa entitete](media/activities-entities-edit-delete.png "Urejanje ali brisanje odnosa entitete")

3. Izberite ikono **Izbriši**.

4. Potrdite izbris.
