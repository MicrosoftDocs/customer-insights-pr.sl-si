---
title: Predlagani segmenti na podlagi mer (predogled)
description: Naj vam strojno učenje pomaga pri iskanju novih in zanimivih segmentov, ki temeljijo na atributih strank.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: e3f504827029afa12c65ec6f065a62606aaa823f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170977"
---
# <a name="suggested-segments-based-on-measures-preview"></a>Predlagani segmenti na podlagi mer (predogled)

Odkrijte zanimive segmente svojih strank z modelom umetne inteligence. Funkcija, ki jo poganja strojno učenje, predlaga segmente, ki temeljijo na merah ali atributih strank. Pomaga lahko izboljšati vaše ključne kazalnike uspešnosti (KPI) ali bolje razumeti vpliv atributov v kontekstu drugih atributov.

> [!NOTE]
> Funkcija predlaganih segmentov uporablja avtomatizirana sredstva za ocenjevanje podatkov in izdelavo napovedi na podlagi teh podatkov. Zato se lahko uporablja kot metoda profiliranja, kot je ta izraz opredeljen v Splošni uredbi o varstvu podatkov (»GDPR«). Za uporabo te funkcije za obdelavo podatkov lahko veljajo načela splošne uredbe o varstvu podatkov ali drugi zakoni oz. predpisi. Odgovorni ste za zagotovitev, da je vaša uporaba storitve Dynamics 365 Customer Insights, vključno s to funkcijo, v skladu z vsemi veljavnimi zakoni in predpisi, vključno z zakoni v zvezi z zasebnostjo, osebnimi podatki, biometričnimi podatki, varstvom podatkov in zaupnostjo komunikacij.

:::image type="content" source="media/suggested-segments.png" alt-text="Stran s predlaganimi segmenti, ki prikazuje podrobnosti predloga v stranskem podoknu.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Predlagani segmenti za izboljšanje KPI-jev

Če uporabljate [ustvarjenih ukrepov](measures.md) za lažje sledenje vašim KPI-jem ustvarite segmente za ogled vplivov na KPI-je. Te informacije lahko uporabite za vodenje visoko ciljane kampanje.

Na primer: sledite meri, imenovani *SkupnaPorabaNaStranko*. Kot podjetje bi želeli, da to število narašča. Ko izberete merilo kot primarni atribut, izberite atribute, za katere želite oceniti vpliv. Recimo *raven članstva*, *obdobje članstva* in *poklic*. Rešitev Customer Insights lahko nato predlaga segment, ki vam pove, na koga ta mera najbolj vpliva. Na primer: *Računovodje*, ki so *Zlati* člani in ki z vašim podjetjem sodelujejo *najmanj pet let* imajo največji vpliv na mero *SkupnaPorabaNaStranko*. Za vsak predlog boste prejeli ocenjeno velikost segmenta. Te podatke lahko uporabite za ustvarjanje kampanj za ciljno skupino.

## <a name="understand-what-influences-a-customer-attribute"></a>Razumevanje, kaj vpliva na atribut stranke

Kot primarni atribut lahko namesto mere uporabite atribut stranke. Na podlagi vaše izbire vplivnih atributov model umetne inteligence ustvari niz predlogov, ki prikazujejo, kako izbrani atributi vplivajo na primarni atribut.

Za primarni atribut lahko na primer izberete *Član programa nagrajevanja (Da/Ne)*. Drugi vplivni atributi so *Delovna doba*, *Poklic* in *Število zahtev za podporo*. Model umetne inteligence lahko predlaga segmente, ki prikazujejo, da so predvsem strokovnjaki za IT z delovno dobo višjo od dveh let člani programa nagrajevanja. Predlaga lahko tudi, da so računovodje z delovno dobo višjo od enega leta in z manj kot tremi zahtevami za podporo člani programa nagrajevanja.

## <a name="artificial-intelligence-usage"></a>Uporaba umetne inteligence

Algoritem odločitvenega drevesa predlaga zanimive segmente z uporabo primarnega atributa in vplivnih atributov. Predlogi temeljijo na pravilih ali vzorcih, ki jih je zaznal algoritem umetne inteligence. Kot predlogi so prikazani samo segmenti, ki se bistveno razlikujejo od povprečne populacije. Primerjava s povprečno populacijo temelji na izbrani meri ali primarnemu atributu.

### <a name="responsible-ai"></a>Odgovorna umetna inteligenca

S predlaganimi segmenti izberete atribute za ustvarjanje novih segmentov in obdelavo izbranih podatkov. Pri izbiri atributov, vključno z občutljivimi atributi, kot so rasa, spolna usmerjenost ali spol, morate zagotoviti, da podatke lahko in jih obdelujete. Odgovorni ste za spoštovanje vseh zakonov, ki veljajo za vašo organizacijo, ter spoštovanje načel in pravilnikov o zasebnosti vaše organizacije.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Različni rezultati za primarne atribute s kategoričnimi in številčnimi vrednostmi

