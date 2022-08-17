---
title: Pregled povezav (predogledna različica)
description: Povezave z drugimi storitvami iz rešitve Customer Insights.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245531"
---
# <a name="connections-preview-overview"></a>Pregled povezav (predogledna različica)

Povezave so ključnega pomena za omogočanje skupne rabe podatkov iz rešitve Customer Insights. Vsaka povezava vzpostavi skupno rabo podatkov z določeno storitvijo. Uporabite povezave do [konfigurirajte obogatitve tretjih oseb](enrichment-hub.md) in [konfigurirajte izvoze](export-destinations.md). Isto povezavo je mogoče uporabiti večkrat. Ena povezava s storitvijo Dynamics 365 Marketing na primer deluje za več izvozov, eno povezavo za Leadspace pa lahko uporabite za več obogatitev.

## <a name="export-connections"></a>Izvozne povezave

Samo skrbniki lahko konfigurirajo nove povezave, vendar jih lahko [omogočiti dostop sodelujočim](#allow-contributors-to-use-a-connection-for-exports) za uporabo obstoječih povezav. Skrbniki nadzorujejo, kam so lahko poslani podatki, sodelavci pa določajo koristno vsebino in pogostost, ki ustreza njihovim potrebam.

## <a name="enrichment-connections"></a>Obogatitvene povezave

Samo skrbniki lahko konfigurirajo nove povezave, vendar so ustvarjene povezave vedno na voljo skrbnikom in sodelavcem. Skrbniki upravljajo poverilnice in podelijo soglasje za prenose podatkov. Povezave lahko nato za obogatitve uporabijo tako skrbniki kot sodelavci.

## <a name="add-a-new-connection"></a>Dodajanje nove povezave

### <a name="prerequisites"></a>Zahteve

- [Dovoljenja skrbnika](permissions.md)
- Druge Microsoftove storitve, če obstajajo, so v isti organizaciji

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite vrsto povezave, ki jo želite ustvariti. Ali pa pojdite na **Odkrij** zavihek in izberite **Nastaviti** na povezovalni ploščici.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Vnesite zahtevane podatke. Natančna polja so odvisna od storitve, s katero se povezujete. Za podrobnosti o določeni vrsti povezave glejte članek o ciljni storitvi.

1. Če [uporabite storitev Key Vault](use-azure-key-vault.md) za shranjevanje skrivnosti, aktivirajte možnost **Uporaba storitve Key Vault** in izberite skrivnost s seznama.

1. Preglejte zasebnost podatkov in skladnost ter izberite **strinjam se**.

1. Izberite **Shrani** da ustvarite povezavo.

### <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov tretjim osebam ali drugim Microsoftovim izdelkom dovolite prenos podatkov izven meja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo prenesel takšne podatke po vaših navodilih, vendar ste vi odgovorni za zagotovitev, da tretja oseba izpolnjuje morebitne vaše obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Vaš Dynamics 365 Customer Insights skrbnik lahko kadar koli odstrani povezavo in prekine uporabo funkcionalnosti.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>Omogočanje uporabe povezav za izvoze podatkov za sodelavce

Ko nastavljate ali urejate izvozno povezavo, izberite, katerim uporabnikom je dovoljena uporaba te posebne povezave za definiranje [izvoz](export-destinations.md). Privzeto je povezava na voljo uporabnikom z vlogo skrbnika. Spremenite **Izberite, kdo lahko uporablja to povezavo** nastavitev, ki omogoča uporabnikom z vlogo sodelavec uporabo te povezave.

- Sodelavci ne bodo mogli videti povezave ali je urejati. Pri ustvarjanju izvoza bodo videli le prikazno ime in njegovo vrsto.
- Če date povezavo v skupno rabo, sodelavcem dovolite uporabo povezave. Sodelavci bodo videli skupne povezave, ko nastavijo izvoze. Upravljajo lahko vse izvoze, v katerih je uporabljena ta specifična povezava.
- To nastavitev lahko spremenite, hkrati pa ohranite izvoze, ki so jih že določili sodelavci.

## <a name="manage-existing-connections"></a>Upravljajte obstoječe povezave

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Obogatitev** oz **Izvozi** za ogled seznama obogatitvenih ali izvoznih povezav, vrste povezave, kdaj je bila ustvarjena in kdo ima dostop. Seznam povezav lahko razvrstite po kateremkoli stolpcu.

1. Izberite povezavo za ogled razpoložljivih dejanj.

   - **Uredi** povezava.
   - [**Odstrani**](#remove-a-connection) povezava.

### <a name="remove-a-connection"></a>Odstranjevanje povezave

Če povezavo, ki jo odstranjujete, uporabljajo obogatitve ali izvozi, jih najprej odklopite ali odstranite. Pogovorno okno za odstranitev vas vodi do ustreznih obogatitev ali izvozov.

> [!TIP]
> Deaktivirane obogatitve in ločeni izvozi postanejo neaktivni. Ponovno jih aktivirate tako, da jim na strani [Obogatitve](enrichment-hub.md) ali [Izvozi](export-destinations.md) dodate drugo povezavo.

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Obogatitev** oz **Izvozi** zavihek.

1. Izberite povezavo, ki jo želite odstraniti.

1. Na spustnem seznamu izberite **Odstrani**. Prikaže se potrditveno pogovorno okno.

   1. Če je povezava uporabljena v obogatitvah ali izvozih, izberite gumb, da preverite, kateri elementi uporabljajo povezavo.
      - **Izvozi:** Izberite bodisi **Odstrani** izvoz oz **Odklopite povezavo**. Če odstranite povezavo, ohranite izvozno konfiguracijo, vendar se ne bo zagnala, dokler ji ne dodate druge povezave.
      - **Obogatitve:** Izberite bodisi **Izbriši** oz **Deaktiviraj** obogatitve.
   1. Ko za povezavo ni več odvisnosti, se vrnite v razdelek **Skrbnik** > **Povezave** in poskusite znova odstraniti povezavo.

1. Za potrditev izbrisa izberite možnost **Odstrani**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Vzpostavitev povezav s skrivnostmi, ki jih upravlja vaša storitev Key Vault

Nekatere povezave potrebujejo skrivnosti, kot so ključi API ali gesla. Nekatere povezave podpirajo skrivnosti, shranjene v vaši storitvi Key Vault. Izvedite več o podprtih povezavah in o tem, kako jih nastaviti [svoj lastni trezor ključev za Customer Insights](use-azure-key-vault.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
