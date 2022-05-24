---
title: Ustvarjanje in upravljanje okolij
description: Naučite se, kako se prijaviti za storitev in kako upravljati okolja.
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 599cbaf4e19c3a7331e92bfc54c701fefe6c69b3
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741061"
---
# <a name="manage-environments"></a>Upravljanje okolij

## <a name="switch-environments"></a>Zamenjava okolja

V zgornjem desnem kotu strani izberite kontrolnik **Okolje**, če želite spremeniti okolje.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Posnetek zaslona kontrolnika za preklapljanje med okolji.":::

Če ste skrbnik, lahko [ustvarite](create-environment.md) in upravljate okolja.

## <a name="edit-an-existing-environment"></a>Urejanje obstoječega okolja

Uredite lahko določene podatke obstoječih okolij.

1.  V glavi aplikacije izberite izbirnik **Okolje**.

2.  Izberite ikono za **urejanje**.

3. V polju **Urejanje okolja**, lahko posodobite nastavitve okolja.

Za več informacij o nastavitvah okolja glejte [Ustvarjanje novega okolja](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Vzpostavljanje povezave s programom Microsoft Dataverse
   
Korak **Microsoft Dataverse** vam omogoča, da povežete Customer Insights s svojim okoljem Dataverse. 

Ponudite svoje Microsoft Dataverse okolje za izmenjavo podatkov (profilov in vpogledov) s poslovnimi aplikacijami, ki temeljijo na Dataverse, kot je Dynamics 365 Marketing ali modelsko vodene aplikacije v Power Apps.

Če želite uporabiti [pripravljene modele predvidevanja](predictions-overview.md#out-of-box-models), konfigurirajte skupno rabo podatkov z okoljem Dataverse. Ali pa omogočite uvoz podatkov iz virov podatkov na mestu uporabe, ki zagotavljajo URL za okolje Microsoft Dataverse, ki ga upravlja vaša organizacija.

Omogočanje skupne rabe podatkov z Microsoft Dataverse če izberete potrditveno polje za skupno rabo podatkov, boste sprožili enkratno popolno osvežitev vaših podatkovnih virov in vseh drugih procesov.

> [!IMPORTANT]
> 1. Vpogled v stranke in Dataverse morajo biti v isti regiji, da omogočite skupno rabo podatkov.
> 1. Imeti morate vlogo globalnega skrbnika v Dataverse okolje. Preverite, če je to [Dataverse okolje je povezano](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) v določene varnostne skupine in se prepričajte, da ste dodani v te varnostne skupine.
> 1. Nobeno obstoječe okolje Customer Insights ni že povezano s tem Dataverse okolje. Naučite se [odstranite obstoječo povezavo z a Dataverse okolje](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Možnosti konfiguracije za omogočanje skupne rabe podatkov s storitvijo Microsoft Dataverse.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Omogoči skupno rabo podatkov z Dataverse od svojega Azure Data Lake Storage (predogled)

Če je vaše okolje konfigurirano za uporabo lastnega Azure Data Lake Storage za shranjevanje podatkov Customer Insights, kar omogoča skupno rabo podatkov z Microsoft Dataverse potrebuje dodatno konfiguracijo.

1. Ustvarite dve varnostni skupini v svoji naročnini na Azure – eno **Uporabnik z dovoljenjem za branje** varnostna skupina in ena **sodelavec** varnostno skupino in nastavite Microsoft Dataverse kot lastnik za obe varnostni skupini.
2. Upravljajte seznam za nadzor dostopa (ACL) v vsebniku CustomerInsights v vašem računu za shranjevanje prek teh varnostnih skupin. Dodajte Microsoft Dataverse storitev in vse Dataverse poslovne aplikacije, kot je Dynamics 365 Marketing za **Uporabnik z dovoljenjem za branje** varnostna skupina z **le za branje** dovoljenja. Dodaj *samo* aplikacijo Customers Insights za **sodelavec** varnostna skupina za odobritev obojega **beri in piši** dovoljenja za pisanje profilov in vpogledov.
   
#### <a name="prerequisites"></a>Zahteve

Za izvajanje skriptov PowerShell morate imeti uvožene naslednje tri module. 

1. Namestite najnovejšo različico [Azure Active Directory PowerShell za graf](/powershell/azure/active-directory/install-adv2).
   1. V računalniku izberite tipko Windows na tipkovnici in poiščite **Windows PowerShell** in izberite **Zaženi kot skrbnik**.
   1. V oknu PowerShell, ki se odpre, vnesite `Install-Module AzureAD`.
2. Uvozi tri module.
    1. V oknu PowerShell vnesite`Install-Module -Name Az.Accounts` in sledite korakom. 
    1. Ponovite za`Install-Module -Name Az.Resources` in `Install-Module -Name Az.Storage`.

#### <a name="configuration-steps"></a>Koraki konfiguracije

1. Prenesite dva skripta PowerShell, ki ju morate zagnati, od našega inženirja [GitHub repo](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Potrebujete *skrbnik najemnika* dovoljenja za zagon tega skripta PowerShell. 
       - Ta skript PowerShell ustvari dve varnostni skupini v vaši naročnini na Azure. Ena za skupino Uporabnik z dovoljenjem za branje in druga za skupino sodelavec in bo Microsoft Dataverse kot lastnik obeh varnostnih skupin.
       - Izvedite ta skript PowerShell v Windows PowerShell tako, da zagotovite ID naročnine Azure, ki vsebuje vaš Azure Data Lake Storage. Odprite skript PowerShell v urejevalniku, da si ogledate dodatne informacije in implementirano logiko.
       - Shranite obe vrednosti ID-ja varnostne skupine, ki ju generira ta skript, ker ju bomo uporabili v`ByolSetup.ps1` skripta.
       
        > [!NOTE]
        > Ustvarjanje varnostne skupine je mogoče onemogočiti v vašem najemniku. V tem primeru bi bila potrebna ročna nastavitev in vaša Azure AD admin bi moral [omogoči ustvarjanje varnostne skupine](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Potrebujete *Lastnik podatkov shranjevalnih blokov* dovoljenja na ravni računa za shranjevanje/vsebnika za zagon tega skripta ali pa ga bo ta skript ustvaril za vas. Vašo dodelitev vloge lahko ročno odstranite po uspešnem zagonu skripta.
        - Ta skript PowerShell doda zahtevan nadzor dostopa na osnovi tole (RBAC) za Microsoft Dataverse storitev in vse Dataverse -poslovne aplikacije. Prav tako posodobi seznam nadzora dostopa (ACL) v vsebniku CustomerInsights za varnostne skupine, ustvarjene z`CreateSecurityGroups.ps1` skripta. Skupina sodelavec bo imela *rwx* dovoljenje in skupina bralcev bo imela *rx* samo dovoljenje.
        - Izvedite ta skript PowerShell v Windows PowerShell tako, da zagotovite ID naročnine Azure, ki vsebuje vaš Azure Data Lake Storage, ime računa za shranjevanje, ime skupine sredstev ter vrednosti ID-ja varnostne skupine Uporabnik z dovoljenjem za branje in sodelavec. Odprite skript PowerShell v urejevalniku, da si ogledate dodatne informacije in implementirano logiko.
        - Kopirajte izhodni niz po uspešnem zagonu skripta. Izhodni niz izgleda takole:`https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Vnesite izhodni niz, kopiran od zgoraj, v **Identifikator dovoljenj** polje koraka konfiguracije okolja za Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Možnosti konfiguracije za omogočanje lastne skupne rabe podatkov Azure Data Lake Storage z Microsoft Dataverse .":::

Storitev Customer Insights ne podpira naslednjih primerov skupne rabe podatkov.
- Če omogočite skupno rabo podatkov s storitvijo Dataverse, ne boste mogli [ustvariti predvidenih ali manjkajočih vrednosti v entiteti](predictions.md).
- Če omogočite skupno rabo podatkov z Dataverse, v okolju Customer Insights si ne boste mogli ogledati nobenih izbirnih poročil PowerBI Embedded.

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Odstranite obstoječo povezavo z a Dataverse okolje

Ko se povežete z a Dataverse okolje, sporočilo o napaki **Ta organizacija CDS je že povezana z drugim primerkom Customer Insights** pomeni, da Dataverse okolje se že uporablja v okolju Customer Insights. Obstoječo povezavo lahko odstranite kot globalni skrbnik na Dataverse okolje. Zapolnitev sprememb lahko traja nekaj ur.

1. Obiščite spletno mesto [Power Apps](https://make.powerapps.com).
1. Izberite okolje v izbirniku okolja.
1. Pojdi do **Rešitve**
1. Odstranite ali izbrišite imenovano rešitev **Dynamics 365 Customer Insights Dodatek za kartico stranke (predogled)**.

ALI 

1. Odprite svojo Dataverse okolje.
1. Pojdi do **Napredne nastavitve** > **Rešitve**.
1. Odstranite **CustomerInsightsCustomerCard** rešitev.

## <a name="copy-the-environment-configuration"></a>Kopiranje konfiguracije okolja

Kot skrbnik se lahko odločite za kopiranje konfiguracije iz obstoječega okolja, ko ustvarite novo. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Posnetek zaslona možnosti nastavitev v nastavitvah okolja.":::

Prikazan bo seznam vseh razpoložljivih okolij iz vaše organizacije, od koder lahko kopirate podatke.

Kopirane so naslednje konfiguracijske nastavitve:

- Vključeni/uvoženi viri podatkov
- Konfiguracija združevanja podatkov
- Segmenti
- Mere
- Relacije
- dejavnosti
- Kazalo za iskanje in filtre
- Izvoz ciljev
- Načrtovano osveževanje
- Obogatitve
- Upravljanje modelov
- Dodelitve vloge

## <a name="set-up-a-copied-environment"></a>Nastavite kopirano okolje

Ko kopirate konfiguracijo okolja, so naslednji podatki *ne* kopirano:

- Profili strank
- Poverilnice virov podatkov. Za vsak vir podatkov boste morali zagotoviti poverilnice in ročno osvežiti vire podatkov.
- Viri podatkov iz mape Common Data Model in upravljanega jezera podatkov Dataverse. Te vire podatkov boste morali ustvariti ročno z istim imenom kot v izvornem okolju.
- Povezovalne skrivnosti, ki se uporabljajo za izvoz in obogatitev. Ponovno morate preveriti pristnost povezav in nato ponovno aktivirati obogatitve in izvoze. 

Ko kopirate okolje, boste videli potrditveno sporočilo, da je bilo ustvarjeno novo okolje. Izberite **Na vire podatkov**, da prikažete seznam virov podatkov.

Vsi viri podatkov bodo prikazovali stanje **Zahtevane poverilnice**. Uredite vire podatkov in vnesite poverilnice, da jih osvežite.

:::image type="content" source="media/data-sources-copied.png" alt-text="Seznam virov podatkov, ki so bili kopirani in potrebujejo preverjanje pristnosti.":::

Ko osvežite vire podatkov, se pomaknite na možnost **Podatki** > **Poenoti**. Tukaj so na voljo nastavitve iz izvornega okolja. Po potrebi jih uredite ali izberite **Zagon**, da zaženete proces poenotenja podatkov in ustvarite poenoteno entiteto stranke.

Ko je poenotenje podatkov dokončano, odprite možnost **Mere** in **Segmenti**, da ju prav tako osvežite.

Preden znova aktivirate izvoze in obogatitve, pojdite na **Admin** > **Povezave** za ponovno preverjanje pristnosti povezav v vašem novem okolju.

## <a name="change-the-owner-of-an-environment"></a>Spremenite lastnika okolja

Medtem ko ima lahko več uporabnikov skrbniška dovoljenja v Customer Insights, je samo en uporabnik lastnik okolja. Privzeto je skrbnik tisti, ki prvotno ustvari okolje. Kot skrbnik okolja lahko dodelite lastništvo drugemu uporabniku s skrbniškimi dovoljenji.

1. V glavi aplikacije izberite izbirnik **Okolje**.

1. Izberite ikono za **urejanje**.

1. V **Uredi okolje** polje, pojdite na **Osnovni podatki** korak.

1. V **Zamenjajte lastnika okolja** polje, izberite novega lastnika okolja.  

1. Izberite **Preglejte in dokončajte**, potem **Nadgradnja** za uveljavitev sprememb. 

## <a name="claim-ownership-of-an-environment"></a>Zahtevajte lastništvo okolja

Če lastnik okolja zapusti organizacijo ali je njegov uporabniški račun izbrisan, okolje ne bo imelo lastnika. Uporabnik s skrbniškimi dovoljenji lahko zahteva lastništvo in postane novi lastnik. Še naprej si lahko lastijo okolje oz [spremeni lastništvo drugemu skrbniku](#change-the-owner-of-an-environment). 

Če želite zahtevati lastništvo, izberite **Prevzemi lastništvo** gumb, ki se prikaže na vrhu vsake strani v Customer Insights, ko je prvotni lastnik zapustil organizacijo.

## <a name="reset-an-existing-environment"></a>Ponastavitev obstoječega okolja

Kot lastnik okolja lahko okolje ponastavite na prazno stanje, če želite izbrisati vse konfiguracije in odstraniti vnesene podatke.

1.  V glavi aplikacije izberite izbirnik **Okolje**. 

2.  Izberite okolje, ki ga želite ponastaviti, nato pa tri pike (**...**). 

3. Izberite možnost **Ponastavi**. 

4.  Če želite potrditi brisanje, vnesite ime okolja in izberite **Ponastavi**.

## <a name="delete-an-existing-environment"></a>Brisanje obstoječega okolja

Kot lastnik okolja lahko izbrišete okolje, ki ga upravljate.

1.  V glavi aplikacije izberite izbirnik **Okolje**.

2.  Izberite okolje, ki ga želite ponastaviti, nato pa tri pike (**...**). 

3. Izberite možnost **Izbriši**. 

4.  Če želite potrditi izbris, vnesite ime okolja in izberite **Izbriši**.

> [!NOTE]
> Če izbrišete okolje, ne odstranite povezave z a Dataverse okolje. Naučite se [odstranite obstoječo povezavo z a Dataverse okolje](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE [footer-include](includes/footer-banner.md)]
