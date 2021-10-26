---
title: Dejavnosti stranke
description: Določitev dejavnosti strank in njihov ogled v časovnici v profilih strank.
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: c250efcd54ec126c0726b22a971cdedd89760d6b
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617989"
---
# <a name="customer-activities"></a>Dejavnosti stranke

Združite dejavnosti strank iz [različnih virov podatkov](data-sources.md) v rešitvi Dynamics 365 Customer Insights, da ustvarite časovnico, ki dejavnosti našteva v časovnem zaporedju. V aplikacijah Dynamics 365 vključite časovnico z rešitvijo [Dodatek za kartico stranke](customer-card-add-in.md) ali v nadzorni plošči storitve Power BI.

## <a name="define-an-activity"></a>Določanje dejavnosti

Vaši viri podatkov lahko vključujejo entitete s transakcijskimi podatki in podatki o dejavnosti iz več virov podatkov. Določite te entitete in izberite časovnice, ki si jih želite ogledati na časovnici stranke. Izberite entiteto, ki vključuje vašo ciljno dejavnost ali dejavnosti.

Entiteta mora imeti vsaj en atribut vrste **Datum**, da je lahko vključena na časovnico stranke, vi pa ne morete dodajati entitet brez polja **Datum**. Ukaz **Dodaj dejavnost** je onemogočen, če take entitete ni mogoče najti.

1. Pri vpogledih v občinstvo izberite **Podatki** > **Dejavnosti**.

1. Izberite možnost **Dodaj dejavnost**, da se začne vodena izkušnja za postopek nastavitve dejavnosti.

1. V koraku **Podatki o dejavnosti** nastavite vrednosti za naslednja polja:

   - **Ime dejavnosti**: izberite ime dejavnosti.
   - **Entiteta**: izberite entiteto, ki vključuje transakcijske podatke ali podatke o dejavnosti.
   - **Primarni ključ**: izberite polje, ki edinstveno določi zapis. Ne sme vsebovati podvojenih, praznih ali manjkajočih vrednosti.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Nastavite podatke o dejavnosti za ime, entiteto in primarni ključ.":::

1. Izberite možnost **Naprej** za pomik na naslednji korak.

1. V koraku **Odnos** konfigurirajte podrobnosti za povezavo vaših podatkov o dejavnosti z ustreznimi zapisi stranke. V koraku so upodobljene povezave med entitetami.  

   - **Prvič**: tuje polje v entiteti dejavnosti, ki bo uporabljeno za vzpostavitev odnosa z drugo entiteto.
   - **Drugič**: ustrezna izvorna entiteta stranke, s katero bo entiteta dejavnosti v odnosu. Nanašate se lahko samo na izvorne entitete strank, ki se uporabljajo v postopku poenotenja podatkov.
   - **Tretjič**: če odnos med to entiteto dejavnosti in izbrano izvorno entiteto stranke že obstaja, bo ime odnosa v načinu samo za branje. Če takšen odnos ni na voljo, bo na podlagi imena, ki ste ga navedli v tem polju, ustvarjen nov.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Določite odnos entitete.":::

   > [!TIP]
   > V okoljih B2B lahko izbirate med entitetami računa in drugimi entitetami. Če izberete entiteto računa, se pot odnosa samodejno nastavi. Za druge entitete morate določiti pot odnosa do ene ali več vmesnih entitet, dokler ne dosežete entitete računa.

1. Izberite možnost **Naprej** za pomik na naslednji korak. 

1. V koraku **Poenotenje dejavnosti** izberite dogodek dejavnosti in čas začetka dejavnosti. 
   - **Zahtevana polja**
      - **Dejavnost dogodka**: polje, ki predstavlja dogodek za to dejavnost.
      - **Časovni žig**: polje, ki predstavlja čas začetka dejavnosti.

   - **Izbirna polja**
      - **Dodatne podrobnosti**: polje z relevantnimi informacijami za to dejavnost.
      - **Ikona**: ikona, ki najbolje predstavlja to vrsto dejavnosti.
      - **Spletni naslov** : polje z URL-jem s podatki o tej dejavnosti. Na primer transakcijski sistem, ki je vir te dejavnosti. Ta URL je lahko katero koli polje iz vira podatkov, lahko pa je oblikovano kot novo polje s pretvorbo v orodju Power Query. Podatki z URL-ja bodo shranjeni v entiteti *Poenotena dejavnost*, ki se lahko porabi v nadaljnjem toku z uporabo [API-jev](apis.md).

   - **Pokaži na časovnici**
      - Izberite, če želite to dejavnost pokazati v pogledu časovnice vaših profilov strank. Izberite **Da** za prikaz dejavnosti v časovnici ali **Ne**, da jih skrijete.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="V entiteti Poenotena dejavnost navedite podatke o dejavnosti stranke.":::

