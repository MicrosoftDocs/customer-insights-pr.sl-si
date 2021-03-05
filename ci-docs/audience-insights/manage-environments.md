---
title: Ustvarjanje in upravljanje okolij
description: Naučite se, kako se prijaviti za storitev in kako upravljati okolja.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 744f0bcbf5d2700363180f44e38d6dee9bf5df63
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270132"
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

Če želite ustvariti okolje:

1. V glavi aplikacije izberite izbirnik **Okolje**.

1. Izberite **Novo**.

   > [!div class="mx-imgBorder"]
   > ![Nastavitve okolja](media/environment-settings-dialog.png)

1. V pogovornem oknu **Ustvari novo okolje** izberite **Novo okolje**.

   Če želite [prekopirati podatke iz trenutnega okolja](#additional-considerations-for-copy-configuration-preview), izberite **Kopiraj iz obstoječega okolja**. Prikazan bo seznam vseh razpoložljivih okolij iz vaše organizacije, od koder lahko kopirate podatke.

1. Navedite naslednje podrobnosti:
   - **Ime**: ime tega okolja. To polje je že izpolnjeno, če ste kopirali iz obstoječega okolja, lahko pa ga spremenite.
   - **Območje**: območje, v katerem je storitev uvedena in gostovana.
   - **Vrsta**: izberite, ali želite ustvariti produkcijsko ali preizkusno okolje.

2. Če želite, lahko izberete **Napredne nastavitve**:

   - **Shrani vse podatke v**: določa, kam želite shraniti izhodne podatke, ustvarjene s storitvijo Customer Insights. Na voljo imate dve možnosti: **Shramba za Customer Insights** (shramba Azure Data Lake, ki jo upravlja ekipa za Customer Insights) in **Azure Data Lake Storage Gen2** (vaša shramba Azure Data Lake Storage). Privzeto je izbrana možnost »Shramba za Customer Insights«.

   > [!NOTE]
   > Če shranite podatke v Azure Data Lake Storage, se strinjate, da bodo podatki preneseni na ustrezno geografsko lokacijo za ta račun za shrambo Azure in tam shranjeni. Ta lokacija se lahko razlikuje od lokacije, kjer so shranjeni podatki v storitvi Dynamics 365 Customer Insights. [Več o tem preberite v Microsoftovem središču zaupanja.](https://www.microsoft.com/trust-center)
   >
   > Trenutno se uvožene entitete vedno shranijo v shrambo Data Lake, ki jo upravlja aplikacija Customer Insights.
   > Podpiramo samo račune za shranjevanje Azure Data Lake Gen2 iz iste regije Azure, ki ste jo izbrali pri ustvarjanju okolja.
   > Podpiramo samo račune za shrambo z omogočenim hierarhičnim imenskim prostorom (HNS) shrambe Azure Data Lake Gen2.

   - Za možnost Azure Data Lake Storage Gen2 lahko izbirate med možnostjo, ki temelji na viru, in možnostjo preverjanja pristnosti, ki temelji na naročnini. Za več informacij glejte [Povezovanje vpogledov v občinstvo in računa Azure Data Lake Storage Gen2 z glavnim imenom storitve Azure](connect-service-principal.md). Imena **Vsebnik** ni mogoče spremeniti in bo naslednji: customerinsights.
   
   - Če želite uporabiti [predvidevanja](predictions.md) ali konfigurirati skupno rabo podatkov z aplikacijami in rešitvami, ki temeljijo na storitvi Microsoft Dataverse, navedite URL okolja Microsoft Dataverse pod razdelkom **Konfigurirajte skupno rabo podatkov z Microsoft Dataverse in omogočite dodatne zmogljivosti**. Izberite možnost **Omogoči skupno rabo podatkov** za skupno rabo izhodnih podatkov Customer Insights s storitvijo Microsoft Dataverse Managed Data Lake.

     > [!NOTE]
     > - Skupna raba podatkov s storitvijo Microsoft Dataverse Managed Data Lake trenutno ni podprta, če vse podatke shranjujete v shrambi Azure Data Lake Storage.
     > - [Predvidevanje manjkajočih vrednosti v entiteti](predictions.md) trenutno ni podprto, če je omogočena skupna rabo podatkov s storitvijo Microsoft Dataverse Managed Data Lake.

     > [!div class="mx-imgBorder"]
     > ![Možnosti konfiguracije za omogočanje skupne rabe podatkov s storitvijo Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)

   Ko zaženete postopke, na primer uvoz podatkov ali ustvarjanje segmenta, bodo v zgoraj navedenem računu za shranjevanje ustvarjene ustrezne mape. Podatkovne datoteke in datoteke model.json bodo ustvarjene in dodane v zadevne podmape na podlagi procesa, ki ga izvajate.

   Če ustvarite več okolij Customer Insights in izhodne entitete iz teh okolij shranite v svoj račun za shranjevanje, bodo za vsako okolje ustvarjene ločene mape, pri čemer bo v vsebniku ci_<environmentid>.

### <a name="additional-considerations-for-copy-configuration-preview"></a>Dodatni premisleki glede konfiguracije kopiranja (predogled)

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
- Viri podatkov iz mape Common Data Model in upravljanega jezera Common Data Service. Te vire podatkov boste morali ustvariti ročno z istim imenom kot v izvornem okolju.

Ko kopirate okolje, boste videli potrditveno sporočilo, da je bilo ustvarjeno novo okolje. Izberite **Na vire podatkov**, da prikažete seznam virov podatkov.

Vsi viri podatkov bodo prikazovali stanje **Zahtevane poverilnice**. Uredite vire podatkov in vnesite poverilnice, da jih osvežite.

> [!div class="mx-imgBorder"]
> ![Viri podatkov kopirani](media/data-sources-copied.png)

Ko osvežite vire podatkov, se pomaknite na možnost **Podatki** > **Poenoti**. Tukaj so na voljo nastavitve iz izvornega okolja. Po potrebi jih uredite ali izberite **Zagon**, da zaženete proces poenotenja podatkov in ustvarite poenoteno entiteto stranke.

Ko je poenotenje podatkov dokončano, odprite možnost **Mere** in **Segmenti**, da ju prav tako osvežite.

## <a name="edit-an-existing-environment"></a>Urejanje obstoječega okolja

Uredite lahko določene podatke obstoječih okolij.

1.  V glavi aplikacije izberite izbirnik **Okolje**.

2.  Izberite ikono za **urejanje**.

3. V polju **Uredi okolje** lahko posodobite **prikazno ime** okolja, vendar pa ne morete spremeniti **regije** ali **tipa**.

4. Če je okolje konfigurirano za shranjevanje podatkov v shrambi Azure Data Lake Storage Gen2, lahko posodobite **ključ računa**. Vendar pa ne morete spremeniti možnosti **Ime računa** ali imena razdelka **Vsebnik**.

5. Po želji lahko posodobitev opravite prek povezave na podlagi ključa kupca s povezavo, ki temelji na viru ali naročnini. Po nadgradnji ne morete povrniti ključa kupca po posodobitvi. Za več informacij glejte [Povezovanje vpogledov v občinstvo in računa Azure Data Lake Storage Gen2 z glavnim imenom storitve Azure](connect-service-principal.md). Ob posodobitvi povezave ne morete spremeniti podatkov **vsebnika**.

## <a name="reset-an-existing-environment"></a>Ponastavitev obstoječega okolja

Če želite izbrisati vse konfiguracije in odstraniti vključene podatke, lahko kot administrator okolje ponastavite v prazno stanje.

1.  V glavi aplikacije izberite izbirnik **Okolje**. 

2.  Izberite okolje, ki ga želite ponastaviti, in izberite tri pike **...**. 

3. Izberite možnost **Ponastavi**. 

4.  Če želite potrditi brisanje, vnesite ime okolja in izberite **Ponastavi**.

## <a name="delete-an-existing-environment-available-only-for-admins"></a>Izbris obstoječega okolja (na voljo samo za skrbnike)

Kot skrbnik lahko izbrišete okolja, katerih skrbnik ste.

1.  V glavi aplikacije izberite izbirnik **Okolje**.

2.  Izberite okolje, ki ga želite ponastaviti, in izberite tri pike **...**. 

3. Izberite možnost **Izbriši**. 

4.  Če želite potrditi izbris, vnesite ime okolja in izberite **Izbriši**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]