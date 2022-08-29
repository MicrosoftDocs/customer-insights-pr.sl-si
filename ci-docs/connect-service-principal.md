---
title: Povezava z računom Azure Data Lake Storage z uporabo glavnega imena storitve Azure
description: Uporaba glavnega imena storitve Azure za povezovanje s shrambo Data Lake.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: eba10068c48db5c147100c25a397bcc13b014784
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304217"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Povezava z računom Azure Data Lake Storage z uporabo glavnega imena storitve Azure

Dynamics 365 Customer Insights ponuja možnost povezave z Azure Data Lake Storage račun z uporabo principala storitve Azure namesto ključev računa za shranjevanje.

Samodejna orodja, ki uporabljajo storitve Azure, morajo imeti omejena dovoljenja. Namesto da bi se v aplikacije vpisali kot uporabnik s vsemi pravicami, Azure ponuja glavno ime storitve. Uporabite principale storitev za varno [dodajte ali uredite mapo skupnega podatkovnega modela kot vir podatkov](connect-common-data-model.md) oz [ustvarite ali posodobite okolje](create-environment.md).

## <a name="prerequisites"></a>Zahteve

- Račun Data Lake Storage, ki bo uporabljal principala storitve, mora biti Gen2. Računi za shranjevanje Azure Data Lake Gen1 niso podprti.
- Račun Data Lake Storage ima [hierarhičen imenski prostor omogočen](/azure/storage/blobs/data-lake-storage-namespace).
- Skrbniška dovoljenja za vaš najemnik imenika Azure, če morate ustvariti novega principala storitve.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Ustvarjanje glavnega imena storitve Azure za storitev Customer Insights

Preden ustvarite novega principala storitve za Customer Insights, preverite, ali že obstaja v vaši organizaciji. V večini primerov že obstaja.

### <a name="look-for-an-existing-service-principal"></a>Poiščite obstoječega glavnega imena storitve

