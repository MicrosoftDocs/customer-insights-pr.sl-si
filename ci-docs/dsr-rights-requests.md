---
title: Zahteve posameznikov, na katere se nanašajo podatki, (DSR) v skladu z uredbo GDPR | Microsoftovo gradivo
description: Odgovorite na zahteve subjektov podatkov za zmožnost vpogleda Dynamics 365 Customer Insights občinstvo.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: c116f7ce208c0288851a4b2230e27784ba3a5337
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732700"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Zahteve posameznikov, na katere se nanašajo podatki, (DSR) v skladu z uredbo GDPR

Splošna uredba Evropske unije o varstvu podatkov (GDPR) velja od 25. maja 2018. Posameznikom daje pomembne pravice glede njihovih podatkov. Pri GDPR gre za zaščito in omogočanje pravic posameznikov do zasebnosti. Več informacij o Microsoftovi zavezanosti do varnosti in skladnosti lahko preberete v [Microsoftovem središču zaupanja](https://www.microsoft.com/trust-center).

Prizadevamo si, da svojim strankam pomagamo izpolniti zahteve uredbe GDPR. Vključuje pravico do brisanja in izvoza podatkov, kar vključuje osebne podatke, kot so ID-ji uporabnikov, telefonske številke in e-poštni naslovi. Skrbniki lahko izvajajo zahteve uporabnikov za brisanje ali izvoz osebnih podatkov.

## <a name="audience-insights"></a>Vpogledi v občinstvo

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Odgovarjanje na zahteve GDPR, na katere se nanašajo osebni podatki, za zmožnost vpogledov Dynamics 365 Customer Insights občinstvo

»Pravica do izbrisa« z odstranitvijo osebnih podatkov iz podatkov o strankah, ki jih ima organizacija, je ključna zaščita v Splošni uredbi o varstvu podatkov (GDPR). Odstranitev osebnih podatkov vključuje odstranitev vseh osebnih podatkov in sistemsko ustvarjenih dnevnikov, razen informacij iz dnevnika spremljanja sprememb.

#### <a name="manage-data-subject-delete-requests"></a>Upravljanje zahtev posameznika, na katerega se nanašajo podatki, za izbris

Vpogledi v občinstvo nudijo naslednje izkušnje v izdelkih, s katerimi lahko izbrišete osebne podatke za določeno stranko ali uporabnika:

- **Upravljanje zahtev za izbris podatkov o strankah**: podatki o strankah v storitvi Customer Insights se uvozijo iz izvirnih virov podatkov zunaj storitve Customer Insights. Vse zahteve za izbris v skladu z uredbo GDPR morajo biti izvedene v izvirnem viru podatkov.
- **Upravljanje zahtev za izbris uporabniških podatkov storitve Customer Insights**: podatke za uporabnike je ustvaril Customer Insights. Vse zahteve za izbris v skladu z uredbo GDPR morajo biti izvedene v storitvi Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Upravljanje zahtev za izbris podatkov o strankah

Skrbnik storitve Customer Insights lahko upošteva te korake, da odstrani podatke stranke, ki so bili izbrisani iz vira podatkov:

1. Prijavite se v Dynamics 365 Customer Insights.
2. Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.
3. Za vsak vir podatkov na seznamu, ki vsebuje izbrisane podatke strank:
   1. Izberite možnost (...) in nato **Osveži**.
   2. Preverite stanje vira podatkov v razdelku **Stanje**. Kljukica pomeni, da je bila osvežitev uspešna. Opozorilni trikotnik pomeni, da je prišlo do napake. Če se prikaže opozorilni trikotnik, pošljite sporočilo na naslov D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Obravnava zahtev za izbris podatkov o strankah v skladu z uredbo GDPR.](audience-insights/media/gdpr-data-sources.png "Obravnava zahtev za izbris podatkov o strankah v skladu z uredbo GDPR")

##### <a name="manage-delete-requests-for-user-data"></a>Upravljanje zahtev za izbris uporabniških podatkov

Skrbnik storitve Customer Insights lahko za izbris uporabniških podatkov storitve Customer Insights upošteva te korake:

1. Prijavite se v Dynamics 365 Customer Insights.
2. Pri vpogledih v občinstvo izberite **Skrbnik** > **Dovoljenja**.
3. Potrdite polje za uporabnika, ki ga želite izbrisati.
4. Izberite **Odstrani**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Odziv na zahteve posameznikov, na katere se nanašajo podatki, za izvoz v skladu z uredbo GDPR

