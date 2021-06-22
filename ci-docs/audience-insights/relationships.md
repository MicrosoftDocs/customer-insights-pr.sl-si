---
title: Odnosi med entitetami in poti entitet
description: Ustvarite in upravljajte odnose med entitetami iz več virov podatkov.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171184"
---
# <a name="relationships-between-entities"></a>Odnosi med entitetami

Odnosi povezujejo entitete in definirajo graf vaših podatkov, ko imajo entitete skupni identifikator, tj. tuji ključ. Ta tuji ključ se lahko sklicuje od ene entitete na drugo. Povezane entitete omogočajo določitev segmentov in ukrepov na podlagi več virov podatkov.

Obstajajo tri vrste odnosov: 
- Sistemski odnosi, ki jih ni mogoče urejati in jih je ustvaril sistem kot del postopka za poenotenje podatkov
- Podedovani odnosi, ki jih ni mogoče urejati in se samodejno ustvarijo iz vnesenih virov podatkov 
- Odnosi po meri, ki jih je mogoče urejati in jih ustvarjajo in konfigurirajo uporabniki

## <a name="non-editable-system-relationships"></a>Sistemski odnosi, ki jih ni mogoče urejati

Med poenotenjem podatkov se sistemski odnosi samodejno ustvarijo na podlagi pametnega ujemanja. Ti odnosi pomagajo povezati zapise profila stranke z ustreznimi zapisi. Naslednji diagram prikazuje ustvarjanje treh sistemskih odnosov. Entiteto stranke se poveže z drugimi entitetami, da se ustvari poenotena entiteta *Stranka*.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagram s potmi odnosov za entiteto stranke s tremi odnosi 1-n.":::

- **Odnos *CustomerToContact*** je bil ustvarjen med entiteto *Stranka* in entiteto *Stik*. Za entiteto *Stranka* se uporabi polje ključa Contact_ **contactId** za povezovanje s poljem ključa entitete *Stik* **contactID**.
- **Odnos *CustomerToAccount*** je bil ustvarjen med entiteto *Stranka* in entiteto *Kupec*. Za entiteto *Stranka* se uporabi polje ključa Account_ **accountID** za povezovanje s poljem ključa entitete *Kupec* **accountID**.
- **Odnos *CustomerToWebAccount*** je bil ustvarjen med entiteto *Stranka* in entiteto *WebAccount*. Za entiteto *Stranka* se uporabi polje ključa **WebAccount_webaccountID** za povezovanje s poljem ključa entitete *WebAccount* **webaccountID**.

## <a name="non-editable-inherited-relationships"></a>Podedovani odnosi, ki jih ni mogoče urejati

Med postopkom vnosa podatkov sistem preveri obstoječe odnose za vire podatkov. Če odnosi ne obstajajo, jih sistem samodejno ustvari. Ti odnosi se uporabljajo tudi v nadaljnjih postopkih.

## <a name="create-a-custom-relationship"></a>Ustvarjanje odnosa po meri

Odnos je sestavljen iz *izvorne entitete*, ki vsebuje tuji ključ, in *ciljne entitete*, na katero kaže tuji ključ izvorne entitete. 

1. Pri vpogledih v občinstvo izberite **Podatki** > **Odnosi**.

2. Izberite **Nov odnos**.

3. V podokno **Nov odnos** vnesite te podatke:

   :::image type="content" source="media/relationship-add.png" alt-text="Podokno za nov odnos s praznimi vnosnimi polji.":::

   - **Ime odnosa**: ime, ki odraža namen odnosa. Primer: CustomerToSupportCase.
   - **Opis**: opis odnosa.
   - **Izvorna entiteta**: entiteta, ki se v odnosu uporablja kot vir. Primer: SupportCase.
   - **Ciljna entiteta**: entiteta, ki se v odnosu uporablja kot cilj. Primer: Stranka.
   - **Kardinalnost vira**: določa kardinalnost izvorne entitete. Kardinalnost opisuje število možnih elementov v naboru. Navezuje se na ciljno kardinalnost. Izbirate lahko med **Ena** in **Mnogo**. Podprti so samo odnosi »mnogo proti ena« in »ena proti ena«.  
     - Mnogo proti ena: več izvornih zapisov se lahko nanaša na en ciljni zapis. Primer: več primerov za podporo iz ene stranke.
     - Ena proti ena: posamezen izvorni zapis se nanaša na en ciljni zapis. Primer: en ID zvestobe za eno stranko.

     > [!NOTE]
     > Odnose »mnogo proti mnogo« je mogoče ustvariti z dvema odnosoma »mnogo proti ena« in povezovalno entiteto, ki povezuje izvorno entiteto in ciljno entiteto.

   - **Kardinalnost cilja**: izberite kardinalnost zapisov ciljne entitete. 
   - **Polje izvornega ključa**: polje tujega ključa v izvorni entiteti. Primer: SupportCase bi lahko uporabil CaseID kot polje tujega ključa.
   - **Ciljno polje ključa**: polje ključa ciljne entitete. Primer, kjer bi lahko Stranka uporabila polje ključa **CustomerID**.

4. Izberite možnost **Shrani**, da ustvarite odnos po meri.

## <a name="view-relationships"></a>Ogled odnosov

Na strani Odnosi so navedeni vsi ustvarjeni odnosi. Vsaka vrstica predstavlja odnos, ki vključuje tudi podrobnosti o izvorni entiteti, ciljni entiteti in kardinalnosti. 

:::image type="content" source="media/relationships-list.png" alt-text="Seznam odnosov in možnosti v orodni vrstici strani Odnosi.":::

Ta stran ponuja nabor možnosti za obstoječe in nove odnose: 
- **Nov odnos**: [Ustvari odnos po meri](#create-a-custom-relationship).
- **Vizualizator**: [Raziščite vizualizator odnosov](#explore-the-relationship-visualizer), da si ogledate omrežni diagram obstoječih odnosov in njihovo kardinalnost.
- **Filtriraj po**: izberite vrsto odnosov, ki naj se prikažejo na seznamu.
- **Iskanje odnosov**: za iskanje lastnosti odnosov uporabite iskanje na podlagi besedila.

### <a name="explore-the-relationship-visualizer"></a>Raziščite vizualizator odnosov

Vizualizator odnosov prikazuje omrežni diagram obstoječih odnosov med povezanimi entitetami in njihovo kardinalnost.

Če želite prilagoditi pogled, lahko spremenite položaj polj tako, da jih povlečete na platno.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Posnetek zaslona omrežnega diagrama vizualizatorja odnosov s povezavami med povezanimi entitetami.":::

Razpoložljive možnosti: 
- **Izvozi kot sliko**: shranite trenutni pogled kot slikovno datoteko.
- **Spremeni v vodoravno/navpično postavitev**: spremenite poravnavo entitet in odnosov.
- **Uredi**: posodobite lastnosti odnosov po meri v podoknu za urejanje in shranite spremembe.

## <a name="manage-existing-relationships"></a>Upravljanje obstoječih odnosov 

Na strani Odnosi vsak odnos predstavlja ena vrstica. 

Izberite odnos in eno od naslednjih možnosti: 
 
- **Uredi**: posodobite lastnosti odnosov po meri v podoknu za urejanje in shranite spremembe.
- **Izbriši**: izbrišite odnos po meri.
- **Pogled**: oglejte si sistemsko ustvarjene in podedovane odnose. 

## <a name="next-step"></a>Naslednji korak

Sistemski odnosi in odnosi po meri se uporabljajo za [ustvarjanje segmentov](segments.md) na podlagi več virov podatkov, ki niso več ločeni.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
