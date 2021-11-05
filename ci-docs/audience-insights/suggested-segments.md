---
title: Predlagani segmenti, ki jih omogoča strojno učenje
description: Naj vam strojno učenje pomaga pri iskanju novih in zanimivih segmentov, ki temeljijo na atributih strank.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 44e46bb650b6f090afcab3bc940d03a304e9c375
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673203"
---
# <a name="suggested-segments-preview"></a>Predlagani segmenti (predogled)

Odkrijte zanimive segmente svojih strank z modelom umetne inteligence. Funkcija, ki jo poganja strojno učenje, predlaga segmente, ki temeljijo na merah ali atributih strank. Lahko vam pomaga izboljšati KPI-je ali bolje razumeti vpliv atributov v zvezi z drugimi atributi. 

> [!NOTE]
> Funkcija predlaganja segmentov uporablja avtomatizirana sredstva za ocenjevanje podatkov in ustvarjanje predvidevanj na podlagi teh podatkov, zato se lahko uporablja kot način profiliranja, saj je ta izraz opredeljen v Splošni uredbi o varstvu podatkov (»GDPR«). Za uporabo te funkcije za obdelavo podatkov lahko veljajo načela splošne uredbe o varstvu podatkov ali drugi zakoni oz. predpisi. Odgovorni ste za zagotovitev, da je vaša uporaba storitve Dynamics 365 Customer Insights, vključno s to funkcijo, v skladu z vsemi veljavnimi zakoni in predpisi, vključno z zakoni v zvezi z zasebnostjo, osebnimi podatki, biometričnimi podatki, varstvom podatkov in zaupnostjo komunikacij.

:::image type="content" source="media/suggested-segments.png" alt-text="Stran s predlaganimi segmenti, ki prikazuje podrobnosti predloga v stranskem podoknu.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Predlagani segmenti za izboljšanje KPI-jev

Kot uporabnik vpogledov v ciljne skupine ste verjetno ustvarili [vrsto ukrepov](measures.md), ki pomagajo slediti vašim ključnim kazalnikom učinkovitosti (KPI-jem). Pomembno se je zavedati, kako določeni atributi vplivajo na ta KPI pri ustvarjanju segmentov in vodenju visoko ciljno usmerjene kampanje.   
Na primer: sledite meri, imenovani *SkupnaPorabaNaStranko*. Kot podjetje bi želeli, da to število narašča. Če izberete mero kot primarni atribut, lahko izberete atribute, za katere želite oceniti vpliv. Recimo *raven članstva*, *obdobje članstva* in *poklic*. Rešitev Customer Insights lahko nato predlaga segment, ki vam pove, na koga ta mera najbolj vpliva. Na primer: *Računovodje*, ki so *Zlati* člani in ki z vašim podjetjem sodelujejo *najmanj pet let* imajo največji vpliv na mero *SkupnaPorabaNaStranko*. Za vsak predlog boste prejeli ocenjeno velikost segmenta. Te podatke lahko uporabite za ustvarjanje kampanj za ciljno skupino.

## <a name="understand-what-influences-a-customer-attribute"></a>Razumevanje, kaj vpliva na atribut stranke

Kot primarni atribut lahko namesto mere uporabite atribut stranke. Na podlagi vaše izbire vplivnih atributov model umetne inteligence ustvari niz predlogov, ki prikazujejo, kako izbrani atributi vplivajo na primarni atribut.   
Za primarni atribut lahko na primer izberete *Član programa nagrajevanja (Da/Ne)*. Drugi vplivni atributi so *Delovna doba*, *Poklic* in *Število zahtev za podporo*. Model umetne inteligence lahko predlaga segmente, ki prikazujejo, da so predvsem strokovnjaki za IT z delovno dobo višjo od dveh let člani programa nagrajevanja. Predlaga lahko tudi, da so računovodje z delovno dobo višjo od enega leta in z manj kot tremi zahtevami za podporo člani programa nagrajevanja. 

## <a name="artificial-intelligence-usage"></a>Uporaba umetne inteligence

Algoritem odločitvenega drevesa predlaga zanimive segmente z uporabo primarnega atributa in vplivnih atributov. Predlogi temeljijo na pravilih ali vzorcih, ki jih je zaznal algoritem umetne inteligence. Kot predlogi so prikazani samo segmenti, ki se bistveno razlikujejo od povprečne populacije. Primerjava s povprečno populacijo temelji na izbrani meri ali primarnemu atributu.

### <a name="responsible-ai"></a>Odgovorna umetna inteligenca

Predlagani segmenti omogočajo izbiro atributov za ustvarjanje novih segmentov in obdelavo izbranih podatkov. Pri izbiri atributov, vključno z občutljivimi atributi, kot so rasa, spolna usmerjenost ali spol, morate zagotoviti, da podatke lahko in jih obdelujete. Odgovorni ste za spoštovanje vseh zakonov, ki veljajo za vašo organizacijo, ter spoštovanje načel in pravilnikov o zasebnosti vaše organizacije.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Različni rezultati za primarne atribute s kategoričnimi in številčnimi vrednostmi

Predlogi za segmente se razlikujejo, če za primarni atribut izberete številski ali kategorični atribut. Vrednosti v kategoričnem atributu vsebujejo dve ali več kategorij oz. vrst. Številski atribut vsebuje količinske podatke in ima občutek za merjenje.

