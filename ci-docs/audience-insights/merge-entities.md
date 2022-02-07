---
title: Združevanje entitet za poenotenje podatkov
description: Združite entitete za ustvarjanje poenotenih profilov strank.
ms.date: 01/28/2022
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
  - ci-merge
---

# <a name="merge-entities"></a>Združevanje entitet

Faza spajanja je zadnja faza v postopku poenotenja podatkov. Njen namen je uskladitev podatkov v sporu. Primer podatkov v sporu je na primer ime stranke, ki ga najdemo v dveh zbirkah podatkov, vendar je v vsaki prikazan nekoliko drugače (»Grant Marshall« v primerjavi z »Grant Marshal«), ali telefonska številka, ki se razlikuje v obliki zapisa (617-803-091X v primerjavi s 617803091X). Spajanje teh podatkovnih točk v sporu poteka na osnovi »atribut za atributom«.

:::image type="content" source="media/merge-fields-page.png" alt-text="Stran za spajanje v postopku poenotenja podatkov, ki prikazuje tabelo s spojenimi polji, ki določajo poenoten profil kupca.":::

Po zaključku [faze ujemanja](match-entities.md) fazo spajanja začnete tako, da izberete ploščico **Spajanje** na strani **Poenotenje**.

## <a name="review-system-recommendations"></a>Pregled priporočil sistema

V zavihku **Podatki** > **Poenotenje** > **Spajanje** izberete in izključite atribute za spojitev znotraj vaše entitete poenotenega profila kupca. Poenoten profil stranke je rezultat postopka poenotenja podatkov. Sistem samodejno spoji nekatere atribute.

Če si želite ogledati atribute, ki so vključeni v enega od vaših samodejno spojenih atributov, izberite ta spojeni atribut v zavihku **Polja za stranke** v tabeli. Atributi, ki sestavljajo ta spojeni atribut, bodo prikazani v dveh novih vrsticah pod spojenim atributom.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Ločevanje, preimenovanje, izključevanje in urejanje spojenih polj

Spremenite lahko, kako sistem obdeluje spojene atribute, da ustvari poenoten profil stranke. Izberite možnost **Pokaži več** in izberite, kaj želite spremeniti.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Možnosti v spustnem meniju Prikaži več za upravljanje spojenih atributov.":::

Če želite več informacij, glejte naslednje razdelke.

## <a name="separate-merged-fields"></a>Ločevanje spojenih polj

Če želite ločiti spojena polja, v tabeli poiščite atribut. Ločena polja so prikazana kot posamezne podatkovne točke na poenotenem profilu stranke. 

1. Izberite spojeno polje.
  
1. Izberite možnost **Pokaži več** in **Loči polja**.
 
1. Potrdite ločevanje.

1. Izberite možnost **Shrani** in **Zaženi** za obdelavo sprememb.

## <a name="rename-merged-fields"></a>Preimenovanje spojenih polj

Spremenite prikazno ime spojenih atributov. Imen izhodne entitete ni mogoče spremeniti.

1. Izberite spojeno polje.
  
1. Izberite možnost **Pokaži več** in **Preimenuj**.

1. Potrdite spremenjeno prikazno ime. 

1. Izberite možnost **Shrani** in **Zaženi** za obdelavo sprememb.

## <a name="exclude-merged-fields"></a>Izključevanje spojenih polj

Iz poenotenega profila stranke izključite atribut. Če se polje uporablja v drugih procesih, na primer v segmentu, ga odstranite iz teh procesov, preden ga izključite iz profila stranke. 

1. Izberite spojeno polje.
  
1. Izberite možnost **Pokaži več** in **Izključi**.

1. Potrdite izključitev.

1. Izberite možnost **Shrani** in **Zaženi** za obdelavo sprememb. 

Na strani za **spajanje** izberite **Izključena polja** za ogled seznama vseh izključenih polj. To podokno vam omogoča vnovično dodajanje izključenih polj.

## <a name="edit-a-merged-field"></a>Urejanje spojenega polja

1.  Izberite spojeno polje.

1.  Izberite možnost **Pokaži več** in **Uredi**.

