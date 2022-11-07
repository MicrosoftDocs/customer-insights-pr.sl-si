---
title: Dejavnosti stika s strankami ali podjetja
description: Določite dejavnosti stika s stranko ali podjetjem in si jih oglejte na časovnici v profilih strank.
ms.date: 10/26/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: srivas15
ms.author: shsri
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: d8caa477278f04c3a0a95ced15f4bea2a22aa8cd
ms.sourcegitcommit: da6a2d189edacc8f2c0f2abedcb28245f26fe74c
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 10/27/2022
ms.locfileid: "9723801"
---
# <a name="customer-or-business-contact-activities"></a>Dejavnosti stika s strankami ali podjetja

Aktivnosti strank so dejanja ali dogodki, ki jih izvajajo stranke ali poslovni stiki. Na primer transakcije, trajanje klicev podpore, pregledi spletnih mest, nakupi ali vračila. Te dejavnosti so vsebovane v enem ali več virih podatkov. Z Customers Insights konsolidirajte svoje dejavnosti strank iz teh [viri podatkov](data-sources.md) in jih povežite s profili strank. Te dejavnosti so prikazane kronološko na časovnici v profilu stranke. Vključite časovnico v aplikacije Dynamics 365 z [Dodatek za kartico stranke](customer-card-add-in.md) rešitev.

## <a name="define-a-customer-activity"></a>Določite dejavnost stranke

Entiteta mora imeti vsaj en atribut vrste **Datum** vključiti v časovnico stranke. Ukaz **Dodaj dejavnost** je onemogočen, če take entitete ni mogoče najti.

1. Pojdi do **podatki** > **dejavnosti**.

1. Izberite **Dodajte dejavnost** za začetek vodene izkušnje.

1. V **Podatki o dejavnosti** koraku vnesite naslednje podatke:

   - **Ime dejavnosti**: izberite ime dejavnosti.
   - **Subjekt dejavnosti** : izberite entiteto, ki vključuje podatke o transakcijah ali dejavnostih.
   - **Primarni ključ**: izberite polje, ki edinstveno določi zapis. Ne sme vsebovati podvojenih, praznih ali manjkajočih vrednosti.

     > [!NOTE]
     > Primarni ključ za vsako vrstico mora ostati dosleden med vir podatkov osvežitvami. Če je primarni ključ za vrstico posodobljen v vir podatkov osvežitvi, ustvari dvojnike v izhodni entiteti dejavnosti. 

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Nastavite podatke o dejavnosti za ime, entiteto in primarni ključ.":::

1. Izberite **Naprej**.

1. V **Razmerje** korak, izberite **Dodajte razmerje** za povezavo vaših podatkov o dejavnosti z ustreznim zapisom stranke. V koraku so upodobljene povezave med entitetami.  

   - **Tuji ključ** : Tuje polje v vaši entiteti dejavnosti, ki bo uporabljeno za vzpostavitev odnosa z drugo entiteto.
   - **Na ime subjekta** : Ustrezna izvorna entiteta stranke, s katero bo vaša entiteta dejavnosti v razmerju. Nanašate se lahko samo na izvorne entitete strank, ki se uporabljajo v postopku poenotenja podatkov.
   - **Ime razmerja** : Če razmerje med to entiteto dejavnosti in izbrano izvorno entiteto stranke že obstaja, bo ime razmerja v načinu samo za branje. Če takšen odnos ni na voljo, bo na podlagi imena, ki ste ga navedli v tem polju, ustvarjen nov.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Določite odnos entitete.":::

   > [!TIP]
   > V okoljih »podjetja podjetjem« lahko izbirate med entitetami računa in drugimi entitetami. Če izberete entiteto računa, se pot odnosa samodejno nastavi. Za druge entitete morate določiti pot odnosa do ene ali več vmesnih entitet, dokler ne dosežete entitete računa.

1. Izberite **Prijavite se** ustvariti odnos.

1. Izberite **Naprej**.