Z numeričnim atributom, kot sta *letni dohodek* ali *obdobje članstva* kot primarni atribut, sistem predlaga segmente, ki imajo višjo ali nižjo povprečno vrednost numeričnega atributa v primerjavi z vsemi strankami.

Posledica kategoričnega atributa, kot je *zadovoljstvo strank* kot primarni atribut, so predlagani segmenti, ki imajo večji ali manjši odstotek strank, ki pripadajo določeni kategoriji, v primerjavi z odstotkom vseh strank, ki pripadajo isti kategoriji. na primer: kot primarni atribut je izbran atribut *zadovoljstvo strank*, ki je sestavljen iz treh kategorij (*Nizko*, *Srednje* in *Visoko*). Za vsako kategorijo bodo predlagani segmenti, ki imajo višji ali nižji odstotek strank, ki pripadajo tej kategoriji, v primerjavi z deležem vseh strank v isti kategoriji. Če je 22 % vseh strank *visoko* zadovoljnih, bodo za to kategorijo predlagani le segmenti, ki imajo večji ali manjši delež strank z *visokim* zadovoljstvom v primerjavi z 22 %. Za vsako drugo kategorijo (*Nizko* in *Srednje*) bodo na podoben način predlagani segmenti, če so statistično pomembni.

> [!NOTE]
> Trenutno podpiramo samo primarne kategorične atribute, ki imajo največ 10 kategorij. Če želite videti predloge za segmente, ki temeljijo na primarnem atributu z več kot 10 kategorijami, priporočamo, da nekatere kategorije razvrstite v skupine, da zmanjšate število kategorij na 10 ali manj. Ta omejitev velja samo za primarne atribute. Za vplivne kategorične atribute trenutno podpiramo največ 100 kategorij.

## <a name="generate-suggested-segments"></a>Ustvarjanje predlaganih segmentov

1. Izberite **Segmenti**.

1. Izberite zavihek **Predlogi (predogled)**.

1. Za vodeno izkušnjo izberite **Pridobivanje novih predlogov**.

1. Kot primarni atribut izberite mero ali atribut stranke in izberite **Naprej**.

   :::image type="content" source="media/suggested-segments-primary-attribute.png" alt-text="Izbira primarnega atributa za predloge na strani »Predlagani segmenti«.":::

1. Izberite vplivne atribute in izberite **Shrani**.
   
   > [!TIP]
   > Če izberete več vplivnih atributov, se izboljša možnost ocene, kako vplivajo na primarni atribut. Ne vključujte atributov, ki nimajo vpliva na primarni atribut. Če so na primer vse vaše stranke iz določene države, ne vključite atributa *država*, ker to ne bo vplivalo na rezultat.

1. Glede na število profilov strank in izbrane atribute lahko traja nekaj minut, da obdelamo izbrane atribute. 

## <a name="view-details-of-a-suggested-segment"></a>Ogled podrobnosti predlaganega segmenta

Ko bo model umetne inteligence ustvaril predloge, jih boste našli na seznamu **Segmenti** > **Predlogi (predogled)**.
 
Izberite predlagani segment, če želite pregledati podrobnosti tega predloga. Prav tako lahko pregledate vrednosti ali pravila atributov, ki se jih je model umetne inteligence naučil za predlaganje izbranega segmenta.

## <a name="save-a-suggestion-as-a-segment"></a>Shranjevanje predloga kot segmenta

1. Odprite **Segmenti** > **Predlogi (predogled)**.

1. Izberite segment, ki ga želite shraniti. 

1. V stranskem podoknu izberite **Shrani kot segment**. 

1. Po shranjevanju segmenta se bo prikazal na seznamu segmentov na zavihku **Vsi segmenti**. Zdaj ga je mogoče [osvežiti, urediti ali izbrisati kot kateri koli drug segment](segments.md).

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Osvežitev ali urejanje niza segmentov

1. Odprite **Segmenti** > **Predlogi (predogled)**.

1. Izberite **Osveži predloge**, da osvežite predloge in obdržite konfigurirane atribute. Ali pa izberite **Uredi atribute**, da spremenite konfigurirane atribute. Sistem bo znova zagnal model umetne inteligence, ustvaril predloge za segmente na podlagi najnovejših podatkov in nadomestil trenutne predloge.

## <a name="limitations"></a>Omejitve

1. Neujemanje ocenjene velikosti segmenta: če izberete primarni atribut, ki vsebuje prazne vrednosti, lahko to vpliva na ocenjeno velikost segmenta v predlogih za segmente. Pri shranjevanju takega segmenta se lahko dejanska velikost segmenta razlikuje od prvotne ocene.
 
2. Primarni atributi logične vrste ne delujejo: trenutno kot primarni atribut podpiramo samo niz in številske vrste podatkov.

3. Predlagani segmenti niso dovolj različni: upoštevajte, da izbrani atributi in porazdelitev vrednosti teh atributov vplivajo na rezultate. Spremenite lahko vplivne atribute ali celo primarni atribut, da dobite drugačne rezultate.



[!INCLUDE[footer-include](../includes/footer-banner.md)]