1.  Določite, kako združiti ali spojiti polja z eno od treh možnosti:
    - **Pomembnost**: Določi zmagovalno vrednost na podlagi uvrstitve pomembnosti, določene za vključena polja. To je privzeta možnost spajanja. Izberite **Premakni gor/dol**, da določite razvrstitev pomembnosti.
    :::image type="content" source="media/importance-merge-option.png" alt-text="Možnost pomembnosti v dialogu za spajanje polj."::: 
    - **Najnovejše**: Določi zmagovalno vrednost na podlagi najnovejših. Zahteva datum ali številsko polje za vsako vključeno entiteto v obsegu spajanja polj za določitev nedavnosti.
    :::image type="content" source="media/recency-merge-option.png" alt-text="Možnost nedavnosti v dialogu za spajanje polj.":::
    - **Najstarejše**: Določi zmagovalno vrednost na podlagi najstarejših. Zahteva datum ali številsko polje za vsako vključeno entiteto v obsegu spajanja polj za določitev nedavnosti.

1.  Če želite sodelovati v postopku spajanja, lahko dodate več polj.

1.  Spojeno polje lahko preimenujete.

1. Če želite uporabiti spremembe, izberite **Dokončaj**.

1. Izberite možnost **Shrani** in **Zaženi** za obdelavo sprememb. 

## <a name="combine-fields-manually"></a>Ročno združi polja

Ročno določite spojeni atribut.

1. Na **Združi** stran, izberite **Združite**.

1. Izberite **Polja** možnost.

1. Pravilnik zmagovalnega spajanja določite v spustnem meniju **Združi polja glede na**.

1. Izberite polje, ki ga želite dodati. Izberite možnost **Dodaj polja**, če želite združiti več polj.

1. Navedite **Ime** in **Ime izhodnega polja**.

1. Če želite uporabiti spremembe, izberite **Dokončaj**.

1. Izberite možnost **Shrani** in **Zaženi** za obdelavo sprememb. 

## <a name="combine-a-group-of-fields"></a>Združite skupino polj

Skupino polj obravnavajte kot eno samo enoto. Na primer, če naši zapisi vsebujejo polja Naslov1, Naslov2, Mesto, Država in Zip. Verjetno se ne želimo združiti v naslov2 drugega zapisa, ker mislimo, da bi naši podatki postali popolnejši

1. Na **Združi** stran, izberite **Združite**.

1. Izberite **Skupina polj** možnost.

1. Določite politiko zmagovalca spajanja v **Razvrstite skupine po** spustni meni.

1. Izberite **Dodaj** in izberite, ali želite v polja dodati več polj ali dodatnih skupin.

1. Zagotovite a **ime** in an **Ime izhoda** za vsako kombinirano polje.

1. Zagotovite a **ime** za skupino polj. 

1. Če želite uporabiti spremembe, izberite **Dokončaj**.

1. Izberite možnost **Shrani** in **Zaženi** za obdelavo sprememb.

## <a name="change-the-order-of-fields"></a>Spreminjanje vrstnega reda polj

Nekatere entitete vsebujejo več podrobnosti kot druge. Če entiteta vključuje najnovejše podatke o polju, jo lahko pri spajanju vrednosti prednostno obravnavate pred drugimi entitetami.

1. Izberite spojeno polje.
  
1. Izberite možnost **Pokaži več** in **Uredi**.

1. V podoknu **Združevanje polj** izberite možnost **Premik gor/dol**, da nastavite vrstni red, ali pa jih povlecite in spustite na želeni položaj.

1. Potrdite spremembo.

1. Izberite možnost **Shrani** in **Zaženi** za obdelavo sprememb.

## <a name="configure-customer-id-generation"></a>Konfiguriranje generacije ID-ja stranke 

Ko konfigurirate polja za spajanje, lahko določite, kako ustvariti vrednosti CustomerId, edinstvene identifikatorje profila stranke. Korak spajanja v postopku poenotenja podatkov ustvari edinstven identifikator profila stranke. Identifikator je CustomerId v entiteti *Stranka*, ki je rezultat postopka poenotenja podatkov. 

CustomerId v entiteti Stranka temelji na razprševanju prve vrednosti primarnih zmagovalnih ključev, ki niso »null«. Ti ključi prihajajo iz entitet, uporabljenih v fazi ujemanja in spajanja, nanje pa vpliva vrstni red ujemanja.Tako se lahko ustvarjeni ID stranke spremeni, ko se vrednost primarnega ključa spremeni v primarni entiteti vrstnega reda ujemanja. Vrednost primarnega ključa morda ne predstavlja vedno iste stranke.