Kot del naše zaveze za sodelovanje z vami na vaši poti do uvedbe Splošne uredbe o varstvu podatkov (GDPR) smo ustvarili dokumentacijo, ki vam bo pomagala pri pripravi. Ta dokumentacija opisuje korake, ki jih lahko danes opravite za zagotavljanje skladnosti z uredbo GDPR pri uporabi vpogledov v občinstvo.

#### <a name="manage-export-and-view-requests"></a>Upravljajte izvoza in ogled zahtev

Zaradi pravice do prenosljivosti podatkov lahko posamezniki, na katere se nanašajo podatki, zahtevajo kopijo svojih osebnih podatkov v elektronski obliki (tj. »strukturirana, pogosto uporabljena, strojno berljiva in interoperabilna oblika«), ki se jo lahko pošlje drugemu upravljavcu podatkov.

##### <a name="export-customer-data-tenant-admin"></a>Izvoz podatkov o stranki (skrbnik najemnika)

Skrbnik najemnika lahko za izvoz podatkov upošteva ta navodila:

1. Pošljite e-poštno sporočilo na naslov D365CI@microsoft.com ter v zahtevi navedite e-poštni naslov stranke. Ekipa Customer Insights bo na registrirani e-poštni naslov skrbnika najemnika poslala e-poštno sporočilo s prošnjo za potrditev izvoza podatkov.
2. Potrdite potrditev izvoza podatkov za zahtevano stranko.
3. Prejmite izvožene podatke prek e-poštnega naslova skrbnika najemnika.

##### <a name="export-user-data-tenant-admin"></a>Izvoz uporabniških podatkov (skrbnik najemnika)

1. Pošljite e-poštno sporočilo na naslov D365CI@microsoft.com ter v zahtevi navedite e-poštni naslov uporabnika. Ekipa Customer Insights bo na registrirani e-poštni naslov skrbnika najemnika poslala e-poštno sporočilo s prošnjo za potrditev izvoza podatkov.
2. Potrdite potrditev izvoza podatkov za zahtevanega uporabnika.
3. Prejmite izvožene podatke prek e-poštnega naslova skrbnika najemnika.

## <a name="consent-management-preview"></a>Upravljanje privolitve (predogled)

Zmožnost upravljanja privolitve ne zbira uporabniških podatkov neposredno. Uvaža in obdeluje samo podatke o privolitvi, ki jih zagotovijo uporabniki v drugih aplikacijah.