1. V koraku **Poenotenje dejavnosti** izberite dogodek dejavnosti in čas začetka dejavnosti.
   - **Zahtevana polja**
      - **Dejavnost dogodka**: polje, ki predstavlja dogodek za to dejavnost.
      - **Časovni žig**: polje, ki predstavlja čas začetka dejavnosti.

   - **Izbirna polja**
      - **Dodatne podrobnosti**: polje z relevantnimi informacijami za to dejavnost.
      - **Ikona**: ikona, ki najbolje predstavlja to vrsto dejavnosti.
      - **Spletni naslov** : polje z URL-jem s podatki o tej dejavnosti. Na primer transakcijski sistem, ki je vir te dejavnosti. Ta URL je lahko katero koli polje iz vir podatkov ali pa je sestavljen kot novo polje z Power Query transformacija. Podatki z URL-ja bodo shranjeni v entiteti *Poenotena dejavnost*, ki se lahko porabi v nadaljnjem toku z uporabo [API-jev](apis.md).

   - **Pokaži na časovnici**
      - Izberite, če želite to dejavnost pokazati v pogledu časovnice vaših profilov strank. Izberite **Da** za prikaz dejavnosti v časovnici ali **Ne**, da jih skrijete.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="V entiteti Poenotena dejavnost navedite podatke o dejavnosti stranke.":::

1. Izberite **Naslednji**, da izberete vrsto dejavnosti, ali izberite **Dokončaj in pregledaj** da shranite dejavnost z nastavljeno vrsto dejavnosti **drugo**.

1. V koraku **Vrsta dejavnosti** izberite vrsto dejavnosti in po želji izberite, ali želite semantično preslikati nekatere vrste dejavnosti za uporabo na drugih področjih storitve Customer Insights. Trenutno, *Povratne informacije*, *·*, *nalog*, *·*, in *Naročnina* tipi dejavnosti podpirajo semantiko po strinjanju s preslikavo polj. Če vrsta dejavnosti za novo dejavnost ni pomembna, lahko izberete možnost *Drugo* ali *Ustvari novo* za prilagojeno vrsto dejavnosti.

1. Izberite **Naprej**.

1. V koraku **Pregled** preverite svoje izbire. Vrnite se na kateregakoli izmed prejšnjih korakov in posodobite podatke, če je to potrebno.

1. Izberite možnost **Shrani dejavnost** za uporabo sprememb in izberite možnost **Končano**, da se vrnete v razdelek **Podatki** > **Dejavnosti**. Prikaže se ustvarjena dejavnost.

1. Ko ustvarite vse svoje dejavnosti, izberite **Teči** jih obdelati.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-customer-activities"></a>Upravljajte dejavnosti obstoječih strank

Pojdi do **podatki** > **dejavnosti** da si ogledate svoje shranjene dejavnosti, njihovo izvorno entiteto, vrsto dejavnosti in ali so vključene v časovnico stranke. Seznam dejavnosti lahko razvrstite po katerem koli stolpcu ali uporabite iskalno polje, da poiščete dejavnost, ki jo želite upravljati.

Izberite dejavnost za ogled razpoložljivih dejanj.

- **Uredi** dejavnost za spremembo njegove konfiguracije. Konfiguracija se odpre v koraku pregleda. Po spremembi konfiguracije izberite možnost **Shrani dejavnost** in nato izberite možnost **Zaženi** za obdelavo sprememb.
- **Preimenuj** dejavnost. Če želite uporabiti spremembe, izberite **Shrani**.
- **Izbriši** dejavnost. Če želite izbrisati več kot eno dejavnost hkrati, izberite dejavnosti in nato **Izbriši**. Potrdite brisanje.

## <a name="view-activity-timelines-on-customer-profiles"></a>Ogled časovnic dejavnosti v profilih strank

1. Če ste izbrali **Prikaži na časovnici dejavnosti** v konfiguraciji dejavnosti pojdite na **Stranke** in izberite profil stranke, da si ogledate dejavnosti stranke v **Časovnica dejavnosti** razdelek.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Oglejte si konfigurirane dejavnosti v profilih strank.":::

