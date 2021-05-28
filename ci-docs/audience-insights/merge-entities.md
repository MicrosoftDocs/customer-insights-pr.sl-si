---
title: Združevanje entitet za poenotenje podatkov
description: Združite entitete za ustvarjanje poenotenih profilov strank.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2cab702509596dd87c0c9b9769d1af8ba8387f9d
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085596"
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

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Možnosti v spustnem meniju Pokaži več za upravljanje spojenih atributov.":::

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

## <a name="manually-combine-fields"></a>Ročno združevanje polj

Ročno določite spojeni atribut. 

1. Na strani za **spajanje** izberite možnost **Združi polja**.

1. Navedite **Ime** in **Ime izhodnega polja**.

1. Izberite polje, ki ga želite dodati. Izberite možnost **Dodaj polja**, če želite združiti več polj.

1. Potrdite izključitev.

1. Izberite možnost **Shrani** in **Zaženi** za obdelavo sprememb. 

## <a name="change-the-order-of-fields"></a>Spreminjanje vrstnega reda polj

Nekatere entitete vsebujejo več podrobnosti kot druge. Če entiteta vključuje najnovejše podatke o polju, jo lahko pri spajanju vrednosti prednostno obravnavate pred drugimi entitetami.

1. Izberite spojeno polje.
  
1. Izberite možnost **Pokaži več** in **Uredi**.

1. V podoknu **Združevanje polj** izberite možnost **Premik gor/dol**, da nastavite vrstni red, ali pa jih povlecite in spustite na želeni položaj.

1. Potrdite spremembo.

1. Izberite možnost **Shrani** in **Zaženi** za obdelavo sprememb.

## <a name="run-your-merge"></a>Zagon spajanja

Ne glede na to, ali atribute spajate ročno ali jih spoji sistem, lahko vedno zaženete spajanje. Za začetek postopka izberite **Zaženi** na strani **Spajanje**.

> [!div class="mx-imgBorder"]
> ![Shranjevanje in zagon spajanja podatkov](media/configure-data-merge-save-run.png "Shranjevanje in zagon spajanja podatkov")

Izberite možnost **Zaženi samo spajanje**, če želite, da se rezultat prikaže samo v poenoteni entiteti stranke. Procesi iz strežnika bodo osveženi, kot je [opredeljeno v načrtovanju osveževanja](system.md#schedule-tab).

Izberite možnost **Zaženi procese spajanja in procese iz strežnika**, da osvežite sistem s svojimi spremembami. Vsi procesi, vključno z obogatitvijo, segmenti in merami, se bodo samodejno ponovili. Po zaključku vseh procesov iz strežnika profili strank prikažejo vse spremembe, ki ste jih naredili.

Če želite narediti več sprememb in ponoviti korak, lahko prekličete spajanje v teku. Izberite **Osveževanje ...**, nato pa **Prekliči posel** v stranskem podoknu, ki se prikaže.

> [!TIP]
> Na voljo je [šest vrst stanja](system.md#status-types) za opravila/postopke. Poleg tega je večina postopkov [odvisna od drugih nadaljnjih postopkov](system.md#refresh-policies). Izberete lahko stanje postopka in si ogledate podrobnosti o poteku celotnega posla. Ko za enega izmed poslov izberete **Prikaži podrobnosti**, se prikažejo dodatne informacije: čas obdelave, zadnji datum obdelave ter vse napake in opozorila, povezana z opravilom.

## <a name="next-step"></a>Naslednji korak

Za pridobitev več vpogledov v stranke konfigurirajte možnosti [Dejavnosti](activities.md), [Obogatitev](enrichment-hub.md) ali [Odnosi](relationships.md).

Če ste že konfigurirali dejavnosti, obogatitev ali segmente, bodo samodejno obdelani za uporabo najnovejših podatkov o strankah.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
