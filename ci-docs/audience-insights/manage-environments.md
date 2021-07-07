---
title: Ustvarjanje in upravljanje okolij
description: Naučite se, kako se prijaviti za storitev in kako upravljati okolja.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 904ce68336cba4b7a4d5a37692b72d091400559d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304900"
---
# <a name="manage-environments"></a>Upravljanje okolij

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Ta članek pojasnjuje, kako ustvariti novo organizacijo in kako omogočiti uporabo okolja.

## <a name="sign-up-and-create-an-organization"></a>Prijavite se in ustvarite organizacijo

1. Pojdite na spletno mesto [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).

2. Izberite **Začetek**.

3. Izberite želeni scenarij prijave in ustrezno povezavo.

4. Sprejmite določila in pogoje in izberite **Nadaljuj**, da začnete ustvarjati organizacijo.

5. Ko je okolje ustvarjeno, boste preusmerjeni na storitev [Customer Insights](https://home.ci.ai.dynamics.com).

6. Uporabite predstavitveno okolje za raziskovanje aplikacije ali pa ustvarite novo okolje po korakih, opisanih v naslednjem razdelku.

7. Ko določite nastavitve okolja, izberite **Ustvari**.

8. Po uspešnem ustvarjanju okolja boste prijavljeni.

## <a name="create-an-environment-in-an-existing-organization"></a>Ustvarite okolje v obstoječi organizaciji

Novo okolje lahko ustvarite na dva načina. Lahko določite popolnoma novo konfiguracijo ali kopirate nekatere konfiguracijske nastavitve iz obstoječega okolja.

> [!NOTE]
> Organizacije lahko ustvarijo *dve* okolji za vsako licenco Customer Insights. Če vaša organizacija kupi več kot eno licenco, [se obrnite na našo skupino za podporo](https://go.microsoft.com/fwlink/?linkid=2079641), da vam poveča število razpoložljivih okolij. Za več informacij o zmogljivosti in dodatni zmogljivosti prenesite [Vodnik za licenciranje za Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Če želite ustvariti okolje:

1. V glavi aplikacije izberite izbirnik **Okolje**.

1. Izberite **Novo**.

   > [!div class="mx-imgBorder"]
   > ![Nastavitve okolja.](media/environment-settings-dialog.png)

1. V pogovornem oknu **Ustvari okolje** izberite **Novo okolje**.

   Če želite [prekopirati podatke iz trenutnega okolja](#considerations-for-copy-configuration-preview), izberite **Kopiraj iz obstoječega okolja**. Prikazan bo seznam vseh razpoložljivih okolij iz vaše organizacije, od koder lahko kopirate podatke.

1. Navedite naslednje podrobnosti:
   - **Ime**: ime tega okolja. To polje je že izpolnjeno, če ste kopirali iz obstoječega okolja, lahko pa ga spremenite.
   - **Vrsta**: izberite, ali želite ustvariti produkcijsko ali preizkusno okolje.
   - **Območje**: območje, v katerem je storitev uvedena in gostovana.
   
1. Če želite, lahko izberete **Napredne nastavitve**:

   - **Shrani vse podatke v**: določa, kam želite shraniti izhodne podatke, ustvarjene s storitvijo Customer Insights. Na voljo imate dve možnosti: **Shramba storitve Customer Insights** (storitev Azure Data Lake, ki jo upravlja ekipa za Customer Insights) in **Azure Data Lake Storage** (vaša lastna storitev Azure Data Lake Storage). Privzeto je izbrana možnost »Shramba za Customer Insights«.

     > [!NOTE]
     > Če shranite podatke v Azure Data Lake Storage, se strinjate, da bodo podatki preneseni na ustrezno geografsko lokacijo za ta račun za shrambo Azure in tam shranjeni. Ta lokacija se lahko razlikuje od lokacije, kjer so shranjeni podatki v storitvi Dynamics 365 Customer Insights. [Več o tem preberite v Microsoftovem središču zaupanja.](https://www.microsoft.com/trust-center)
     >
     > Trenutno se uvožene entitete vedno shranijo v shrambo Data Lake, ki jo upravlja aplikacija Customer Insights. 
     > 
     > Podpiramo samo račune Azure Data Lake Storage iz tiste regije v storitvi Azure, ki ste jo izbrali pri ustvarjanju okolja. 
     > 
     > Podpiramo samo račune Azure Data Lake Storage z omogočenim hierarhičnim imenskim prostorom.


   - V sklopu možnosti Azure Data Lake Storage lahko za preverjanje pristnosti izberete možnost, ki temelji na virih, ali možnost, ki temelji na naročnini. Za več informacij glejte [Povezovanje vpogledov v občinstvo in računa Azure Data Lake Storage Gen2 z glavnim imenom storitve Azure](connect-service-principal.md). Imena **Zabojnika** ni mogoče spremeniti in ostaja `customerinsights`.
   
   - Če želite uporabljati [napovedi](predictions.md), konfigurirati skupno rabo podatkov z okoljem Microsoft Dataverse ali omogočiti uvoz podatkov iz podatkovnih virov na mestu uporabe, zagotovite URL okolja Microsoft Dataverse pod možnostjo **Konfiguriranje skupne rabe podatkov s storitvijo Microsoft Dataverse in omogočanje dodatnih zmogljivosti**. Izberite možnost **Omogoči skupno rabo podatkov** za skupno rabo izhodnih podatkov Customer Insights s storitvijo Microsoft Dataverse Managed Data Lake.

     > [!NOTE]
     > - Skupna raba podatkov s storitvijo Microsoft Dataverse Managed Data Lake trenutno ni podprta, če vse podatke shranjujete v shrambi Azure Data Lake Storage.
     > - [Predvidevanje manjkajočih vrednosti v entiteti](predictions.md) trenutno ni podprto, če je omogočena skupna rabo podatkov s storitvijo Microsoft Dataverse Managed Data Lake.

     > [!div class="mx-imgBorder"]
     > ![Možnosti konfiguracije za omogočanje skupne rabe podatkov s storitvijo Microsoft Dataverse.](media/datasharing-with-DataverseMDL.png)

   Ko zaženete postopke, na primer uvoz podatkov ali ustvarjanje segmenta, bodo v zgoraj navedenem računu za shranjevanje ustvarjene ustrezne mape. Podatkovne datoteke in datoteke model.json bodo ustvarjene in dodane v mape na podlagi imena postopka.

   Če ustvarite več okolij Customer Insights in izhodne entitete iz teh okolij shranite v svoj račun za shranjevanje, bodo za vsako okolje ustvarjene ločene mape, pri čemer bo v vsebniku ci_<environmentid>.

### <a name="considerations-for-copy-configuration-preview"></a>Vidiki za konfiguracijo kopiranja (predogledna različica)

Kopirane so naslednje konfiguracijske nastavitve:

- Konfiguracije funkcije
- Vključeni/uvoženi viri podatkov
- Konfiguracija poenotenja podatkov (preslikava, ujemanje, spajanje)
- Segmenti
- Mere
- Odnosi
- Dejavnosti
- Kazalo za iskanje in filtre
- Izvoz ciljev
- Načrtovano osveževanje
- Obogatitve
- Upravljanje modelov
- Dodelitve vloge

Naslednje nastavitve *niso* kopirane:

- Profili strank
- Poverilnice virov podatkov. Za vsak vir podatkov boste morali zagotoviti poverilnice in ročno osvežiti vire podatkov.
- Viri podatkov iz mape Common Data Model in shrambe Data Lake, ki jo upravlja Dataverse. Te vire podatkov boste morali ustvariti ročno z istim imenom kot v izvornem okolju.

Ko kopirate okolje, boste videli potrditveno sporočilo, da je bilo ustvarjeno novo okolje. Izberite **Na vire podatkov**, da prikažete seznam virov podatkov.

Vsi viri podatkov bodo prikazovali stanje **Zahtevane poverilnice**. Uredite vire podatkov in vnesite poverilnice, da jih osvežite.

> [!div class="mx-imgBorder"]
> ![Kopirani viri podatkov.](media/data-sources-copied.png)

Ko osvežite vire podatkov, se pomaknite na možnost **Podatki** > **Poenoti**. Tukaj so na voljo nastavitve iz izvornega okolja. Po potrebi jih uredite ali izberite **Zagon**, da zaženete proces poenotenja podatkov in ustvarite poenoteno entiteto stranke.

Ko je poenotenje podatkov dokončano, odprite možnost **Mere** in **Segmenti**, da ju prav tako osvežite.

## <a name="edit-an-existing-environment"></a>Urejanje obstoječega okolja

Uredite lahko določene podatke obstoječih okolij.

1.  V glavi aplikacije izberite izbirnik **Okolje**.

2.  Izberite ikono za **urejanje**.

3. V polju **Uredi okolje** lahko posodobite **prikazno ime** okolja, vendar pa ne morete spremeniti **regije** ali **tipa**.

4. Če je okolje konfigurirano za shranjevanje podatkov v shrambi Azure Data Lake Storage, lahko posodobite **Ključ računa**. Vendar pa ne morete spremeniti možnosti **Ime računa** ali imena razdelka **Vsebnik**.

5. Po želji lahko povezavo, ki temelji na ključu računa posodobite ter zamenjate s povezavo, ki temelji na virih ali na naročnini. Po nadgradnji ne morete povrniti ključa kupca po posodobitvi. Za več informacij glejte [Povezovanje vpogledov v občinstvo in računa Azure Data Lake Storage Gen2 z glavnim imenom storitve Azure](connect-service-principal.md). Ob posodobitvi povezave ne morete spremeniti podatkov **vsebnika**.

6. Izbirno lahko zagotovite URL okolja Microsoft Dataverse pod možnostjo **Konfiguriranje skupne rabe podatkov s storitvijo Microsoft Dataverse in omogočanje dodatnih zmogljivosti**. Te zmogljivosti vključujejo skupno rabo podatkov z aplikacijami in rešitvami na podlagi storitve Microsoft Dataverse, uvoz podatkov iz podatkovnih virov na mestu uporabe ali uporabo [napovedi](predictions.md). Izberite možnost **Omogoči skupno rabo podatkov** za skupno rabo izhodnih podatkov Customer Insights s storitvijo Microsoft Dataverse Managed Data Lake.

   > [!NOTE]
   > - Skupna raba podatkov s storitvijo Microsoft Dataverse Managed Data Lake trenutno ni podprta, če vse podatke shranjujete v shrambi Azure Data Lake Storage.
   > - [Predvidevanje manjkajočih vrednosti v entiteti](predictions.md) trenutno ni podprto, ko omogočite izmenjavo podatkov s storitvijo Microsoft Dataverse Managed Data Lake.

   Ko omogočite izmenjavo podatkov z okoljem Microsoft Dataverse, se bo zagnala popolna osvežitev vaših virov podatkov in drugih postopkov. Če se postopki trenutno izvajajo, ne boste videli možnosti za omogočanje skupne rabe podatkov s storitvijo Microsoft Dataverse. Počakajte, da se ti postopki končajo ali jih prekličete, da omogočite izmenjavo podatkov. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Možnosti konfiguracije za omogočanje skupne rabe podatkov s storitvijo Microsoft Dataverse.":::
   
   Ko zaženete postopke, na primer uvoz podatkov ali ustvarjanje segmenta, bodo v zgoraj navedenem računu za shranjevanje ustvarjene ustrezne mape. Podatkovne datoteke in datoteke model.json bodo ustvarjene in dodane v zadevne podmape, odvisno od postopka, ki ga izvajate.

## <a name="reset-an-existing-environment"></a>Ponastavitev obstoječega okolja

Če želite izbrisati vse konfiguracije in odstraniti vključene podatke, lahko kot administrator okolje ponastavite v prazno stanje.

1.  V glavi aplikacije izberite izbirnik **Okolje**. 

2.  Izberite okolje, ki ga želite ponastaviti, nato pa tri pike (**...**). 

3. Izberite možnost **Ponastavi**. 

4.  Če želite potrditi brisanje, vnesite ime okolja in izberite **Ponastavi**.

## <a name="delete-an-existing-environment"></a>Brisanje obstoječega okolja

Kot skrbnik lahko izbrišete okolja, katerih skrbnik ste.

1.  V glavi aplikacije izberite izbirnik **Okolje**.

2.  Izberite okolje, ki ga želite ponastaviti, nato pa tri pike (**...**). 

3. Izberite možnost **Izbriši**. 

4.  Če želite potrditi izbris, vnesite ime okolja in izberite **Izbriši**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
