---
title: Izvozi segmente Customer Insights v Adobe Standard oglaševalske akcije (predogled)
description: Naučite se uporabljati segmente Customer Insights v Adobe Standard kampanje.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 9915591cd969bf825f5d1669de43ed4f9953f898
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082354"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Izvozi segmente Customer Insights v Adobe Standard oglaševalske akcije (predogled)

Kot uporabnik Dynamics 365 Customer Insights, ste morda ustvarili segmente, da bodo vaše marketinške kampanje učinkovitejše s ciljanjem na ustrezne ciljne skupine. Če želite uporabiti segment iz Customer Insights v Adobe Experience Platform in aplikacije, kot so Adobe Campaign Standard, morate slediti nekaj korakom, opisanim v tem članku.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagram postopka korakov, opisanih v tem članku.":::

## <a name="prerequisites"></a>Zahteve

- Licenca za Dynamics 365 Customer Insights
- Licenca za aplikacijo Adobe Campaign Standard
- Račun za shrambo zbirke dvojiških podatkov Azure

## <a name="campaign-overview"></a>Pregled akcije

Če želite bolje razumeti, kako lahko uporabite segmente iz Customer Insights v Adobe Experience Platform, poglejmo izmišljeno vzorčno kampanjo.

Predpostavimo, da vaše podjetje ponuja mesečno naročninsko storitev za vaše stranke v ZDA. Želeli boste prepoznati stranke, ki še niso podaljšale naročnine, vendar morajo to storiti v naslednjih osmih dneh. Če želite obdržati te stranke, jim po e-pošti pošljite promocijsko ponudbo z uporabo aplikacije Adobe Campaign Standard.

V tem primeru želimo promocijsko e-poštno akcijo izvesti enkrat. Ta članek ne zajema primerov uporabe večkratne izvedbe akcije. Vendar pa Customer Insights in Adobe Campaign Standard je mogoče konfigurirati tako, da deluje tudi za ponavljajoči se scenarij oglaševalske akcije.

## <a name="identify-your-target-audience"></a>Določanje ciljnega občinstva

V našem scenariju predvidevamo, da so e-poštni naslovi strank na voljo in da so bile analizirane njihove promocijske nastavitve, da se identificirajo člani segmenta.

The [segment, ki ste ga določili v Customer Insights](segments.md) je poklican **ChurnProneCustomers** in nameravate tem strankam poslati promocijo po e-pošti.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Posnetek zaslona strani s segmenti z ustvarjenim segmentom ChurnProneCustomers.":::

E-poštno sporočilo, ki ga želite poslati, bo vsebovalo ime, priimek in končni datum naročnine stranke. Stranke obvešča o popustu, ki ga bodo dobile, če bodo svojo naročnino podaljšale, še preden se konča.

## <a name="export-your-target-audience"></a>Izvoz ciljnega občinstva

### <a name="configure-a-connection"></a>Konfiguriranje povezave

Ko je naš cilj občinstvo identificiran, lahko konfiguriramo izvoz v račun Azure Blob Storage.

1. V storitvi Customer Insights pojdite na **Admin** > **Povezave**.

