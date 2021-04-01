---
title: Izvozite podatke Customer Insights v gostitelje SFTP
description: Preberite, kako konfigurirati povezavo z gostiteljem SFTP.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598405"
---
# <a name="connector-for-sftp-preview"></a>Povezovalnik za SFTP (predogled)

Uporabite svoje podatke o strankah v aplikacijah drugih ponudnikov tako, da jih izvozite v gostitelja s protokolom za varen prenos datotek (SFTP).

## <a name="prerequisites"></a>Zahteve

- Razpoložljivost gostitelja SFTP in ustreznih poverilnic

## <a name="connect-to-sftp"></a>Vzpostavitev povezave z SFTP-jem

1. Izberite **Skrbnik** > **Cilji za izvoz**.

1. V razdelku **SFTP** izberite **Nastavi**.

1. Dajte svojemu cilju prepoznavno ime v polju **Prikazno ime**.

1. Vnesite **uporabniško ime**, **geslo**, **ime gostitelja** in **izvozno mapo** za vaš račun SFTP.

1. Če želite preskusiti povezavo, izberite **Preveri**.

1. Po uspešnem preverjanju izberite, ali želite podatke izvoziti **stisnjeno** ali **razširjeno**, in izberite **ločilo polja** za izvožene datoteke.

1. Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.

1. Izberite **Naslednji**, če želite začeti konfigurirati izvoz.

## <a name="configure-the-export"></a>Konfiguriranje izvoza

1. Izberite entitete, na primer segmente, ki jih želite izvoziti.

   > [!NOTE]
   > Vsaka izbrana entiteta bo ob izvozu imela do pet izhodnih datotek. 

1. Izberite **Shrani**.

## <a name="export-the-data"></a>Izvoz podatkov

Lahko [izvozite podatke na zahtevo](export-destinations.md). Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).

## <a name="known-limitations"></a>Znane omejitve

- Trajanje izvoza je odvisno od zmogljivosti vašega sistema. Kot minimalno konfiguracijo strežnika priporočamo dvojedrni procesor in 1 Gb pomnilnika. 
- Izvoz entitet z do 100 milijoni profilov strank lahko traja 90 minut, če uporabite priporočeno minimalno konfiguracijo dvojedrnega procesorja in 1 Gb pomnilnika. 

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov prek SFTP-ja, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da cilj za izvoz izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.


[!INCLUDE[footer-include](../includes/footer-banner.md)]