Če konfigurirate stabilen ID stranke, se lahko temu izognete.

**Konfiguriranje enoličnega ID-ja stranke**

1. Odprite razdelek **Poenotenje** > **Spoji**.

1. Izberite zavihek **Ključi**. 

1. Pomaknite se v vrstico **CustomerId** in izberite možnost **Konfiguriraj**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Kontrolnik za prilagoditev ID-ja generacije.":::

1. Izberite do pet polj, ki bodo vsebovala edinstven ID stranke in so bolj stabilna. Zapisi, ki se ne ujemajo z vašo konfiguracijo, namesto tega uporabljajo sistemsko konfiguriran ID.  

1. Izberite **Dokončaj** in zaženite postopek spajanja, da uporabite spremembe.

## <a name="group-profiles-into-households-or-clusters"></a>Združevanje profilov v gospodinjstva ali gruče

Kot del postopka konfiguracije ustvarjanja profila stranke lahko določite pravila za združevanje sorodnih profilov v gručo. Trenutno sta na voljo dve vrsti gruč – gospodinjska in po meri. Sistem samodejno izbere gospodinjstvo z vnaprej določenimi pravili, če entiteta *Stranka* vsebuje semantični polji *Person.LastName* in *Location.Address*. Ustvarite lahko tudi gručo z lastnimi pravili in pogoji, ki so podobni [pravilom za ujemanje](match-entities.md#define-rules-for-match-pairs).

**Določite gospodinjstvo ali gručo**

1. Odprite razdelek **Poenotenje** > **Spoji**.

1. V zavihku **Spoji** izberite **Napredno** > **Ustvari gručo**.

   :::image type="content" source="media/create-cluster.png" alt-text="Nadzor za ustvarjanje nove gruče.":::

1. Izberite med gručama **Gospodinjstvo** ali **Po meri**. Če semantični polji *Person.LastName* in *Location.Address* obstajata v entiteti *Stranka*, bo samodejno izbrano gospodinjstvo.

1. Vnesite ime za gručo in izberite **Končano**.

1. Izberite zavihek **Gruče**, da poiščete gručo, ki ste jo ustvarili.

1. Določite pravila in pogoje za opredelitev gruče.

1. Izberite **Zaženi**, da zaženete postopek spajanja in ustvarite gručo.

Po zagonu postopka spajanja se identifikatorji gruče dodajo kot nova polja v entiteto *Stranka*.

## <a name="run-your-merge"></a>Zagon spajanja

Ne glede na to, ali atribute spajate ročno ali jih spoji sistem, lahko vedno zaženete spajanje. Za začetek postopka izberite **Zaženi** na strani **Spajanje**.

> [!div class="mx-imgBorder"]
> ![Shranjevanje in zagon spajanja podatkov.](media/configure-data-merge-save-run.png "Shranjevanje in zagon spajanja podatkov")

Izberite možnost **Zaženi samo spajanje**, če želite, da se rezultat prikaže samo v poenoteni entiteti stranke. Procesi iz strežnika bodo osveženi, kot je [opredeljeno v načrtovanju osveževanja](system.md#schedule-tab).

Izberite možnost **Zaženi procese spajanja in procese iz strežnika**, da osvežite sistem s svojimi spremembami. Vsi procesi, vključno z obogatitvijo, segmenti in merami, se bodo samodejno ponovili. Po zaključku vseh procesov iz strežnika profili strank prikažejo vse spremembe, ki ste jih naredili.

Če želite narediti več sprememb in ponoviti korak, lahko prekličete spajanje v teku. Izberite **Osveževanje ...**, nato pa **Prekliči posel** v stranskem podoknu, ki se prikaže.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

:::image type="content" source="media/process-detail-path.png" alt-text="Pot do več podrobnosti o obdelavi s povezave do stanja opravila.":::

## <a name="next-step"></a>Naslednji korak

Za pridobitev več vpogledov v stranke konfigurirajte možnosti [Dejavnosti](activities.md), [Obogatitev](enrichment-hub.md) ali [Odnosi](relationships.md).

Če ste že konfigurirali dejavnosti, obogatitev ali segmente, bodo samodejno obdelani za uporabo najnovejših podatkov o strankah.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
