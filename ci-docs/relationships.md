---
title: Odnosi med entitetami in poti entitet
description: Ustvarite in upravljajte odnose med entitetami iz več virov podatkov.
ms.date: 09/27/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-entities
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segments
- ci-segment-builder
- ci-measure-builder
- ci-measure-template
- ci-permissions
- customerInsights
ms.openlocfilehash: e622e5fa0b5738e31db1c668d95312adbc4f7d36
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183592"
---
# <a name="relationships-between-entities-and-entity-paths"></a>Odnosi med entitetami in poti entitet

Odnosi povezujejo entitete in definirajo graf vaših podatkov, ko imajo entitete skupni identifikator, tj. tuji ključ. Ta tuji ključ se lahko sklicuje od ene entitete na drugo. Povezane entitete omogočajo določitev segmentov in ukrepov na podlagi več virov podatkov.

Obstajajo tri vrste odnosov: 
- Sistem brez možnosti urejanja Odnosi ustvari sistem kot del procesa poenotenja podatkov
- Podedovani Odnosi, ki jih ni mogoče urejati, so samodejno ustvarjeni iz podatkovnih virov
- Odnosi po meri, ki jih je mogoče urejati, ustvarijo in konfigurirajo uporabniki

## <a name="non-editable-system-relationships"></a>Sistemski odnosi, ki jih ni mogoče urejati

Med poenotenjem podatkov se sistemski odnosi samodejno ustvarijo na podlagi pametnega ujemanja. Ti odnosi pomagajo povezati zapise profila stranke z ustreznimi zapisi. Naslednji diagram prikazuje ustvarjanje treh sistemskih odnosov. Entiteto stranke se poveže z drugimi entitetami, da se ustvari poenotena entiteta *Stranka*.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagram s potmi odnosov za entiteto stranke s tremi odnosi 1-n.":::

- **Odnos *CustomerToContact*** je bil ustvarjen med entiteto *Stranka* in entiteto *Stik*. Za entiteto *Stranka* se uporabi polje ključa **Contact_contactId** za povezovanje s poljem ključa entitete *Stik* **contactID**.
- **Odnos *CustomerToAccount*** je bil ustvarjen med entiteto *Stranka* in entiteto *Kupec*. Za entiteto *Stranka* se uporabi polje ključa **Account_accountID** za povezovanje s poljem ključa entitete *Kupec* **accountID**.
- **Odnos *CustomerToWebAccount*** je bil ustvarjen med entiteto *Stranka* in entiteto *WebAccount*. Za entiteto *Stranka* se uporabi polje ključa **WebAccount_webaccountID** za povezovanje s poljem ključa entitete *WebAccount* **webaccountID**.

## <a name="non-editable-inherited-relationships"></a>Podedovani odnosi, ki jih ni mogoče urejati

Med postopkom vnosa podatkov sistem preveri obstoječe odnose za vire podatkov. Če odnosi ne obstajajo, jih sistem samodejno ustvari. Ti odnosi se uporabljajo tudi v nadaljnjih postopkih.

## <a name="create-a-custom-relationship"></a>Ustvarjanje odnosa po meri

Odnos je sestavljen iz *izvorne entitete*, ki vsebuje tuji ključ, in *ciljne entitete*, na katero kaže tuji ključ izvorne entitete. 

1. Odprite razdelek **Podatki** > **Odnosi**.

2. Izberite **Nov odnos**.

3. V podokno **Nov odnos** vnesite te podatke:

   :::image type="content" source="media/relationship-add.png" alt-text="Podokno za nov odnos s praznimi vnosnimi polji.":::

   - **Ime odnosa**: ime, ki odraža namen odnosa. Primer: CustomerToSupportCase.
   - **Opis**: opis odnosa.
   - **Izvorna entiteta**: entiteta, ki se v odnosu uporablja kot vir. Primer: SupportCase.
   - **Ciljna entiteta**: entiteta, ki se v odnosu uporablja kot cilj. Primer: Stranka.
   - **Kardinalnost vira** : Kardinalnost izvorne entitete. Kardinalnost opisuje število možnih elementov v naboru. Navezuje se na ciljno kardinalnost. Izbirate lahko med **Ena** in **Mnogo**. Podprti so samo odnosi »mnogo proti ena« in »ena proti ena«.  
     - Mnogo proti ena: več izvornih zapisov se lahko nanaša na en ciljni zapis. Primer: več primerov za podporo iz ene stranke.
     - Ena proti ena: posamezen izvorni zapis se nanaša na en ciljni zapis. Primer: en ID zvestobe za eno stranko.

     > [!NOTE]
     > Odnose »mnogo proti mnogo« je mogoče ustvariti z dvema odnosoma »mnogo proti ena« in povezovalno entiteto, ki povezuje izvorno entiteto in ciljno entiteto.

   - **Ciljna kardinalnost** : Kardinalnost zapisov ciljne entitete.
   - **Polje ključa vira** : Polje tujega ključa v izvorni entiteti. Primer: SupportCase uporablja **ID primera** kot polje tujega ključa.
   - **Ciljno ključno polje** : Ključno polje ciljne entitete. Primer: Stranka uporablja **Identifikacijska številka stranke** kot ključno polje.