Predlogi za segmente se razlikujejo, če za primarni atribut izberete številski ali kategorični atribut. Vrednosti v kategoričnem atributu vsebujejo dve ali več kategorij oz. vrst. Številski atribut vsebuje količinske podatke in ima občutek za merjenje.

Z numeričnim atributom, kot sta *letni dohodek* ali *obdobje članstva* kot primarni atribut, sistem predlaga segmente, ki imajo višjo ali nižjo povprečno vrednost numeričnega atributa v primerjavi z vsemi strankami.

Posledica kategoričnega atributa, kot je *zadovoljstvo strank* kot primarni atribut, so predlagani segmenti, ki imajo večji ali manjši odstotek strank, ki pripadajo določeni kategoriji, v primerjavi z odstotkom vseh strank, ki pripadajo isti kategoriji. na primer: kot primarni atribut je izbran atribut *zadovoljstvo strank*, ki je sestavljen iz treh kategorij (*Nizko*, *Srednje* in *Visoko*). Za vsako kategorijo bodo predlagani segmenti, ki imajo višji ali nižji odstotek strank, ki pripadajo tej kategoriji, v primerjavi z deležem vseh strank v isti kategoriji. Če je 22 % vseh strank *visoko* zadovoljnih, bodo za to kategorijo predlagani le segmenti, ki imajo večji ali manjši delež strank z *visokim* zadovoljstvom v primerjavi z 22 %. Za vsako drugo kategorijo (*Nizko* in *Srednje*) bodo na podoben način predlagani segmenti, če so statistično pomembni.

> [!NOTE]
> Trenutno podpiramo samo primarne kategorične atribute, ki imajo največ 10 kategorij. Če želite videti predloge segmentov, ki temeljijo na primarnem atributu z več kot 10 kategorijami, priporočamo, da nekatere kategorije združite v skupine, da zmanjšate število kategorij na 10 ali manj. Ta omejitev velja samo za primarne atribute. Za vplivne kategorične atribute trenutno podpiramo največ 100 kategorij.

## <a name="generate-suggested-segments"></a>Ustvarjanje predlaganih segmentov

1. Pojdi do **Segmenti** in izberite **Predlogi (predogled)** zavihek.

1. Izberite **Poiščite nove predloge** in izberite **Izboljšajte mero/metriko**. Izberite **Začetek**.

   :::image type="content" source="media/suggested-segments-measure.png" alt-text="Izbira ukrepa izboljšanja na predlaganih segmentih.":::

1. Izberite atribut stranke ali mero kot primarni atribut in izberite **Naslednji**.

1. Izberite vplivne atribute in izberite **Teči**.

   > [!TIP]
   > Če izberete več vplivnih atributov, se izboljša možnost ocene, kako vplivajo na primarni atribut. Ne vključite atributov, ki nimajo vpliva na primarni atribut. Če so na primer vse vaše stranke iz določene države, ne vključite atributa *država*, ker to ne bo vplivalo na rezultat.

Glede na število profilov strank in izbrane atribute lahko traja nekaj minut, da obdelamo izbrane atribute.

## <a name="manage-suggested-segments"></a>Upravljajte predlagane segmente

Pojdi do **Segmenti** in izberite **Predlogi (predogled)** zavihek. V **Predlogi segmentov na podlagi atributov** izberite predlagani segment za ogled razpoložljivih dejanj.

- **Pogled** predlagane podrobnosti segmenta in vrednosti atributov ali pravila, ki se jih je naučil model AI.
- **Shrani kot segment** predlog kot segment. Prikaže se na **Vsi segmenti** zavihek in lahko [osveženo, urejeno ali izbrisano](segments.md).
- **Uredi atribute** in spremenite konfigurirane atribute, ki bodo nadomestili trenutne predloge.
- **Osveži predloge** da osvežite predloge, medtem ko ohranite konfigurirane atribute.

## <a name="limitations"></a>Omejitve

1. Neujemanje ocenjene velikosti segmenta: če izberete primarni atribut, ki vsebuje prazne vrednosti, lahko to vpliva na ocenjeno velikost segmenta v predlogih za segmente. Pri shranjevanju takega segmenta se lahko dejanska velikost segmenta razlikuje od prvotne ocene.

2. Primarni atributi logične vrste ne delujejo: trenutno kot primarni atribut podpiramo samo niz in številske vrste podatkov.

3. Predlagani segmenti niso dovolj različni: upoštevajte, da izbrani atributi in porazdelitev vrednosti teh atributov vplivajo na rezultate. Spremenite lahko vplivne atribute ali celo primarni atribut, da dobite drugačne rezultate.

[!INCLUDE [footer-include](includes/footer-banner.md)]