1. Če želite filtrirati dejavnosti na časovnici dejavnosti:

   - Izberite eno ali več ikon dejavnosti, da izboljšate rezultate, da bodo vključevali samo izbrane vrste.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtrirajte dejavnosti po vrstah z uporabo ikon.":::

   - Izberite **Filter** da odprete ploščo s filtri za konfiguracijo filtrov časovne osi. Filtriraj po *ActivityType* in/ali *Datum*. Izberite **Uporabi**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="S ploščo filtrov konfigurirajte pogoje filtra.":::

> [!NOTE]
> Filtri dejavnosti se odstranijo, ko zapustite profil stranke. Uporabiti jih morate vsakič, ko odprete profil stranke.

## <a name="define-a-contact-activity"></a>Določite dejavnost stika

Za poslovne račune (B-to-B) uporabite a *ContactProfile* entiteta za zajemanje dejavnosti stikov. Na časovnici dejavnosti za račun lahko vidite, kateri stik je bil odgovoren za posamezno dejavnost. Večina korakov sledi konfiguraciji preslikave dejavnosti strank.

   > [!NOTE]
   > Če želite definirati dejavnost na ravni stika, a *ContactProfile* mora biti ustvarjena entiteta bodisi kot a [enoten kontaktni profil](data-unification-contacts.md) ali skozi [pomensko preslikavo](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).
   >
   > Morate imeti oboje **AccountID** in **ContactID** atribute za vsak zapis v vaših podatkih o dejavnosti.
  
1. Pojdi do **podatki** > **dejavnosti**.

1. Izberite **Dodaj dejavnost**.

1. V **Podatki o dejavnosti** koraku vnesite naslednje podatke:

   - **Ime dejavnosti**: izberite ime dejavnosti.
   - **Subjekt dejavnosti** : izberite entiteto, ki vključuje podatke o transakcijah ali dejavnostih.
   - **Primarni ključ**: izberite polje, ki edinstveno določi zapis. Ne sme vsebovati podvojenih, praznih ali manjkajočih vrednosti.

     > [!NOTE]
     > Primarni ključ za vsako vrstico mora ostati dosleden med vir podatkov osvežitvami. Če je primarni ključ za vrstico posodobljen v vir podatkov osvežitvi, ustvari dvojnike v izhodni entiteti dejavnosti. 


1. V **Odnosi** koraku ustvarite posredno razmerje med podatki o izvoru dejavnosti in računi, pri čemer uporabite svoje kontaktne podatke kot posredniško entiteto. Za več informacij glejte [neposredne in posredne poti odnosov](relationships.md#relationship-paths).
   - Primer razmerja za dejavnost, imenovano *Nakupi*:
      - **Podatki o izvorni dejavnosti nakupov** > **Kontaktni podatki** na atributu **ContactID**
      - **Kontaktni podatki** > **Podatki o računu** na atributu **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Primer postavitve razmerja.":::

1. Po nastavitvi Odnosi izberite **Naslednji** in dokončajte konfiguracijo preslikave dejavnosti. Za podrobne korake o ustvarjanju dejavnosti glejte [določite dejavnost stranke](#define-a-customer-activity).

1. Zaženite svoje preslikave dejavnosti.

1. Vaše dejavnosti na ravni stika bodo zdaj vidne na časovnici vaše stranke.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Končni rezultat po konfiguraciji dejavnosti stika":::

## <a name="contact-level-activity-timeline-filtering"></a>Filtriranje časovne premice dejavnosti na ravni stika

Ko konfigurirate preslikavo dejavnosti na ravni kontakta in jo zaženete, bo časovnica dejavnosti za vaše stranke posodobljena. Vključuje njihove ID-je ali imena, odvisno od vašega *ContactProfile* konfiguracijo, za dejavnosti, na katerih so ukrepali. Dejavnosti lahko filtrirate po stikih na časovnici in si ogledate določene stike, ki vas zanimajo. Poleg tega si lahko z izbiro ogledate vse dejavnosti, ki niso dodeljene določenemu stiku **Dejavnosti niso preslikane v stik**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Možnosti filtriranja so na voljo za dejavnosti na ravni stika.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