1. Izberite **Dodaj povezavo** in izberite **Adobe Campaign**, da konfigurirate povezavo, ali izberite **Nastavitev** v ploščici **Adobe Campaign**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfiguracijska ploščica za aplikacijo Adobe Campaign Standard.":::

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Vnesite **Ime računa**, **Ključ računa** in **Vsebnik** računa Azure Blob Storage, kamor želite izvoziti segment.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Posnetek zaslona konfiguracije računa za shrambo."::: 

   - Če želite izvedeti več o tem, kako do imena in ključa računa shrambe zbirke dvojiških podatkov Azure, si oglejte [Upravljanje nastavitev računa za shrambo na portalu storitve Azure](/azure/storage/common/storage-account-manage).

   - Če želite izvedeti, kako ustvariti vsebnik, glejte [Ustvarjanje vsebnika](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Izberite možnost **Shrani**, da dokončate povezavo.

### <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite možnost **Dodaj izvoz** za ustvarjanje novega izvoza.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku Adobe Campaign. Če se vam poimenovanje tega odseka ne prikaže, to pomeni, da vam ni na voljo nobena tovrstna povezava.

1. Izberite segment, ki ga želite izvoziti. V tem primeru je to **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Posnetek zaslona uporabniškega vmesnika za izbiro segmenta, ko je izbran segment ChurnProneCustomers.":::

1. Izberite **Naprej**.

1. Zdaj preslikamo **Vir** polja iz segmenta Customer Insights v **Tarča** imena polj v Adobe Standardna profilna shema oglaševalske akcije.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Preslikava polj za povezovalnik aplikacije Adobe Campaign Standard.":::

   Če želite dodati več atributov, izberite **Dodaj atribut**. Ciljno ime se lahko razlikuje od imena izvornega polja, tako da lahko še vedno preslikate izhod segmenta iz Customer Insights v Adobe Standardna oglaševalska akcija, če polja v obeh sistemih nimata enakega imena.

   > [!NOTE]
   > E-poštni naslov se uporablja kot polje identitete, vendar lahko uporabite kateri koli drug identifikator iz profila stranke za preslikavo podatkov v Adobe Standard kampanje.

1. Izberite **Shrani**.

Ko shranite cilj za izvoz, ga najdete v razdelku **Podatki** > **Izvoz**.

Zdaj lahko [izvozite segment na zahtevo](export-destinations.md#run-exports-on-demand). Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md).

> [!NOTE]
> Prepričajte se, da je število zapisov v izvoženem segmentu znotraj dovoljene meje vaše licence za aplikacijo Adobe Campaign Standard.

Izvoženi podatki so shranjeni v vsebniku za shrambo zbirke dvojiških podatkov Azure, ki ste ga konfigurirali zgoraj. V vsebniku se samodejno ustvari naslednja pot do mape:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp% .csv*

Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfiguracija aplikacije Adobe Campaign Standard

Izvoženi segmenti vsebujejo stolpce, ki ste jih izbrali pri določanju cilja izvoza v prejšnjem koraku. Te podatke je mogoče uporabiti, da [ustvarite profile v aplikaciji Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Če želite uporabiti segment v aplikaciji Adobe Campaign Standard, moramo razširiti shemo profila v aplikaciji Adobe Campaign Standard, da vključimo dva dodatna polja. Preberite, kako [razširite vir profila](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) z novimi polji v aplikaciji Adobe Campaign Standard.

V tem primeru gre za polja *Ime in datum segmenta (izbirno)*.

Ta polja bomo uporabili za identifikacijo profilov v aplikaciji Adobe Campaign Standard, na katere ciljamo s to akcijo.

Če ni drugih zapisov v aplikaciji Adobe Campaign Standard, razen tistega, ki ga nameravate uvoziti, lahko ta korak preskočite.

## <a name="import-data-into-adobe-campaign-standard"></a>Uvozite podatke v aplikacijo Adobe Campaign Standard

Zdaj, ko je vse na svojem mestu, moramo uvoziti pripravljene občinstvo podatke iz Customer Insights v Adobe Campaign Standard za ustvarjanje profilov. Preberite, [kako uvoziti profile v aplikacijo Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) z uporabo poteka dela.

Delovni potek uvoza na spodnji sliki je bil konfiguriran tako, da se izvaja vsakih osem ur in išče izvožene segmente Customer Insights (datoteka .csv v shrambi blobov Azure). Potek dela izvleče vsebino datoteke .csv v določenem vrstnem redu stolpcev. Ta potek dela je bil izdelan za obravnavo osnovnih napak in zagotavljanje, da ima vsak zapis e-poštni naslov, preden vnesemo podatke v aplikacijo Adobe Campaign Standard. Potek dela prav tako iz imena datoteke izvleče ime segmenta, preden ga vstavi v podatke profila aplikacije Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Posnetek zaslona poteka dela uvoza v uporabniški vmesnik aplikacije Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Pridobitev občinstva v aplikaciji Adobe Campaign Standard

Ko so podatki uvoženi v aplikacijo Adobe Campaign Standard, [lahko ustvarite potek dela](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) in [poizvedbo](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) strank na podlagi *Ime segmenta* in *Datum segmenta* za izbiro profilov, ki so bili določeni za našo vzorčno akcijo.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Ustvarjanje in pošiljanje e-poštnega sporočila z uporabo aplikacije Adobe Campaign Standard

Ustvarite e-poštno vsebino ter [preskusite in pošljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-poštno sporočilo.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Vzorec e-poštnega sporočila s ponudbo za podaljšanje iz aplikacije Adobe Campaign Standard.":::
