---
title: Povezave z drugimi storitvami iz rešitve Customer Insights.
description: Delite podatke z drugimi storitvami.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 10704e287960c1a9171031135ff8f78a45b6e965
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643338"
---
# <a name="connections-preview-overview"></a>Pregled povezav (predogledna različica)

Povezave so ključnega pomena za omogočanje skupne rabe podatkov iz rešitve Customer Insights. Vsaka povezava vzpostavi skupno rabo podatkov z določeno storitvijo. Povezave so temelj za [konfiguriranje obogatitev neodvisnih proizvajalcev](enrichment-hub.md) in [konfiguriranje izvozov](export-destinations.md). Isto povezavo je mogoče uporabiti večkrat. Ena povezava s storitvijo Dynamics 365 Marketing na primer deluje za več izvozov, eno povezavo za Leadspace pa lahko uporabite za več obogatitev.

Odprite razdelek **Skrbnik** > **Povezave**, da ustvarite povezave in si jih ogledate.

V zavihku **Povezave** so prikazane vse dejavne povezave. Na seznamu je prikazana vrstica za vsako posamezno povezavo. 

Na zavihku **Odkrivanje** pridobite hiter pregled in opis ter ugotovite, kaj lahko storite s posamezno možnostjo razširljivosti.

### <a name="exports"></a>Izvozi

Nove povezave lahko konfigurirajo samo skrbniki, lahko pa sodelavcem dodelijo dostop do uporabe obstoječih povezav. Skrbniki nadzorujejo, kam so lahko poslani podatki, sodelavci pa določajo koristno vsebino in pogostost, ki ustreza njihovim potrebam. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](#allow-contributors-to-use-a-connection-for-exports).

### <a name="enrichments"></a>Obogatitve

Nove povezave lahko konfigurirajo samo skrbniki, vendar so ustvarjene povezave vedno na voljo tako skrbnikom kot sodelavcem. Skrbniki upravljajo poverilnice in podelijo soglasje za prenose podatkov. Povezave lahko nato za obogatitve uporabijo tako skrbniki kot sodelavci.

## <a name="add-a-new-connection"></a>Dodajanje nove povezave

Za dodajanje povezav morate imeti [skrbniška dovoljenja](permissions.md). Če vzpostavite povezavo z drugimi Microsoftovimi storitvami, predvidevamo, da sta obe storitvi del iste organizacije.

1. Odprite razdelek **Skrbnik** > **Povezave (predogled)**.

1. Pojdite na zavihek **Povezave**.

1. Izberite možnost **Dodaj povezavo**, da ustvarite novo povezavo. V spustnem meniju izberite vrsto povezave, ki jo želite ustvariti.

1. V podoknu **Vzpostavitev povezave** vnesite zahtevane podrobnosti. 
   1. **Prikazno ime** in vrsta povezave opisujeta povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.
   1. Dejanska polja so odvisna od storitve, s katero vzpostavljate povezavo. Podrobnosti o določeni vrsti povezave lahko izveste v ustreznem članku o ciljni storitvi.
   1. Če [uporabite storitev Key Vault](use-azure-key-vault.md) za shranjevanje skrivnosti, aktivirajte možnost **Uporaba storitve Key Vault** in izberite skrivnost s seznama.

1. Izberite možnost **Shrani**, da ustvarite povezavo.

Izberete lahko tudi **Nastavitev** na ploščici na zavihku **Odkrivanje**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Omogočanje uporabe povezav za izvoze podatkov za sodelavce

Ko nastavljate povezavo za izvoz podatkov ali jo urejate, izberete uporabnike, ki lahko uporabijo to povezavo za določanje [izvozov podatkov](export-destinations.md). Privzeto je povezava na voljo uporabnikom z vlogo skrbnika. To nastavitev lahko spremenite v razdelku **Izberite, kdo lahko uporablja to povezavo** in dovolite uporabo te povezave uporabnikom z vlogo sodelavca.

- Sodelavci ne bodo mogli videti povezave ali je urejati. Pri ustvarjanju izvoza bodo videli le prikazno ime in vrsto povezave.
- Če date povezavo v skupno rabo, sodelavcem dovolite uporabo povezave. Sodelavci bodo videli skupne povezave, ko nastavijo izvoze. Upravljajo lahko vse izvoze, v katerih je uporabljena ta specifična povezava.
- To nastavitev lahko spremenite, hkrati pa ohranite izvoze, ki so jih že določili sodelavci.

## <a name="edit-a-connection"></a>Urejanje povezave

1. Odprite razdelek **Skrbnik** > **Povezave (predogled)**.

1. Pojdite na zavihek **Povezave**.

1. Izberite navpične tri pike zraven povezave, ki jo želite urediti.

1. Izberite **Uredi**.

1. Spremenite vrednosti, ki jih želite posodobiti, in izberite **Shrani**.

## <a name="remove-a-connection"></a>Odstranjevanje povezave

Če je povezava, ki jo želite odstraniti, uporabljena v obogatitvah ali izvozih, jo morate najprej odstraniti oziroma z njo prekiniti povezavo. Pogovorno okno za odstranitev vas bo vodilo do ustreznih obogatitev oziroma izvozov. 

Odstranjene obogatitve in izvozi bodo postali nedejavni. Ponovno jih aktivirate tako, da jim na strani [Obogatitve](enrichment-hub.md) ali [Izvozi](export-destinations.md) dodate drugo povezavo.

1. Odprite razdelek **Skrbnik** > **Povezave (predogled)**.

1. Pojdite na zavihek **Povezave**.

1. Izberite navpične tri pike zraven povezave, ki jo želite odstraniti.

1. Na spustnem seznamu izberite **Odstrani**. Prikaže se potrditveno pogovorno okno.

   1. Če je povezava uporabljena v obogatitvah ali izvozih, izberite gumb, da preverite, kateri elementi uporabljajo povezavo.
      - **Izvozi:** če želite odstraniti povezavo, lahko izberete možnost odstranjevanja ali prekinjanja povezave z izvozi. Za prekinitev povezave z izvozom lahko skrbniki uporabijo dejanje **Prekini povezavo**. To dejanje je na voljo za posamezen izbrani izvoz ali več njih. Če prekinete povezavo, se konfiguracija izvoza ohrani, vendar se ne bo zagnala, dokler ji ni dodana druga povezava.
      - **Obogatitve:** če želite odstraniti povezavo, lahko izberete možnost deaktiviranja ali odstranjevanja obogatitev. 
   1. Ko za povezavo ni več odvisnosti, se vrnite v razdelek **Skrbnik** > **Povezave** in poskusite znova odstraniti povezavo.

1. Za potrditev izbrisa izberite možnost **Odstrani**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Vzpostavitev povezav s skrivnostmi, ki jih upravlja vaša storitev Key Vault

Nekatere povezave potrebujejo skrivnosti, kot so ključi API ali gesla. Nekatere povezave podpirajo skrivnosti, shranjene v vaši storitvi Key Vault. Preberite več o podprtih povezavah in o tem, kako jih nastaviti [svoj lastni trezor ključev za vpogled v stranke](use-azure-key-vault.md).