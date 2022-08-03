---
title: Izvozi segmente Customer Insights v Adobe Standardna akcija (predogled)
description: Naučite se uporabljati segmente Customer Insights v Adobe Standardna akcija.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195540"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Izvozi segmente Customer Insights v Adobe Standardna akcija (predogled)

Izvozite segmente, ki ciljajo na ustrezne ciljne skupine Adobe Standardna akcija.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagram postopka korakov, opisanih v tem članku.":::

## <a name="prerequisites"></a>Zahteve

- An Adobe Standardna licenca oglaševalske akcije.
- An [Račun Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) ime in ključ računa. Za iskanje imena in ključa glejte [Upravljajte nastavitve računa za shranjevanje na portalu Azure](/azure/storage/common/storage-account-manage).
- An [Vsebnik za shranjevanje podatkov Azure Blob](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Pregled akcije

Da bi bolje razumeli, kako lahko uporabite segmente iz storitve Customer Insights v Adobe Experience Platform, poglejmo fiktivno vzorčno akcijo.

Predpostavimo, da vaše podjetje ponuja mesečno naročninsko storitev za vaše stranke v ZDA. Želeli boste prepoznati stranke, ki še niso podaljšale naročnine, vendar morajo to storiti v naslednjih osmih dneh. Če želite obdržati te stranke, jim po e-pošti pošljite promocijsko ponudbo z uporabo aplikacije Adobe Campaign Standard.

V tem primeru želimo promocijsko e-poštno akcijo izvesti enkrat. Ta članek ne zajema primerov uporabe večkratne izvedbe akcije. Vendar Customer Insights in Adobe Campaign Standard je mogoče konfigurirati tako, da deluje tudi za scenarij ponavljajoče se oglaševalske akcije.

## <a name="identify-your-target-audience"></a>Določanje ciljnega občinstva

V našem scenariju predvidevamo, da so e-poštni naslovi strank na voljo v Customer Insights in da so bile njihove promocijske nastavitve analizirane, da bi identificirali člane segmenta.

The [segment, ki ste ga definirali v Customer Insights](segments.md) je poklican **ChurnProneCustomers** in tem strankam nameravate poslati e-poštno promocijo.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Posnetek zaslona strani s segmenti z ustvarjenim segmentom ChurnProneCustomers.":::

E-poštno sporočilo, ki ga želite poslati, bo vsebovalo ime, priimek in končni datum naročnine stranke. Stranke obvešča o popustu, ki ga bodo dobile, če bodo svojo naročnino podaljšale, še preden se konča.

## <a name="export-your-target-audience"></a>Izvoz ciljnega občinstva

### <a name="set-up-connection-to-adobe-campaign"></a>Nastavite povezavo z Adobe Kampanja

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **Adobe Kampanja**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto jo lahko uporabljajo samo skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vnesite **Ime računa**, **računa**, in **Posoda** za vaš račun Blob Storage.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Posnetek zaslona konfiguracije računa za shrambo.":::

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite možnost **Shrani**, da dokončate povezavo.

### <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku Adobe Campaign. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Vnesite ime za izvoz.

1. Izberite segment, ki ga želite izvoziti. V tem primeru je to **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Posnetek zaslona uporabniškega vmesnika za izbiro segmenta, ko je izbran segment ChurnProneCustomers.":::

1. Izberite **Naprej**.

1. Zemljevid **Vir** polja od segmenta Customer Insights do **Tarča** imena polj v Adobe Standardna shema profila oglaševalske akcije.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Preslikava polj za povezovalnik aplikacije Adobe Campaign Standard.":::

   Če želite dodati več atributov, izberite **Dodaj atribut**. Ciljno ime se lahko razlikuje od imena izvornega polja, tako da lahko vseeno preslikate izhod segmenta iz Customer Insights v Adobe Campaign Standard, če polja nimajo enakega imena v obeh sistemih.

   > [!NOTE]
   > E-poštni naslov se uporablja kot polje identitete, vendar lahko za preslikavo podatkov uporabite kateri koli drug identifikator iz profila stranke Adobe Standardna akcija.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Prepričajte se, da je število zapisov v izvoženem segmentu znotraj dovoljene meje vaše licence za aplikacijo Adobe Campaign Standard.

Izvoženi podatki so shranjeni v vsebniku za shrambo zbirke dvojiških podatkov Azure, ki ste ga konfigurirali zgoraj. V vašem vsebniku se samodejno ustvari naslednja pot do mape: *%ContainerName% /CustomerInsights_%instanceID% /% ime izvozne destinacije%_%segmentname%_%timestamp% .csv*

Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfiguracija aplikacije Adobe Campaign Standard

Izvoženi segmenti vsebujejo stolpce, ki ste jih izbrali med konfiguracijo izvoza. Te podatke je mogoče uporabiti, da [ustvarite profile v aplikaciji Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Za uporabo segmenta v Adobe Standardna akcija, [razširite shemo profila](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) v Adobe Campaign Standard za vključitev dveh dodatnih polj.

V našem primeru sta ti polji Ime segmenta in Datum segmenta. Ta polja bomo uporabili za identifikacijo profilov v aplikaciji Adobe Campaign Standard, na katere ciljamo s to akcijo.

Če ni drugih zapisov v Adobe Campaign Standard, razen tistega, kar boste uvozili, preskočite ta korak.

## <a name="import-data-into-adobe-campaign-standard"></a>Uvozite podatke v aplikacijo Adobe Campaign Standard

Uvozite pripravljene podatke občinstvo iz Customer Insights v Adobe Kampanja Standard do [ustvarite profile z uporabo delovnega toka](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

Delovni tok uvoza na spodnji sliki je bil konfiguriran tako, da se izvaja vsakih osem ur in išče izvožene segmente Customer Insights (datoteka .csv v Azure Blob Storage). Potek dela izvleče vsebino datoteke .csv v določenem vrstnem redu stolpcev. Ta potek dela je bil izdelan za obravnavo osnovnih napak in zagotavljanje, da ima vsak zapis e-poštni naslov, preden vnesemo podatke v aplikacijo Adobe Campaign Standard. Potek dela prav tako iz imena datoteke izvleče ime segmenta, preden ga vstavi v podatke profila aplikacije Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Posnetek zaslona poteka dela uvoza v uporabniški vmesnik aplikacije Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Pridobitev občinstva v aplikaciji Adobe Campaign Standard

Ko so podatki uvoženi v Adobe Standardna oglaševalska akcija, [ustvarite potek dela](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) in [poizvedbo](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) stranke na podlagi imena segmenta in datuma segmenta za izbiro profilov, ki so bili identificirani za našo vzorčno akcijo.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Ustvarjanje in pošiljanje e-poštnega sporočila z uporabo aplikacije Adobe Campaign Standard

Ustvarite e-poštno vsebino ter [preskusite in pošljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-poštno sporočilo.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Vzorec e-poštnega sporočila s ponudbo za podaljšanje iz aplikacije Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
