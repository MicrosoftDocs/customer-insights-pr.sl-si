---
title: Povezava z računom Azure Data Lake Storage z uporabo glavnega imena storitve Azure
description: Uporaba glavnega imena storitve Azure za povezovanje s shrambo Data Lake.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 949caa73578dbe0a511726ec045c0fd5f4621de4
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082249"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Povezava z računom Azure Data Lake Storage z uporabo glavnega imena storitve Azure

Ta članek govori o tem, kako povezati Dynamics 365 Customer Insights z Azure Data Lake Storage račun z uporabo principala storitve Azure namesto ključev računa za shranjevanje.

Avtomatizirana orodja, ki uporabljajo storitve Azure, bi morala imeti vedno omejena dovoljenja. Namesto da bi se v aplikacije vpisali kot uporabnik s vsemi pravicami, Azure ponuja glavno ime storitve. Za varno lahko uporabite principe storitev [dodajte ali uredite mapo skupnega podatkovnega modela kot vir podatkov](connect-common-data-model.md) oz [ustvarite ali posodobite okolje](create-environment.md).

> [!IMPORTANT]
>
> - Račun Data Lake Storage, ki bo uporabljal principala storitve, mora biti Gen2 in imeti [hierarhičen imenski prostor je omogočen](/azure/storage/blobs/data-lake-storage-namespace). Računi za shranjevanje podatkov Azure Data Lake Gen1 niso podprti.
> - Za ustvarjanje principala storitve potrebujete skrbniška dovoljenja za najemnik imenika Azure.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Ustvarjanje glavnega imena storitve Azure za storitev Customer Insights

Preden ustvarite novega principala storitve za Customer Insights, preverite, ali že obstaja v vaši organizaciji.

### <a name="look-for-an-existing-service-principal"></a>Poiščite obstoječega glavnega imena storitve

