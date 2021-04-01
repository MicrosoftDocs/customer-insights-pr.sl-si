---
title: Odnosi med entitetami in poti entitet
description: Ustvarite in upravljajte odnose med entitetami iz več virov podatkov.
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595232"
---
# <a name="relationships-between-entities"></a>Odnosi med entitetami

Odnosi vam pomagajo pri povezovanju entitet in ustvarjanju grafa vaših podatkov, kadar si entitete delijo skupni identifikator (tuji ključ), na katerega se je mogoče sklicevati iz ene entitete v drugo. Povezane entitete vam omogočajo, da določite segmente in mere na podlagi več virov podatkov.

Obstajata dve vrsti odnosov. Sistemski odnosi, ki so ustvarjeni samodejno in jih ni mogoče urejati, ter odnosi po meri, ki jih ustvarijo in konfigurirajo uporabniki.

Med postopki ujemanja in spajanja so sistemski odnosi ustvarjeni v ozadju na osnovi pametnega ujemanja. Ti odnosi pomagajo povezati zapise profila stranke z drugimi ustreznimi zapisi entitet. Spodnji diagram prikazuje ustvarjanje treh sistemskih odnosov, ko se entiteta stranke ujema z dodatnimi entitetami in se ustvari entiteta končnega profila stranke.

> [!div class="mx-imgBorder"]
> ![Ustvarjanje odnosa](media/relationships-entities-merge.png "Ustvarjanje odnosa")

- **Odnos *CustomerToContact*** je bil ustvarjen med entiteto stranke in entiteto stika. Za entiteto stranke se uporabi polje ključa **Contact_contactId** za povezovanje s poljem ključa entitete stika **contactId**.
- **Odnos *CustomerToAccount*** je bil ustvarjen med entiteto stranke in entiteto kupca. Za entiteto stranke se uporabi polje ključa **Account_accountId** za povezovanje s poljem ključa entitete kupca **accountId**.
- **Odnos *CustomerToWebAccount*** je bil ustvarjen med entiteto stranke in entiteto spletnega kupca. Za entiteto stranke se uporabi polje ključa **WebAccount_webaccountId** za povezovanje s poljem ključa entitete spletnega kupca **webaccountId**.

## <a name="create-a-relationship"></a>Ustvarjanje odnosa

Na strani **Odnosi** določite odnose po meri. Vsak odnos je sestavljen iz izvorne entitete (entiteta, ki ima tuji ključ) in ciljne entitete (entiteta, na katero kaže tuji ključ izvorne entitete).

1. Pri vpogledih v občinstvo izberite **Podatki** > **Odnosi**.

2. Izberite **Nov odnos**.

3. V podoknu **Dodaj odnos** vnesite te podatke:

   > [!div class="mx-imgBorder"]
   > ![Vnos podrobnosti o odnosu](media/relationships-add.png "Vnos podrobnosti o odnosu")

   - **Ime odnosa**: ime, ki odraža namen odnosa (npr. **AccountWebLogs**).
   - **Opis**: opis odnosa.
   - **Izvorna entiteta**: izberite entiteto, ki se uporablja kot vir v odnosu (na primer WebLog).
   - **Kardinalnost**: izberite kardinalnost zapisov izvorne entitete. »Mnogo« na primer pomeni, da je več zapisov Weblog povezanih z eno entiteto WebAccount.
   - **Polje izvornega ključa**: predstavlja polje za tuji ključ v izvorni entiteti. WebLog ima na primer polje za tuji ključ **accountId**.
   - **Ciljna entiteta**: izberite entiteto, ki se uporablja kot cilj v odnosu (na primer WebAccount).
   - **Kardinalnost cilja**: izberite kardinalnost zapisov ciljne entitete. »Ena« na primer pomeni, da je več zapisov Weblog povezanih z eno entiteto WebAccount.
   - **Ciljno polje ključa**: to polje predstavlja polje ključa ciljne entitete. WebAccount ima na primer polje ključa **accountId**.

> [!NOTE]
> Podprti so samo odnosi »mnogo proti ena« in »ena proti ena«. Odnose »mnogo proti mnogo« lahko ustvarite z uporabo dveh odnosov »mnogo proti ena« in entiteto povezave (entiteta, ki se uporablja za povezovanje izvorne in ciljne entitete).

## <a name="delete-a-relationship"></a>Brisanje odnosa

1. Pri vpogledih v občinstvo izberite **Podatki** > **Odnosi**.

2. Potrdite polja pri odnosih, ki jih želite izbrisati.

3. Izberite **Izbriši** na vrhu tabele **Odnosi**.

4. Potrdite izbris.

## <a name="next-step"></a>Naslednji korak

Sistemski odnosi in odnosi po meri se uporabljajo za ustvarjanje segmentov na podlagi več virov podatkov, ki niso več ločeni. Če želite več informacij, glejte [Segmenti](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]