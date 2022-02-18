---
title: Povezava z računom Azure Data Lake Storage z uporabo glavnega imena storitve
description: Uporaba glavnega imena storitve Azure za povezovanje s shrambo Data Lake.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 1af01e5579f85d7c8bc8976a003f53ef2dd280d1
ms.sourcegitcommit: b7189b8621e66ee738e4164d4b3ce2af0def3f51
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/03/2022
ms.locfileid: "8088167"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Povezava z računom Azure Data Lake Storage z uporabo glavnega imena storitve Azure

Ta članek govori o tem, kako povezati Dynamics 365 Customer Insights z Azure Data Lake Storage račun z uporabo principala storitve Azure namesto ključev računa za shranjevanje. 

Avtomatizirana orodja, ki uporabljajo storitve Azure, bi morala imeti vedno omejena dovoljenja. Namesto da bi se v aplikacije vpisali kot uporabnik s vsemi pravicami, Azure ponuja glavno ime storitve. Za varno lahko uporabite principe storitev [dodajte ali uredite mapo skupnega podatkovnega modela kot vir podatkov](connect-common-data-model.md) oz [ustvarite ali posodobite okolje](create-environment.md).

> [!IMPORTANT]
> - Račun Data Lake Storage, ki bo uporabljal principala storitve, mora biti Gen2 in imeti [Imenski prostor hierarhičen je omogočen](/azure/storage/blobs/data-lake-storage-namespace). Računi za shranjevanje podatkov Azure Data Lake Gen1 niso podprti.
> - Za ustvarjanje principala storitve potrebujete skrbniška dovoljenja za svojo naročnino na Azure.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Ustvarjanje glavnega imena storitve Azure za storitev Customer Insights

Preden ustvarite novega principala storitve za Customer Insights, preverite, ali že obstaja v vaši organizaciji.

### <a name="look-for-an-existing-service-principal"></a>Poiščite obstoječega glavnega imena storitve

1. Odprite [skrbniški portal Azure](https://portal.azure.com) in se vpišite v svojo organizacijo.

2. Iz **storitev Azure** izberite **Azure Active Directory**.

3. Pod možnostjo **Upravljanje** izberite **Aplikacije za podjetja**.

4. Poiščite ID Microsoftove aplikacije:
   - Vpogledi občinstva: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` z imenom `Dynamics 365 AI for Customer Insights`
   - Vpogledi v interakcije: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` z imenom `Dynamics 365 AI for Customer Insights engagement insights`

5. Če najdete ujemajoči se zapis, to pomeni, da glavno ime storitve že obstaja. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Posnetek zaslona, ki prikazuje obstoječe glavno ime storitve.":::
   
6. Če se ne vrnejo nobeni rezultati, ustvarite novo glavno ime storitve.

>[!NOTE]
>Če želite izkoristiti vse možnosti storitve Dynamics 365 Customer Insights, predlagamo, da obe aplikaciji dodate glavnemu imenu storitve.

### <a name="create-a-new-service-principal"></a>Ustvari novo glavno ime storitve

1. Namestite najnovejšo različico storitve Azure Active Directory PowerShell for Graph. Za več informacij pojdite na [Namestitev storitve Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. V računalniku izberite tipko Windows na tipkovnici in poiščite **Windows PowerShell** in izberite **Zaženi kot skrbnik**.
   
   1. V oknu PowerShell, ki se odpre, vnesite `Install-Module AzureAD`.

2. Ustvarite glavno ime storitve za Customer Insights z modulom Azure AD PowerShell.

   1. V oknu PowerShell vnesite `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Zamenjajte *[ID vašega najemnika]* z dejanskim ID-jem vašega najemnika, kjer želite ustvariti glavno ime storitve. Parameter z imenom okolja, `AzureEnvironmentName`, je izbiren.
  
   1. Vnesite `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Ta ukaz ustvari glavno ime storitve za vpoglede v občinstvo izbranega najemnika. 

   1. Vnesite `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Ta ukaz ustvari glavno ime storitve za vpoglede v interakcije v izbranem najemniku.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Dodelite dovoljenja glavnemu imenu storitve za dostop do računa za shranjevanje

Pojdite na portal Azure, da dodelite dovoljenja glavnemu imenu storitve za račun za shranjevanje, ki ga želite uporabiti pri vpogledih v občinstvo.

1. Odprite [skrbniški portal Azure](https://portal.azure.com) in se vpišite v svojo organizacijo.

1. Odprite račun za shranjevanje, do katerega želite, da ima glavno ime storitve dostop za vpoglede v občinstvo.

1. V levem podoknu izberite **Nadzor dostopa (IAM)** in nato izberite **Dodaj** > **Dodaj dodelitev vloge**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Posnetek zaslona, ki prikazuje portal Azure med dodajanjem dodelitve vloge.":::

1. V podoknu **Dodaj dodelitev vlog** nastavite naslednje lastnosti:
   - Vloga: **Sodelujoči v shrambi zbirke dvojiških podatkov**
   - Dodeli dostop za: **uporabnik, skupina ali glavno ime storitve**
   - Izberite: **Dynamics 365 AI za storitev Customer Insights** in **Dynamics 365 AI za vpoglede v interakcije storitve Customer Insights** (dve [glavni imeni storitve](#create-a-new-service-principal), ki ste ju ustvarili prej v tem postopku)

1.  Izberite **Shrani**.

Uvedba sprememb lahko traja do 15 minut.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>V priponko računa za shranjevanje za vpoglede občinstva vnesite ID vira Azure ali podrobnosti o naročnini za Azure

V vpogledih v občinstvo lahko priložite račun za storitev Data Lake Storage, da [shranite izhodne podatke](manage-environments.md) ali [ga uporabite kot vir podatkov](connect-common-data-service-lake.md). Ta možnost vam omogoča izbiro med pristopom, ki temelji na virih, ali pristopom, ki temelji na naročnini. Odvisno od pristopa, ki ga izberete, sledite postopku v enem od naslednjih razdelkov.

### <a name="resource-based-storage-account-connection"></a>Povezava računa za shrambo na podlagi vira

1. Odprite [skrbniški portal Azure](https://portal.azure.com), se vpišite v svojo naročnino in odprite račun za shranjevanje.

1. V levem podoknu pojdite v razdelek **Nastavitve** > **Lastnosti**.

1. Kopirajte vrednost ID-ja vira računa za shranjevanje.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopirajte ID vira računa za shranjevanje.":::

1. V vpoglede občinstva vstavite ID vira v polje vira, prikazano na zaslonu za povezavo računa za shranjevanje.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Vnesite podatke za ID vira računa za shranjevanje.":::   

1. Nadaljujte s preostalimi koraki pri vpogledih v občinstvo, da pripnete račun za shranjevanje.

### <a name="subscription-based-storage-account-connection"></a>Povezava računa za shranjevanje na podlagi naročnine

1. Odprite [skrbniški portal Azure](https://portal.azure.com), se vpišite v svojo naročnino in odprite račun za shranjevanje.

1. V levem podoknu pojdite v razdelek **Nastavitve** > **Lastnosti**.

1. Preglejte **naročnino**, **skupino virov** in **ime** računa za shranjevanje, da se prepričate, da ste izbrali prave vrednosti pri vpogledih v občinstvo.

1. V vpogledih občinstva izberite vrednosti za ustrezna polja, ko prilagate račun za shranjevanje.

1. Nadaljujte s preostalimi koraki pri vpogledih v občinstvo, da pripnete račun za shranjevanje.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
