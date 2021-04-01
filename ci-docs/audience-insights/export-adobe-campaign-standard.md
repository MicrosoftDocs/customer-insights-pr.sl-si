---
title: Izvoz podatkov iz storitve Customer Insights v aplikacijo Adobe Campaign Standard
description: Preberite, kako uporabljati segmente vpogleda v občinstvo v aplikaciji Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596335"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Uporaba segmentov storitve Customer Insights v aplikaciji Adobe Campaign Standard (predogledna različica)

Kot uporabnik vpogledov v občinstvo za Dynamics 365 Customer Insights ste morda ustvarili segmente za izboljšanje učinkovitosti svojih trženjskih akcij s ciljanjem na ustrezno občinstvo. Če želite uporabiti segment iz vpogledov v občinstvo na platformi Adobe Experience Platform in v aplikacijah, kot je Adobe Campaign Standard, morate slediti nekaj korakom, ki so opisani v tem članku.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagram postopka korakov, opisanih v tem članku.":::

## <a name="prerequisites"></a>Zahteve

-   Licenca za Dynamics 365 Customer Insights
-   Licenca aplikacije Adobe Campaign Standard
-   Račun za shrambo zbirke dvojiških podatkov Azure

## <a name="campaign-overview"></a>Pregled akcije

Da boste bolje razumeli, kako lahko uporabite segmente iz vpogledov v občinstvo na platformi Adobe Experience Platform, si oglejmo izmišljeno vzorčno akcijo.

Predpostavimo, da vaše podjetje ponuja mesečno naročninsko storitev za vaše stranke v ZDA. Želeli boste prepoznati stranke, ki še niso podaljšale naročnine, vendar morajo to storiti v naslednjih osmih dneh. Če želite obdržati te stranke, jim pošljite promocijsko ponudbo po e-pošti prek aplikacije Adobe Campaign Standard.

V tem primeru želimo promocijsko e-poštno akcijo izvesti enkrat. Ta članek ne zajema primerov uporabe večkratne izvedbe akcije. Vendar lahko vpoglede v občinstvo in aplikacijo Adobe Campaign Standard nastavite tako, da delujejo tudi za ponavljajoči se scenarij akcije.

## <a name="identify-your-target-audience"></a>Določanje ciljnega občinstva

V našem scenariju predpostavljamo, da so e-poštni naslovi strank na voljo v vpogledih v občinstvo in da so bile njihove promocijske nastavitve analizirane za prepoznavanje članov segmenta.

[Segment, ki ste ga opredelili v vpogledih v občinstvo](segments.md), se imenuje **ChurnProneCustomers** in tem strankam nameravate poslati e-poštno promocijo.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Posnetek zaslona strani s segmenti z ustvarjenim segmentom ChurnProneCustomers.":::

E-poštno sporočilo, ki ga želite poslati, bo vsebovalo ime, priimek in končni datum naročnine stranke. Stranke obvešča o popustu, ki ga bodo dobile, če bodo svojo naročnino podaljšale, še preden se konča.

## <a name="export-your-target-audience"></a>Izvoz ciljnega občinstva

Ko je ciljno občinstvo določeno, lahko konfiguriramo izvoz iz vpogledov v občinsto v račun za shrambo zbirke dvojiških podatkov Azure.

1. Pri vpogledih v občinstvo izberite **Skrbnik** > **Cilji izvoza**.

1. Na ploščici **Adobe Campaign** izberite **Nastavi**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfiguracijska ploščica za Adobe Campaign Standard.":::