1. Odprite [skrbniški portal Azure](https://portal.azure.com) in se vpišite v svojo organizacijo.

2. Iz **storitev Azure** izberite **Azure Active Directory**.

3. Spodaj **Upravljaj**, izberite **Microsoftova aplikacija**.

4. Dodajte filter za **ID aplikacije se začne z**`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ali poiščite ime `Dynamics 365 AI for Customer Insights`.

5. Če najdete ujemajoči se zapis, to pomeni, da glavno ime storitve že obstaja. [Podeli dovoljenja](#grant-permissions-to-the-service-principal-to-access-the-storage-account) za dostop principala storitve do računa za shranjevanje.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Posnetek zaslona, ki prikazuje obstoječe glavno ime storitve.":::

6. Če rezultati niso vrnjeni, [ustvarite novega principala storitve](#create-a-new-service-principal).

### <a name="create-a-new-service-principal"></a>Ustvari novo glavno ime storitve

1. Namestite najnovejšo različico storitve Azure Active Directory PowerShell for Graph. Za več informacij pojdite na [Namestitev storitve Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. V računalniku pritisnite tipko Windows na tipkovnici in poiščite **Windows PowerShell** in izberite **Zaženi kot skrbnik**.

   1. V oknu PowerShell, ki se odpre, vnesite `Install-Module AzureAD`.

2. Ustvarite glavno ime storitve za Customer Insights z modulom Azure AD PowerShell.

   1. V oknu PowerShell vnesite `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Zamenjati *[vaš ID imenika]* z dejanskim ID-jem imenika vaše naročnine na Azure, kjer želite ustvariti principala storitve. Parameter z imenom okolja, `AzureEnvironmentName`, je izbiren.
  
   1. Vnesite `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Ta ukaz ustvari principala storitve za Customer Insights v izbrani naročnini na Azure.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Dodelite dovoljenja glavnemu imenu storitve za dostop do računa za shranjevanje

Če želite podeliti dovoljenja glavnemu servisu za račun za shranjevanje, ki ga želite uporabiti v Customer Insights, mora biti računu za shranjevanje ali vsebniku dodeljena ena od naslednjih vlog:

|Poverilnica|Zahteve|
|----------|------------|
|Trenutno prijavljen uporabnik|**Vloga** : Podatki pomnilniške blob Uporabnik z dovoljenjem za branje, pomnilniški blob sodelavec ali lastnik pomnilniške blob.<br>**Raven** : dovoljenja, dodeljena za račun za shranjevanje ali vsebnik.</br>|
|Vodja storitve Customer Insights -<br>Uporaba Azure Data Lake Storage kot vir podatkov</br>|Možnost 1<ul><li>**Vloga** : Podatki bloba za shranjevanje Uporabnik z dovoljenjem za branje, podatki bloba za shranjevanje sodelavec ali lastnik podatkov bloba za shranjevanje.</li><li>**Raven** : dovoljenja za račun za shranjevanje.</li></ul>Možnost 2 *(brez deljenja dostopa glavnega servisa do računa za shranjevanje)*<ul><li>**Vloga 1** : Podatki bloba za shranjevanje Uporabnik z dovoljenjem za branje, podatki bloba za shranjevanje sodelavec ali lastnik podatkov bloba za shranjevanje.</li><li>**Raven** : dovoljenja za vsebnik.</li><li>**Vloga 2** : Delegator podatkov bloba za shranjevanje.</li><li>**Raven** : dovoljenja za račun za shranjevanje.</li></ul>|
|Vodja storitve Customer Insights - <br>Uporaba Azure Data Lake Storage kot izhod ali cilj</br>|Možnost 1<ul><li>**Vloga** : Storage Blob Data sodelavec ali Storage Blob Owner.</li><li>**Raven** : dovoljenja za račun za shranjevanje.</li></ul>Možnost 2 *(brez deljenja dostopa glavnega servisa do računa za shranjevanje)*<ul><li>**Vloga** : Storage Blob Data sodelavec ali Storage Blob Owner.</li><li>**Raven** : dovoljenja za vsebnik.</li><li>**Vloga 2** : Delegator blob pomnilnika.</li><li>**Raven** : dovoljenja za račun za shranjevanje.</li></ul>|

1. Odprite [skrbniški portal Azure](https://portal.azure.com) in se vpišite v svojo organizacijo.

1. Odprite račun za shranjevanje, do katerega želite, da ima glavni servis za Customer Insights dostop.

1. V levem podoknu izberite **Nadzor dostopa (IAM)** in nato izberite **Dodaj** > **Dodaj dodelitev vloge**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Posnetek zaslona, ki prikazuje portal Azure med dodajanjem dodelitve vloge.":::

1. V podoknu **Dodaj dodelitev vlog** nastavite naslednje lastnosti:
   - **Vloga** : Storage Blob Data Uporabnik z dovoljenjem za branje, Storage Blob sodelavec ali Lastnik Storage Blob na podlagi poverilnic, navedenih zgoraj.
   - **Dodeli dostop do** :**Uporabnik, skupina ali principal storitve**
   - **Izberite** člani: **Dynamics 365 AI for Customer Insights** ([glavni servis](#create-a-new-service-principal) ste iskali prej v tem postopku)

1. Izberite **Pregled + dodelitev**.

Uvedba sprememb lahko traja do 15 minut.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Vnesite ID vira Azure ali podrobnosti o naročnini na Azure v prilogo računa za shranjevanje v Customer Insights

Pripnite račun Data Lake Storage v Customer Insights [shranjevanje izhodnih podatkov](manage-environments.md) oz [uporabite ga kot vir podatkov](connect-dataverse-managed-lake.md). Izbirajte med a [na podlagi virov](#resource-based-storage-account-connection) ali a [na podlagi naročnine](#subscription-based-storage-account-connection) pristopite in sledite tem korakom.

### <a name="resource-based-storage-account-connection"></a>Povezava računa za shrambo na podlagi vira

1. Odprite [skrbniški portal Azure](https://portal.azure.com), se vpišite v svojo naročnino in odprite račun za shranjevanje.

1. V levem podoknu pojdite na **nastavitve** > **Končne točke**.

1. Kopirajte vrednost ID-ja vira računa za shranjevanje.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopirajte ID vira računa za shranjevanje.":::

1. V Customer Insights vstavite ID vira v polje vira, prikazano na zaslonu povezave računa za shranjevanje.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Vnesite podatke za ID vira računa za shranjevanje.":::

1. Nadaljujte s preostalimi koraki v Customer Insights, da priložite račun za shranjevanje.

### <a name="subscription-based-storage-account-connection"></a>Povezava računa za shranjevanje na podlagi naročnine

1. Odprite [skrbniški portal Azure](https://portal.azure.com), se vpišite v svojo naročnino in odprite račun za shranjevanje.

1. V levem podoknu pojdite v razdelek **Nastavitve** > **Lastnosti**.

1. Preglejte **Naročnina**, **virov**, in **Ime** računa za shranjevanje, da zagotovite, da izberete prave vrednosti v Customer Insights.

1. V Customer Insights izberite vrednosti za ustrezna polja, ko pripenjate račun za shranjevanje.

1. Nadaljujte s preostalimi koraki v Customer Insights, da priložite račun za shranjevanje.

[!INCLUDE [footer-include](includes/footer-banner.md)]
