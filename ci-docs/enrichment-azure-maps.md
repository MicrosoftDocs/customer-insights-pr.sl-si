---
title: Obogatite profile strank z podatki o lokaciji iz Azure Maps (predogled)
description: Splošne informacije o obogatitvi proizvajalca storitve Zemljevidi Azure.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f14b4fc20a9a1d8842f42f9e0e656b3d8dcddcf4
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/08/2022
ms.locfileid: "9238062"
---
# <a name="enrich-customer-profiles-with-location-data-from-azure-maps-preview"></a>Obogatite profile strank z podatki o lokaciji iz Azure Maps (predogled)

Zemljevidi Azure zagotavljajo podatke in storitve, osredotočene na lokacijo, za zagotavljanje izkušenj na podlagi geoprostorskih podatkov z vgrajeno lokacijsko inteligenco. Storitve obogatitve podatkov v storitvi Zemljevidi Azure izboljšajo natančnost podatkov o lokaciji vaših strank. Prinaša zmogljivosti, kot so normaliziranje naslovov ter ekstrahiranje zemljepisne širine in dolžine v storitev Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Zahteve

- Aktivna naročnina na zemljevide Azure. Če želite pridobiti naročnino, [prijavite se ali pridobite brezplačen preizkus](https://azure.microsoft.com/services/azure-maps/).

- Zemljevidi Azure [povezava](connections.md) je [konfiguriran](#configure-the-connection-for-azure-maps) s strani skrbnika.

## <a name="configure-the-connection-for-azure-maps"></a>Konfiguriranje povezave za storitev Zemljevidi Azure

Morate biti [skrbnik](permissions.md#admin) v Customer Insights in imajo aktiven ključ API-ja za zemljevide Azure.

1. Pri konfiguriranju obogatitve izberite možnost **Dodaj povezavo** ali pa odprite razdelek **Skrbnik** > **Povezave** ter v ploščici storitve Zemljevidi Azure izberite **Nastavitev**.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Stran za konfiguracijo povezave za storitev Zemljevidi Azure.":::

1. Vnesite ime za povezavo in veljaven ključ API-ja za zemljevide Azure.

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite **Preveri** za potrditev konfiguracije in nato izberite **Shrani**.

## <a name="configure-the-enrichment"></a>Konfiguriranje obogatitve

1. Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.

1. Izberite **Obogati moje podatke** na **Lokacija** od Microsoft Azure Ploščica zemljevidov.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Ploščica za storitev Zemljevidi Azure.":::

1. Preglejte pregled in nato izberite **Naslednji**.

1. Izberite povezavo. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Izberite **Naprej**.

1. Izberite **Stranka nabor podatkov** in izberite profil ali segment, ki ga želite obogatiti s podatki Microsofta. The *Stranka* entiteta obogati vse vaše profile strank, medtem ko segment obogati samo profile strank v tem segmentu.

1. Določite, katero vrsto polj iz vaših poenotenih profilov boste uporabili za ujemanje: primarni in/ali sekundarni naslov. Za oba naslova lahko določite preslikavo polj in obogatite profile za vsak naslov posebej. Na primer za domači in poslovni naslov. Izberite **Naprej**.

1. Preslikajte svoja polja v podatki o lokaciji iz Azure Maps. Polji **Ulica 1** in **Poštna številka** sta obvezni za izbrani primarni in/ali sekundarni naslov. Za večjo natančnost ujemanja dodajte več polj.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Preslikava atributov Azure Maps.":::

1. Izberite možnost **Naprej**, da dokončate preslikavo polj.

1. Pregled **Napredne nastavitve** ki ponujajo največjo prilagodljivost za obravnavo naprednih primerov uporabe. Vendar naslednjih privzetih vrednosti običajno ni treba spreminjati.

   - **Vrsta naslovov** : Najboljši naslov se vrne, tudi če je nepopoln. Če želite pridobit samo popolne naslove, na primer naslove, ki vključujejo hišno številko, počistite vsa potrditvena polja razen **Naslovi točke**.
   - **Jezik** : naslovi se vrnejo v jeziku, ki temelji na območju naslova. Če želite uporabiti standardiziran jezik naslova, v spustnem meniju izberite jezik. Na primer izbiranje **angleščina** vrača **Kopenhagen, Danska** namesto **København, Danska**.
   - **Največje število rezultatov** : Število rezultatov na naslov.

1. Izberite **Naprej**.

1. Zagotovite a **Ime** za obogatitev in **Ime izhodne entitete**.

1. Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.

1. Izberite **Teči** za začetek procesa obogatitve ali zapiranje za vrnitev v **Obogatitve** strani.

## <a name="view-enrichment-results"></a>Oglejte si rezultate obogatitve

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

The **Število strank, obogatenih po področjih** zagotavlja podrobno analizo pokritosti vsakega obogatenega polja.

## <a name="next-steps"></a>Naslednji koraki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