1. Navedite **prikazno ime** za novi cilj izvoza ter vnesite **ime računa**, **ključ računa** in **vsebnik** računa za shrambo zbirke dvojiških podatkov Azure, kamor želite izvoziti segment.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Posnetek zaslona konfiguracije računa za shrambo. "::: 

   - Če želite izvedeti več o tem, kako najti ime in ključ računa za shrambo zbirke dvojiških podatkov Azure, glejte [Upravljanje nastavitev računa za shrambo na portalu storitve Azure](/azure/storage/common/storage-account-manage).

   - Če želite izvedeti, kako ustvariti vsebnik, glejte [Ustvarjanje vsebnika](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Izberite **Naprej**.

1. Izberite segment, ki ga želite izvoziti. V tem primeru je to **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Posnetek zaslona uporabniškega vmesnika za izbiro segmenta, ko je izbran segment ChurnProneCustomers.":::

1. Izberite **Naprej**.

1. Zdaj preslikamo **izvorna** polja iz segmenta vpogledov v občinstvo v ime **ciljnega** polja v shemi profilov Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Preslikava polj za povezovalnik Adobe Campaign Standard.":::

   Če želite dodati več atributov, izberite **Dodaj atribut**. Ciljno ime je lahko drugačno od izvornega imena polja, zato lahko preslikate izhod segmenta iz vpogledov v občinstvo v aplikacijo Adobe Campaign Standard, če polja v sistemih nimajo enakega imena.

   > [!NOTE]
   > E-poštni naslov se uporablja kot polje identitete, vendar lahko uporabljate kateri koli drug identifikator iz profila stranke v vpogledih v občinstvo za preslikavo podatkov v aplikacijo Adobe Campaign Standard.

1. Izberite **Shrani**.

Ko shranite cilj izvoza, ga najdete v možnosti **Skrbnik** > **Izvozi** > **Moji cilji izvoza**.

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Posnetek zaslona z označenim seznamom izvozov in vzorčnim segmentom.":::

Zdaj lahko [izvozite segment na zahtevo](export-destinations.md#export-data-on-demand). Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md).

> [!NOTE]
> Prepričajte se, da je število zapisov v izvoženem segmentu znotraj dovoljene omejitve vaše licence Adobe Campaign Standard.

Izvoženi podatki so shranjeni v vsebniku za shrambo zbirke dvojiških podatkov Azure, ki ste ga konfigurirali zgoraj. V vsebniku se samodejno ustvari naslednja pot do mape:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp% .csv*

Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfiguracija aplikacije Adobe Campaign Standard

Ko je segment iz vpogledov v občinstvo izvožen, vsebuje stolpce, ki ste jih izbrali pri določanju cilja izvoza v prejšnjem koraku. Te podatke je mogoče uporabiti za [ustvarjanje profilov v aplikaciji Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Če želimo segment uporabiti v aplikaciji Adobe Campaign Standard, moramo razširiti shemo profilov v aplikaciji Adobe Campaign Standard, da bo vključevala še dve dodatni polji. Preberite, kako [razširite vir profila](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) z novimi polji v aplikaciji Adobe Campaign Standard.

V našem primeru so to polja *Ime in datum segmenta (izbirno).*

Ta polja bomo uporabili za prepoznavanje profilov v aplikaciji Adobe Campaign Standard, na katere želimo ciljati pri tej akciji.

Če v aplikaciji Adobe Campaign Standard ni drugih zapisov, razen tistega, ki ga boste uvozili, lahko ta korak preskočite.

## <a name="import-data-into-adobe-campaign-standard"></a>Uvoz podatkov v aplikacijo Adobe Campaign Standard

Zdaj, ko je vse na svojem mestu, moramo iz vpogledov v občinstvo v aplikacijo Adobe Campaign Standard uvoziti pripravljene podatke o občinstvu za ustvarjanje profilov. Preberite, [kako uvoziti profile v aplikacijo Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) s potekom dela.

Potek dela uvoza na spodnji sliki je konfiguriran za zagon vsakih 8 ur in išče izvožene segmente vpogledov v občinstvo (datoteka .csv v shrambi zbirke dvojiških podatkov Azure). Potek dela izvleče vsebino datoteke .csv v določenem vrstnem redu stolpcev. Ta potek dela je bil zgrajen tako, da izvaja osnovno obravnavanje napak in zagotavlja, da ima vsak zapis e-poštni naslov, preden podatke hidrira v aplikacijo Adobe Campaign Standard. Potek dela izvleče tudi ime segmenta iz imena datoteke, preden ga vstavi v podatke profila ACS.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Posnetek zaslona poteka dela uvoza v uporabniškem vmesniku aplikacije Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Pridobivanje občinstva v aplikaciji Adobe Campaign Standard

Ko so podatki uvoženi v aplikacijo Adobe Campaign Standard, [lahko ustvarite potek dela](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) in [poizvedbo](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) stranke na podlagi *Imena segmenta* in *Datuma segmenta*, da izberete profile, ki so bili določeni za našo vzorčno akcijo.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Ustvarjanje in pošiljanje e-poštnih sporočil z aplikacijo Adobe Campaign Standard

Ustvarite e-poštno vsebino ter [preskusite in pošljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-poštno sporočilo.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Vzorec e-poštnega sporočila s ponudbo za obnovitev iz aplikacije Adobe Campaign Standard.":::