---
title: Povezava z računom Azure Data Lake Storage z uporabo glavnega imena storitve
description: Uporaba glavnega imena storitve Azure za povezovanje s shrambo Data Lake.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 845d1f55eb99f2adf9b437124addec4f6d016fec
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461168"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Povezava z računom Azure Data Lake Storage z uporabo glavnega imena storitve Azure
<!--note from editor: The Cloud Style Guide would have us just use "Azure Data Lake Storage" to mean the current version, unless the old version (Gen1) is mentioned. I've followed this guidance, even though it seems that our docs and Azure docs are all over the map on this.-->
Avtomatizirana orodja, ki uporabljajo storitve Azure, bi morala imeti vedno omejena dovoljenja. Namesto da bi se v aplikacije vpisali kot uporabnik s vsemi pravicami, Azure ponuja glavno ime storitve. Preberite, če želite izvedeti, kako se povezati s storitvijo Dynamics 365 Customer Insights z računom Azure Data Lake Storage tako, da uporabite glavno ime storitve Azure namesto ključev računa za shranjevanje. 

Lahko uporabite glavno ime storitve, da varno [dodate ali uredite mapo Common Data Model kot vir podatkov](connect-common-data-model.md), oz. [ustvarite ali posodobite okolje](get-started-paid.md).<!--note from editor: Suggested. Or it could be ", or create a new environment or update an existing one". I think "new" is implied with "create". The comma is necessary.-->

> [!IMPORTANT]
> - Račun storitve Data Lake Storage, ki bo uporabil<!--note from editor: Suggested. Or perhaps it could be "The Data Lake Storage account to which you want to give access to the service principal..."--> glavno ime storitve, mora imeti [omogočen hierarhičen imenski prostor](/azure/storage/blobs/data-lake-storage-namespace).
> - Za izdelavo glavnega imena storitve potrebujete skrbniška dovoljenja za naročnino Azure.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Ustvarjanje glavnega imena storitve Azure za storitev Customer Insights

Preden ustvarite novo glavno ime storitve za vpoglede občinstva ali vpoglede v interakcije, preverite, ali v vaši organizaciji že obstaja.

### <a name="look-for-an-existing-service-principal"></a>Poiščite obstoječega glavnega imena storitve

1. Odprite [skrbniški portal Azure](https://portal.azure.com) in se vpišite v svojo organizacijo.

2. Iz **storitev Azure** izberite **Azure Active Directory**.

3. Pod možnostjo **Upravljanje** izberite **Aplikacije za podjetja**.

4. Iskanje za Microsoft<!--note from editor: Via Microsoft Writing Style Guide.--> ID aplikacije:
   - Vpogledi občinstva: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` z imenom `Dynamics 365 AI for Customer Insights`
   - Vpogledi v interakcije: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` z imenom `Dynamics 365 AI for Customer Insights engagement insights`

5. Če najdete ujemajoči se zapis, to pomeni, da glavno ime storitve že obstaja. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Posnetek zaslona, ki prikazuje obstoječe glavno ime storitve.":::
   
6. Če se ne vrnejo nobeni rezultati, ustvarite novo glavno ime storitve.

>[!NOTE]
>Če želite izkoristiti vse možnosti storitve Dynamics 365 Customer Insights, predlagamo, da obe aplikaciji dodate glavnemu imenu storitve.<!--note from editor: Using the note format is suggested, just so this doesn't get lost by being tucked up in the step.-->

### <a name="create-a-new-service-principal"></a>Ustvari novo glavno ime storitve
<!--note from editor: Some general formatting notes: The MWSG wants bold for text the user enters (in addition to UI strings and the settings users select), but there's plenty of precedent for using code format for entering text in PowerShell so I didn't change that. Note that italic should be used for placeholders, but not much else.-->
1. Namestite najnovejšo različico storitve Azure Active Directory PowerShell for Graph. Za več informacij pojdite na [Namestitev storitve Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. V računalniku izberite tipko Windows na tipkovnici in poiščite **Windows PowerShell** in izberite **Zaženi kot skrbnik**.<!--note from editor: Or should this be something like "search for **Windows PowerShell** and, if asked, select **Run as administrator**."?-->
   
   1. V oknu PowerShell, ki se odpre, vnesite `Install-Module AzureAD`.

2. Ustvarite glavno ime storitve za Customer Insights z modulom Azure AD PowerShell.

   1. V oknu PowerShell vnesite `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Zamenjajte *»[svoj ID najemnika]«*<!--note from editor: Edit okay? Or should the quotation marks stay in the command line, in which case it would be "Replace *[your tenant ID]* --> z dejanskim ID-jem vašega najemnika, za katerega želite ustvariti glavno ime storitve. Parameter z imenom okolja, `AzureEnvironmentName`, je izbiren.
  
   1. Vnesite `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Ta ukaz ustvari glavno ime storitve za vpoglede v občinstvo izbranega najemnika. 

   1. Vnesite `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Ta ukaz ustvari glavno ime storitve za vpoglede v interakcije<!--note from editor: Edit okay?--> v izbranem najemniku.

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

Lahko<!--note from editor: Edit suggested only if this section is optional.--> priložite račun storitve Data Lake Storage v vpogledih občinstva, da [shranite izhodne podatke](manage-environments.md) ali [ga uporabite kot vir podatkov](connect-common-data-service-lake.md). Ta možnost vam omogoča izbiro med pristopom, ki temelji na virih, ali pristopom, ki temelji na naročnini. Odvisno od pristopa, ki ga izberete, sledite postopku v enem od naslednjih razdelkov.<!--note from editor: Suggested.-->

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