1. Izberite možnost **Naprej** za pomik na naslednji korak. Izberete lahko možnost **Zaključek in pregled**, da takoj shranite dejavnost z vrsto dejavnosti, nastavljeno na možnost **Drugo**. 

1. V koraku **Vrsta dejavnosti** izberite vrsto dejavnosti in po želji izberite, ali želite semantično preslikati nekatere vrste dejavnosti za uporabo na drugih področjih storitve Customer Insights. Po potrditvi, da se strinjate s preslikavo polj, je mogoče vrste dejavnosti *Povratne informacije*, *Zvestoba*, *SalesOrder*, *SalesOrderLine* in *Naročnina* semantično preslikati. Če vrsta dejavnosti za novo dejavnost ni pomembna, lahko izberete možnost *Drugo* ali *Ustvari novo* za prilagojeno vrsto dejavnosti.

1. Izberite možnost **Naprej** za pomik na naslednji korak. 

1. V koraku **Pregled** preverite svoje izbire. Vrnite se na kateregakoli izmed prejšnjih korakov in posodobite podatke, če je to potrebno.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Preglejte navedena polja za dejavnost.":::
   
1. Izberite možnost **Shrani dejavnost** za uporabo sprememb in izberite možnost **Končano**, da se vrnete v razdelek **Podatki** > **Dejavnosti**. Tukaj vidite, katere dejavnosti so nastavljene za prikaz na časovnici. 

1. Za obdelavo dejavnosti na strani **Dejavnosti** izberite možnost **Zaženi**. 

> [!TIP]
> Na voljo je [šest vrst stanja](system.md#status-types) za opravila/postopke. Poleg tega je večina postopkov [odvisna od drugih nadaljnjih postopkov](system.md#refresh-policies). Izberete lahko stanje postopka in si ogledate podrobnosti o poteku celotnega posla. Ko za enega izmed poslov izberete **Prikaži podrobnosti**, se prikažejo dodatne informacije: čas obdelave, zadnji datum obdelave ter vse napake in opozorila, povezana z opravilom.


## <a name="manage-existing-activities"></a>Upravljanje obstoječih dejavnosti

V razdelku **Podatki** > **Dejavnosti** si lahko ogledate vse shranjene dejavnosti in jih upravljate. Vsaka dejavnost je predstavljena z vrstico, ki vključuje tudi podrobnosti o viru, entiteti in vrsti dejavnosti.

Ko izberete dejavnost, so na voljo naslednja dejanja. 

- **Uredi**: odpre korak nastavitve dejavnosti v koraku pregleda. V tem koraku lahko spremenite vse trenutne konfiguracije. Po spremembi konfiguracije izberite možnost **Shrani dejavnost** in nato izberite možnost **Zaženi** za obdelavo sprememb.

- **Preimenujte**: odpre pogovorno okno, kamor lahko za izbrano dejavnost vnesete drugačno poimenovanje. Če želite uporabiti spremembe, izberite **Shrani**.

- **Izbriši**: odpre pogovorno okno za potrditev brisanja izbrane dejavnosti. Izbrišete lahko tudi več dejavnosti hkrati, in sicer tako, da izberete dejavnosti ter nato izberete ikono za brisanje. Izberite možnost **Izbriši**, da pordite izbris.

## <a name="view-activity-timelines-on-customer-profiles"></a>Ogled časovnic dejavnosti v profilih strank

Ko konfigurirate dejavnosti strank, izberite **Prikaz na časovnici dejavnosti** v konfiguraciji dejavnosti poiščite vse dejavnosti vaših strank na njihovem profilu stranke.

Če želite odpreti časovnico za stranko, odprite razdelek **Stranke** in izberite profil stranke, ki si ga želite ogledati.

Če je stranka sodelovala pri dejavnosti, ki ste jo konfigurirali, jo boste našli v razdelku **Časovnica dejavnosti**.

:::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Oglejte si konfigurirane dejavnosti v profilih strank.":::

Na časovnici dejavnosti lahko filtrirate dejavnosti na več načinov:

- Izberete lahko eno ali več ikon dejavnosti, da izboljšate svoje rezultate in vključite samo izbrane vrste.

  :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtrirajte dejavnosti po vrstah z uporabo ikon.":::

- Izberete lahko **filter**, da odprete ploščo filtrov in nastavite filtre časovnice.

   1. Filtrirate lahko po *vrsti dejavnosti* in *datumu*
   1. Izberite možnost **Uporabi**, da uporabite filtre na časovnici dejavnosti.

   :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="S ploščo filtrov konfigurirajte pogoje filtra.":::

Če želite odstraniti filtre, izberite možnost **x** poleg vsakega filtra, uporabljenega na časovnici, ali izberite možnost **Počisti filtre**.


> [!NOTE]
> Filtri dejavnosti se odstranijo, ko zapustite profil stranke. Uporabiti jih morate vsakič, ko odprete profil stranke.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