Če želite odstraniti podatke o soglasju o določenih uporabnikih, jih odstranite v virih podatkov, ki jih prevzame zmožnost upravljanja privolitve. Po osvežitvi vir podatkov bodo odstranjeni podatki izbrisani tudi v središču za soglasje. Aplikacije, ki uporabljajo entiteto za soglasje, bodo izbrisale tudi podatke, ki so bili odstranjeni iz vira po a [osveži](audience-insights/system.md#refresh-processes). Priporočamo, da po odzivu na zahtevo posameznika, na katerega se nanašajo osebni podatki, hitro osvežite vire podatkov za odstranitev uporabnikovih podatkov iz vseh drugih procesov in aplikacij.


## <a name="engagement-insights-preview"></a>Vpogledi v interakcije (predogledna različica)

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Brisanje in izvoz podatkov o dogodkih, ki vsebujejo podatke, ki omogočajo identifikacijo končnega uporabnika

Naslednji razdelki opisujejo, kako izbrisati in izvoziti podatke o dogodkih, ki bi lahko vsebovali osebne podatke.

Brisanje ali izvoz podatkov:

1. Označite lastnosti dogodka, ki vsebujejo osebne podatke.
2. Izbrišite ali izvozite podatke, povezane s posebnimi vrednostmi (na primer: določeni ID uporabnika).

#### <a name="tag-and-update-event-properties"></a>Označite in posodobite lastnosti dogodka

Osebni podatki so označeni na ravni lastnosti dogodka. Najprej označite lastnosti, ki se štejejo za brisanje ali izvoz.

Če želite lastnost dogodka označiti kot vsebino z osebnimi podatki, sledite tem korakom:

1. Odprite delovni prostor, ki vsebuje dogodek.

1. Odprite **Podatki** > **Dogodki**, da si ogledate seznam dogodkov v izbranem delovnem prostoru.
  
1. Izberite dogodek, ki ga želite označiti.

1. Izberite **Uredi lastnosti**, da odprete podokno s seznamom vseh lastnosti izbranega dogodka.
     
1. Izberite **...** in nato izberite **Uredi** za dostop do pogovornega okna **Posodobi lastnost**.

   ![Uredite dogodek.](engagement-insights/media/edit-event.png "Uredi dogodek")

1. V oknu **Posodobi lastnost** izberite **...** v zgornjem desnem kotu in nato izberite polje **Vsebuje EUII** (tj. podatki, ki omogočajo identifikacijo končnega uporabnika). Za shranjevanje sprememb izberite **Posodobi**.

   ![Shranite spremembe.](engagement-insights/media/update-property.png "Shranite spremembe")

   > [!NOTE]
   > Vsakič, ko se shema dogodkov spremeni ali ustvarite nov dogodek, je priporočljivo, da ocenite povezane lastnosti dogodka in jih po potrebi označite oz. prekličete njihovo oznako kot vsebino z osebnimi podatki.

#### <a name="delete-or-export-tagged-event-data"></a>Izbrišite ali izvozite označene podatke o dogodkih

Če so bile vse lastnosti dogodka označene ustrezno, kot je opisano v prejšnjem koraku, lahko skrbnik okolja izda zahtevo za izbris proti označenim podatkom dogodka.

Za upravljanje zahtev za izbris ali izvoz EUII

1. Odprite možnost **Skrbnik** > **Okolje** > **Nastavitve**.

1. V razdelku **Upravljanje podatkov, ki omogočajo identifikacijo končnega uporabnika (EUII)** izberite **Upravljanje EUII**.

##### <a name="deletion"></a>Brisanje

Za brisanje lahko v razdelku **Brisanje podatkov, ki omogočajo identifikacijo končnega uporabnika (EUII)** vnesete seznam uporabniških ID-jev, ločenih z vejico. Nato se bodo ti ID-ji primerjali z vsemi označenimi lastnostmi dogodkov vseh projektov v trenutnem okolju s pomočjo natančnega ujemanja nizov. 

Če se vrednost lastnosti ujema z enim od podanih ID-jev, bo povezani dogodek trajno izbrisan. Zaradi nepovratnosti tega dejanja morate potrditi brisanje po izbiri možnosti **Izbriši**.

##### <a name="export"></a>Export

Postopek izvoza je enak postopku brisanja, ko gre za določanje vrednosti lastnosti dogodka v razdelku **Brisanje podatkov, ki omogočajo identifikacijo končnega uporabnika (EUII)**. Poleg tega boste morali navesti **URL shrambe zbirke dvojiških podatkov Azure** za določitev izvoznega cilja. URL zbirke dvojiških podatkov Azure mora vsebovati [podpis dostopa v skupni rabi (SAS)](/azure/storage/common/storage-sas-overview).

Po izbiri možnosti **Izvozi** bodo vsi dogodki trenutne ekipe, ki vsebujejo ujemajoče se označene lastnosti, izvoženi v obliki CSV na cilj izvoza.

### <a name="good-practices"></a>Dobre prakse

* Izogibajte se pošiljanju kakršnih koli dogodkov, ki vsebujejo osebne podatke.
* Če morate poslati dogodke, ki vsebujejo podatke EUII, omejite število dogodkov in lastnosti dogodkov, ki vsebujejo podatke EUII. V idealnem primeru se omejite na en tak dogodek.
* Poskrbite, da bo imelo dostop do poslanih osebnih podatkov čim manj ljudi.
* Za dogodke, ki vsebujejo osebne podatke, nastavite, da ena lastnost oddaja enoličen identifikator, ki ga je mogoče enostavno povezati z določenim uporabnikom (na primer ID uporabnika). To olajša ločevanje podatkov in izvoz ali brisanje pravih podatkov.
* Na dogodek označite samo eno lastnost, ki vsebuje osebne podatke. V idealnem primeru tak, ki vsebuje samo enoličen identifikator.
* Ne označujte lastnosti, ki vsebujejo podrobne vrednosti (na primer celotno telo zahteve). Zmogljivost vpogledov v interakcije uporablja natančno ujemanje nizov pri odločanju, katere dogodke izbrisati ali izvoziti.

[!INCLUDE[footer-include](includes/footer-banner.md)]