1. Odprite [skrbniški portal Azure](https://portal.azure.com) in se vpišite v svojo organizacijo.

2. Iz **storitev Azure** izberite **Azure Active Directory**.

3. Spodaj **Upravljaj**, izberite **Microsoftova aplikacija**.

4. Dodajte filter za **ID aplikacije se začne z**`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ali poiščite ime `Dynamics 365 AI for Customer Insights`.

5. Če najdete ujemajoči se zapis, to pomeni, da glavno ime storitve že obstaja.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Posnetek zaslona, ki prikazuje obstoječe glavno ime storitve.":::

6. Če se rezultati ne vrnejo, lahko [ustvarite novega principala storitve](#create-a-new-service-principal). V večini primerov že obstaja in za dostop do pomnilniškega računa morate dodeliti samo dovoljenja principalu storitve.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Dodelite dovoljenja glavnemu imenu storitve za dostop do računa za shranjevanje

Pojdite na portal Azure, da podelite dovoljenja principalu storitve za račun za shranjevanje, ki ga želite uporabiti v Customer Insights. Računu za shranjevanje ali vsebniku mora biti dodeljena ena od naslednjih vlog:

|Poverilnica|Zahteve|
|----------|------------|
|Trenutno prijavljen uporabnik|**Vloga** : Storage Blob Data Uporabnik z dovoljenjem za branje, Storage Blob sodelavec ali Lastnik Storage Blob.<br>**Raven** : Dovoljenja se lahko dodelijo za račun za shranjevanje ali vsebnik.</br>|
|Vodja storitve Customer Insights -<br>Uporaba Azure Data Lake Storage kot vir podatkov</br>|Možnost 1<ul><li>**Vloga** : Storage Blob Data Uporabnik z dovoljenjem za branje, Storage Blob Data sodelavec ali Lastnik podatkov Storage Blob.</li><li>**Raven** : Dovoljenja je treba odobriti za račun za shranjevanje.</li></ul>2. možnost *(brez deljenja dostopa glavnega servisa do računa za shranjevanje)*<ul><li>**1. vloga** : Storage Blob Data Uporabnik z dovoljenjem za branje, Storage Blob Data sodelavec ali Lastnik podatkov Storage Blob.</li><li>**Raven** : Dovoljenja je treba odobriti za vsebnik.</li><li>**2. vloga** : Delegator podatkov blobov za shranjevanje.</li><li>**Raven** : Dovoljenja je treba odobriti za račun za shranjevanje.</li></ul>|
|Vodja storitve Customer Insights - <br>Uporaba Azure Data Lake Storage kot izhod ali cilj</br>|Možnost 1<ul><li>**Vloga** : Storage Blob Data sodelavec ali Storage Blob Lastnik.</li><li>**Raven** : Dovoljenja je treba odobriti za račun za shranjevanje.</li></ul>2. možnost *(brez deljenja dostopa glavnega servisa do računa za shranjevanje)*<ul><li>**Vloga** : Storage Blob Data sodelavec ali Storage Blob Lastnik.</li><li>**Raven** : Dovoljenja je treba odobriti za vsebnik.</li><li>**2. vloga** : Delegator blobov za shranjevanje.</li><li>**Raven** : Dovoljenja je treba odobriti za račun za shranjevanje.</li></ul>|

1. Odprite [skrbniški portal Azure](https://portal.azure.com) in se vpišite v svojo organizacijo.

1. Odprite račun za shranjevanje, do katerega želite, da ima dostop principal storitve za Customer Insights.

1. V levem podoknu izberite **Nadzor dostopa (IAM)** in nato izberite **Dodaj** > **Dodaj dodelitev vloge**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Posnetek zaslona, ki prikazuje portal Azure med dodajanjem dodelitve vloge.":::

1. V podoknu **Dodaj dodelitev vlog** nastavite naslednje lastnosti:
   - Vloga: Storage Blob Data Uporabnik z dovoljenjem za branje, Storage Blob sodelavec ali Lastnik Storage Blob na podlagi poverilnic, navedenih zgoraj.
   - Dodeli dostop za: **uporabnik, skupina ali glavno ime storitve**
   - Izberite člane: **Dynamics 365 AI for Customer Insights** ([ravnatelja storitve](#create-a-new-service-principal) ste pogledali prej v tem postopku)

1. Izberite **Pregled + dodelitev**.

Uvedba sprememb lahko traja do 15 minut.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Vnesite ID vira Azure ali podrobnosti o naročnini Azure v prilogo računa za shranjevanje v Customer Insights

Račun Data Lake Storage v storitvi Customer Insights lahko pripnete [shraniti izhodne podatke](manage-environments.md) oz [uporabite ga kot vir podatkov](connect-dataverse-managed-lake.md). Ta možnost vam omogoča izbiro med pristopom, ki temelji na virih, ali pristopom, ki temelji na naročnini. Odvisno od pristopa, ki ga izberete, sledite postopku v enem od naslednjih razdelkov.

### <a name="resource-based-storage-account-connection"></a>Povezava računa za shrambo na podlagi vira

1. Odprite [skrbniški portal Azure](https://portal.azure.com), se vpišite v svojo naročnino in odprite račun za shranjevanje.

1. V levem podoknu pojdite na **Nastavitve** > **Končne točke**.

1. Kopirajte vrednost ID-ja vira računa za shranjevanje.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopirajte ID vira računa za shranjevanje.":::

1. V Customer Insights vstavite ID vira v polje vira, prikazano na zaslonu povezave računa za shranjevanje.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Vnesite podatke za ID vira računa za shranjevanje.":::   

1. Nadaljujte s preostalimi koraki v Customer Insights, da priložite račun za shranjevanje.

### <a name="subscription-based-storage-account-connection"></a>Povezava računa za shranjevanje na podlagi naročnine

1. Odprite [skrbniški portal Azure](https://portal.azure.com), se vpišite v svojo naročnino in odprite račun za shranjevanje.

1. V levem podoknu pojdite v razdelek **Nastavitve** > **Lastnosti**.

1. Preglejte **Naročnina**, **virov**, in **ime** računa za shranjevanje, da se prepričate, da ste izbrali prave vrednosti v Customer Insights.

1. V Customer Insights izberite vrednosti za ustrezna polja, ko priložite račun za shranjevanje.

1. Nadaljujte s preostalimi koraki v Customer Insights, da priložite račun za shranjevanje.

### <a name="create-a-new-service-principal"></a>Ustvari novo glavno ime storitve

1. Namestite najnovejšo različico storitve Azure Active Directory PowerShell for Graph. Za več informacij pojdite na [Namestitev storitve Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. V računalniku pritisnite tipko Windows na tipkovnici in poiščite **Windows PowerShell** in izberite **Zaženi kot skrbnik**.

   1. V oknu PowerShell, ki se odpre, vnesite `Install-Module AzureAD`.

2. Ustvarite glavno ime storitve za Customer Insights z modulom Azure AD PowerShell.

   1. V oknu PowerShell vnesite `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Zamenjati *[vaš ID imenika]* z dejanskim ID-jem imenika vaše naročnine na Azure, kjer želite ustvariti principala storitve. Parameter z imenom okolja, `AzureEnvironmentName`, je izbiren.
  
   1. Vnesite `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Ta ukaz ustvari principal storitve za Customer Insights za izbrano naročnino Azure.

[!INCLUDE [footer-include](includes/footer-banner.md)]
