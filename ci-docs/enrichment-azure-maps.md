---
title: Obogatitev profilov strank s podatki o lokaciji iz storitve Zemljevidi Azure
description: Splošne informacije o obogatitvi proizvajalca storitve Zemljevidi Azure.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a806b2d0c791972c967c90694527608b4def9f3f
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953648"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Obogatitev profilov strank s storitvijo Zemljevidi Azure (predogledna različica)

Zemljevidi Azure zagotavljajo podatke in storitve, osredotočene na lokacijo, za zagotavljanje izkušenj na podlagi geoprostorskih podatkov z vgrajeno lokacijsko inteligenco. Storitve obogatitve podatkov v storitvi Zemljevidi Azure izboljšajo natančnost podatkov o lokaciji vaših strank. Prinaša zmogljivosti, kot so normaliziranje naslovov ter ekstrahiranje zemljepisne širine in dolžine v storitev Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Zahteve

- Aktivna naročnina na Azure Maps. Če želite dobiti naročnino, [prijavite se ali si zagotovite brezplačen preizkus](https://azure.microsoft.com/services/azure-maps/).

- Azurni zemljevidi [povezavo](connections.md) je [konfiguriran](#configure-the-connection-for-azure-maps) s strani skrbnika.

## <a name="configure-the-connection-for-azure-maps"></a>Konfiguriranje povezave za storitev Zemljevidi Azure

Moraš biti [skrbnik](permissions.md#admin) v Customer Insights in imeti aktiven ključ API-ja za zemljevide Azure.

1. Pri konfiguriranju obogatitve izberite možnost **Dodaj povezavo** ali pa odprite razdelek **Skrbnik** > **Povezave** ter v ploščici storitve Zemljevidi Azure izberite **Nastavitev**.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Stran za konfiguracijo povezave za storitev Zemljevidi Azure.":::

1. Vnesite ime za povezavo in veljaven ključ API-ja za zemljevide Azure.

1. Preglejte in podajte soglasje, tako da v razdelku [Zasebnost in skladnost podatkov](#data-privacy-and-compliance) izberete možnost **Strinjam se**.

1. Izberite **Preverite** da preverite konfiguracijo in nato izberite **Shrani**.

### <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

S tem ko dovolite, da storitev Dynamics 365 Customer Insights podatke prenese storitvi Zemljevidi Azure, omogočite prenos podatkov zunaj omejitve skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo te podatke prenesel po vaših navodilih, vendar ste odgovorni za zagotovitev, da Azure Maps izpolnjujejo morebitne obveznosti glede zasebnosti ali varnosti. Za več informacij pojdite na [Microsoftova izjava o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadar koli odstrani in s tem prekini uporabo te funkcije.

## <a name="configure-the-enrichment"></a>Konfiguriranje obogatitve

1. Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.

1. Izberite **Obogatite moje podatke** na **Lokacija** od Microsoft Azure Ploščica zemljevidov.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Ploščica za storitev Zemljevidi Azure.":::

1. Preglejte pregled in nato izberite **Naslednji**.

1. Izberite povezavo. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Izberite **Naprej**.

1. Izberite **Stranka nabor podatkov** in izberite profil ali segment, ki ga želite obogatiti s podatki iz Microsofta. The *Stranka* entiteta obogati vse vaše profile strank, medtem ko segment obogati samo profile strank, ki jih vsebuje ta segment.

1. Določite, katero vrsto polj iz svojih enotnih profilov želite uporabiti za ujemanje: primarni in/ali sekundarni naslov. Za oba naslova lahko določite preslikavo polj in obogatite profile za vsak naslov posebej. Na primer za domači naslov in poslovni naslov. Izberite **Naprej**.

1. Preslikajte svoja polja na podatki o lokaciji iz Azure Maps. Polji **Ulica 1** in **Poštna številka** sta obvezni za izbrani primarni in/ali sekundarni naslov. Za večjo natančnost ujemanja dodajte več polj.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Preslikava atributov Azure Maps.":::

1. Izberite možnost **Naprej**, da dokončate preslikavo polj.

1. Pregled **Napredne nastavitve** ki ponujajo največjo prilagodljivost za obravnavo naprednih primerov uporabe. Vendar naslednjih privzetih vrednosti običajno ni treba spreminjati.

   - **Vrsta naslovov** : Vrne se najboljše ujemanje naslova, tudi če je nepopolno. Če želite pridobit samo popolne naslove, na primer naslove, ki vključujejo hišno številko, počistite vsa potrditvena polja razen **Naslovi točke**.
   - **Jezik** : Naslovi se vrnejo v jeziku, ki temelji na naslovnem območju. Če želite uporabiti standardiziran jezik naslova, v spustnem meniju izberite jezik. Na primer, izbiranje **angleščina** vrne **Kopenhagen, Danska** namesto **København, Danska**.
   - **Največje število rezultatov** : Število rezultatov na naslov.

1. Izberite **Naprej**.

1. Zagotovite a **ime** za obogatitev in **Ime izhodne entitete**.

1. Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.

1. Izberite **teci** za začetek procesa obogatitve ali blizu vrnitve na **Obogatitve** stran.

## <a name="enrichment-results"></a>Rezultati obogatitve

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

The **Število kupcev, obogatenih po področjih** zagotavlja pregled pokritosti vsakega obogatenega polja.

## <a name="next-steps"></a>Naslednji koraki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