4. Izberite možnost **Shrani**, da ustvarite odnos po meri.

## <a name="set-up-account-hierarchies"></a>Nastavitev hierarhij računov

Okolja, ki so konfigurirana za uporabo poslovnih računov kot primarnega cilja občinstvo, lahko konfigurirajo hierarhije računov za povezane poslovne račune. Na primer podjetje, ki ima ločene poslovne enote.

Organizacije ustvarjajo hierarhije računov za boljše upravljanje računov in njihovih odnosov med seboj. Customer Insights podpira hierarhije računov starš-otrok, ki že obstajajo v zaužitih podatkih strank. Na primer računi iz storitve Dynamics 365 Sales. Te hierarhije je mogoče konfigurirati na **Odnosi** strani.

1. Odprite razdelek **Podatki** > **Odnosi**.
1. Izberite zavihek **Hierarhija računa**.
1. Izberite **Nova hierarhija računa**.
1. V podoknu **Hierarhija računa** vnesite ime za hierarhijo. Sistem ustvari ime za izhodno entiteto, vendar ga lahko spremenite.
1. Izberite entiteto, ki vsebuje hierarhijo vašega računa. Običajno je v isti entiteti, ki vsebuje račune.
1. Izberite **UID računa** in **Nadrejeni UID** iz izbrane entitete.
1. Izberite **Shrani** za dokončanje hierarhije računa.

## <a name="manage-existing-relationships"></a>Upravljanje obstoječih odnosov

Pojdi na **Odnosi** strani za ogled vseh Odnosi, ki so bili ustvarjeni, njihove izvorne entitete, ciljne entitete in kardinalnosti.

:::image type="content" source="media/relationships-list.png" alt-text="Seznam odnosov in možnosti v orodni vrstici strani Odnosi.":::

