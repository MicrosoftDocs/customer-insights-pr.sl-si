---
title: Povezovanje računa Azure Data Lake Storage Gen2 z glavnim imenom storitve
description: Uporabite glavno ime storitve Azure za vpoglede v občinstvo, da se povežete z lastnim jezerom podatkov, ko ga priložite vpogledom v občinstvo.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: cc94ad49f12067d513db4663bff60620d6501eb0
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692133"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Povezovanje računa Azure Data Lake Storage Gen2 z glavnim imenom storitve Azure za vpoglede v občinstvo

Avtomatizirana orodja, ki uporabljajo storitve Azure, bi morala imeti vedno omejena dovoljenja. Namesto da bi se v aplikacije vpisali kot uporabnik s vsemi pravicami, Azure ponuja glavno ime storitve. Preberite nadaljevanje, če želite izvedeti, kako povezati vpogled v občinstvo z računom Azure Data Lake Storage Gen2, ki uporablja glavno ime storitve Azure namesto ključev računa za shranjevanje. 

Z glavnim imenom storitve lahko varno [dodate ali uredite mapo Common Data Model kot vir podatkov](connect-common-data-model.md) ali [ustvarite novo oz. posodobite obstoječe okolje](get-started-paid.md).

> [!IMPORTANT]
> - Račun za shrambo Azure Data Lake Gen2, ki namerava uporabiti glavno ime storitve, mora imeti [omogočeno funkcijo hierarhičnega imenskega prostora (HNS)](/azure/storage/blobs/data-lake-storage-namespace).
> - Za izdelavo glavnega imena storitve potrebujete skrbniška dovoljenja za naročnino Azure.

## <a name="create-azure-service-principal-for-audience-insights"></a>Ustvarjanje glavnega imena storitve Azure za vpoglede v občinstvo

Preden ustvarite novega glavnega imena storitve za vpoglede v občinstvo, preverite, ali ta že obstaja v vaši organizaciji.

### <a name="look-for-an-existing-service-principal"></a>Poiščite obstoječega glavnega imena storitve

1. Odprite [skrbniški portal Azure](https://portal.azure.com) in se vpišite v svojo organizacijo.

2. Izberite **Azure Active Directory** pri storitvah Azure.

3. Pod možnostjo **Upravljanje** izberite **Aplikacije za podjetja**.

4. Poiščite ID lastne aplikacije za vpoglede v občinstvo `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ali ime `Dynamics 365 AI for Customer Insights`.

5. Če najdete ustrezen zapis, to pomeni, da glavno ime storitve za vpoglede v občinstvo obstaja. Ni vam ga treba ustvariti znova.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Posnetek zaslona, ki prikazuje obstoječe glavno ime storitve.":::
   
6. Če se ne vrnejo nobeni rezultati, ustvarite novo glavno ime storitve.

### <a name="create-a-new-service-principal"></a>Ustvari novo glavno ime storitve

1. Namestite najnovejšo različico **Azure Active Directory PowerShell for Graph**. Za več informacij glejte [Namestitev storitve Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).
   - V računalniku izberite tipko Windows na tipkovnici in poiščite možnosti **Windows PowerShell** in **Zaženi kot skrbnik**.
   
   - V oknu PowerShell, ki se odpre, vnesite `Install-Module AzureAD`.

2. Ustvarite glavno ime storitve za vpoglede v občinstvo z modulom Azure AD PowerShell.
   - V oknu PowerShell vnesite `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Zamenjajte vaš ID najemnika z dejanskim ID-jem vašega najemnika, kjer želite ustvariti glavno ime storitve. Parameter z imenom okolja `AzureEnvironmentName` je izbiren.
  
   - Vnesite `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Ta ukaz ustvari glavno ime storitve za vpoglede v občinstvo izbranega najemnika.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Dodelite dovoljenja glavnemu imenu storitve za dostop do računa za shranjevanje

Pojdite na portal Azure, da dodelite dovoljenja glavnemu imenu storitve za račun za shranjevanje, ki ga želite uporabiti pri vpogledih v občinstvo.

1. Odprite [skrbniški portal Azure](https://portal.azure.com) in se vpišite v svojo organizacijo.

1. Odprite račun za shranjevanje, do katerega želite, da ima glavno ime storitve dostop za vpoglede v občinstvo.

1. Izberite **Nadzor dostopa (IAM)** v podoknu za krmarjenje in izberite **Dodaj** > **Dodaj dodelitev vloge**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Posnetek zaslona, ki prikazuje portal Azure med dodajanjem dodelitve vloge.":::
   
1. V podoknu **Dodaj dodelitev vloge** nastavite naslednje lastnosti:
   - Vloga: *Sodelujoči v shrambi zbirke dvojiških podatkov*
   - Dodeli dostop za: *uporabnik, skupina ali glavno ime storitve*
   - Izberite: *Dynamics 365 AI for Customer Insights* ([glavno ime storitve, ki ste ga ustvarili](#create-a-new-service-principal))

1.  Izberite **Shrani**.

Uvedba sprememb lahko traja do 15 minut.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>V priponko računa za shranjevanje za vpoglede v občinstvo vnesite ID vira Azure ali podrobnosti o naročnini za Azure.

Priložite račun za shrambo Azure Data Lake v vpoglede v občinstvo, da [shranite izhodne podatke](manage-environments.md) ali to [uporabite kot vir podatkov](connect-dataverse-managed-lake.md). Če izberete možnost Azure Data Lake, lahko izbirate med pristopom na podlagi virov ali na podlagi naročnine.

Upoštevajte naslednja navodila, da posredujete zahtevane podatke o izbranem pristopu.

### <a name="resource-based-storage-account-connection"></a>Povezava računa za shrambo na podlagi vira

1. Odprite [skrbniški portal Azure](https://portal.azure.com), se vpišite v svojo naročnino in odprite račun za shranjevanje.

1. Odprite **Nastavitve** > **Lastnosti** v podoknu za krmarjenje.

1. Kopirajte vrednost ID-ja vira računa za shranjevanje.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopirajte ID vira računa za shranjevanje.":::

1. Pri vpogledih v občinstvo vstavite ID vira v polje vira, prikazano na zaslonu povezave z računom za shranjevanje.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Vnesite podatke za ID vira računa za shranjevanje.":::   
   
1. Nadaljujte s preostalimi koraki pri vpogledih v občinstvo, da pripnete račun za shranjevanje.

### <a name="subscription-based-storage-account-connection"></a>Povezava računa za shranjevanje na podlagi naročnine

1. Odprite [skrbniški portal Azure](https://portal.azure.com), se vpišite v svojo naročnino in odprite račun za shranjevanje.

1. Odprite **Nastavitve** > **Lastnosti** v podoknu za krmarjenje.

1. Preglejte **naročnino**, **skupino virov** in **ime** računa za shranjevanje, da se prepričate, da ste izbrali prave vrednosti pri vpogledih v občinstvo.

1. Pri vpogledih v občinstvo izberite vrednosti ali ustrezna polja, ko pripnete račun za shranjevanje.
   
1. Nadaljujte s preostalimi koraki pri vpogledih v občinstvo, da pripnete račun za shranjevanje.


[!INCLUDE[footer-include](../includes/footer-banner.md)]