Uporabi **Filtriraj po** oz **Išči Odnosi** možnosti za iskanje določenega razmerja. Za ogled omrežnega diagrama obstoječega Odnosi in njihove kardinalnosti izberite [**Vizualizator**](#explore-the-relationship-visualizer).

Izberite razmerje za ogled razpoložljivih dejanj:
- **Uredi**: posodobite lastnosti odnosov po meri v podoknu za urejanje in shranite spremembe.
- **Izbriši**: izbrišite odnos po meri.
- **Pogled**: oglejte si sistemsko ustvarjene in podedovane odnose.

### <a name="explore-the-relationship-visualizer"></a>Raziščite vizualizator odnosov

Vizualizator odnosov prikazuje omrežni diagram obstoječih odnosov med povezanimi entitetami in njihovo kardinalnost. Prav tako vizualizira pot odnosa.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Posnetek zaslona omrežnega diagrama vizualizatorja odnosov s povezavami med povezanimi entitetami.":::

Če želite prilagoditi pogled, lahko spremenite položaj polj tako, da jih povlečete na platno. Druge možnosti vključujejo: 
- **Izvozi kot sliko**: shranite trenutni pogled kot slikovno datoteko.
- **Spremeni v vodoravno/navpično postavitev**: spremenite poravnavo entitet in odnosov.
- **Uredi**: posodobite lastnosti odnosov po meri v podoknu za urejanje in shranite spremembe.

## <a name="relationship-paths"></a>Poti odnosa

Pot odnosa opisuje entitete, ki so povezane z odnosi med izvorno entiteto in ciljno entiteto. Uporablja se pri ustvarjanju segmenta ali mere, ki vključuje entitete, ki niso entiteta poenotenega profila, in obstaja več možnosti za doseganje entitete poenotenega profila. Različne poti odnosov lahko podajo različne rezultate.

Na primer entiteta *eCommerce_eCommercePurchases* ima do poenotenega profila entitete *Stranka* naslednje odnose:

- eCommerce_eCommercePurchases > Stranka
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Stranka
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Stranka

Pot odnosa določa, katere entitete lahko uporabite pri ustvarjanju pravil za ukrepe ali segmente. Izbira možnosti z najdaljšo potjo odnosa bo verjetno prinesla manj rezultatov, ker morajo biti ujemajoči se zapisi del vseh entitet. V tem primeru mora stranka kupiti izdelke prek e-trgovine (eCommerce_eCommercePurchases) na prodajnem mestu (POS_posPurchases) in sodelovati v našem programu zvestobe (loyaltyScheme_loyCustomers). Če bi izbrali prvo možnost, bi verjetno dobili več rezultatov, ker morajo stranke obstajati le v eni dodatni entiteti.

### <a name="direct-relationship"></a>Neposredni odnos

Odnos je razvrščen kot **neposredni odnos**, če se izvorna entiteta nanaša na ciljno entiteto samo z enim odnosom.

Na primer, če se entiteta dejavnosti, imenovana *eCommerce_eCommercePurchases*, poveže s ciljno entiteto *eCommerce_eCommerceContacts* samo prek *ContactId*, je to neposredni odnos.

:::image type="content" source="media/direct_Relationship.png" alt-text="Izvorna entiteta se poveže neposredno s ciljno entiteto.":::

#### <a name="multi-path-relationship"></a>Odnos z več potmi

**Odnos z več potmi** je posebna vrsta neposrednega odnosa, ki izvorno entiteto poveže z več kot eno ciljno entiteto.

Na primer, če se entiteta dejavnosti, imenovana *eCommerce_eCommercePurchases*, nanaša na dve ciljni entiteti, imenovani *eCommerce_eCommerceContacts* in *loyaltyScheme_loyCustomers*, je to odnos z več potmi.

:::image type="content" source="media/multi-path_relationship.png" alt-text="Izvorna entiteta se prek odnosa z več skoki neposredno poveže z več ciljnimi entitetami.":::

### <a name="indirect-relationship"></a>Posredni odnos

Odnos je razvrščen kot **posredni odnos**, če se izvorna entiteta nanaša na eno ali več dodatnih entitet, preden se nanaša na ciljno entiteto.

#### <a name="multi-hop-relationship"></a>Odnos z več skoki

**Odnos z več skoki** je *posredni odnos*, ki omogoča povezavo izvorne entitete s ciljno entiteto prek ene ali več drugih vmesnih entitet.

Na primer, če se entiteta dejavnosti, imenovana *eCommerce_eCommercePurchasesWest*, poveže z vmesno entiteto, imenovano *eCommerce_eCommercePurchasesEast*, in se nato poveže s ciljno entiteto, imenovano *eCommerce_eCommerceContacts*, je to odnos z več skoki.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="Izvorna entiteta se neposredno poveže s ciljno entiteto z vmesno entiteto.":::

### <a name="multi-hop-multi-path-relationship"></a>Odnos z več skoki in več potmi

Odnose z več skoki in odnose z več potmi lahko uporabite za ustvarjanje **odnosov z več skoki in več potmi**. Ta posebna vrsta združuje funkciji **odnosi z več skoki** in **odnosi z več potmi**. Omogoča, da se med uporabo vmesnih entitet povežete z več kot eno ciljno entiteto.

Na primer, če se entiteta dejavnosti, imenovana *eCommerce_eCommercePurchasesWest*, poveže z vmesno entiteto, imenovano *eCommerce_eCommercePurchasesEast*, in se nato poveže z dvema ciljnima entitetama, imenovanima *eCommerce_eCommerceContacts* in *loyaltyScheme_loyCustomers*, je to odnos z več skoki in več potmi.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="Izvorna entiteta se neposredno poveže z eno ciljno entiteto in se z vmesno entiteto poveže z drugo ciljno entiteto.":::

## <a name="next-step"></a>Naslednji korak

Sistemske odnose in odnose po meri uporabljamo, da [ustvarimo segmente](segments.md) in [mere](measures.md) na podlagi več virov podatkov, ki niso več v silosu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
