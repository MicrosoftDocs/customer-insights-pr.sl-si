---
title: Izvozite podatke Customer Insights v gostitelje SFTP
description: Preberite, kako konfigurirati povezavo z gostiteljem SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643523"
---
# <a name="connector-for-sftp-preview"></a>Povezovalnik za SFTP (predogled)

Uporabite svoje podatke o strankah v aplikacijah drugih ponudnikov tako, da jih izvozite v gostitelja s protokolom za varen prenos datotek (SFTP).

## <a name="prerequisites"></a>Zahteve

- Razpoložljivost gostitelja SFTP in ustreznih poverilnic.

## <a name="connect-to-sftp"></a>Vzpostavite povezavo z gostiteljem SFTP

1. Izberite **Skrbnik** > **Cilji za izvoz**.

1. V razdelku **SFTP** izberite **Nastavi**.

1. Dajte svojemu cilju prepoznavno ime v polju **Prikazno ime**.

1. Vnesite **uporabniško ime**, **geslo** in **ime gostitelja** za vaš račun SFTP. Primer: če je korenska mapa vašega strežnika SFTP /root/folder in želite, da se podatki izvozijo v /root/folder/ci_export_destination_folder, mora biti gostitelj sftp://<server_address>/ci_export_destination_folder.

1. Če želite preskusiti povezavo, izberite **Preveri**.

1. Po uspešnem preverjanju se odločite, ali želite podatke izvoziti v **Stisnjeni mapi** ali **Nestisnjeni mapi** in izberite **ločilni znak za polje** za izvožene datoteke.

1. Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.

1. Izberite **Naslednji**, če želite začeti konfigurirati izvoz.

## <a name="configure-the-connection"></a>Konfiguriraj povezavo

1. Izberite **atribute strank**, ki jih želite izvoziti. Lahko izvozite enega ali več atributov.

1. Izberite **Naprej**.

1. Izberite segmente, ki jih želite izvoziti.

1. Izberite **Shrani**.

## <a name="export-the-data"></a>Izvoz podatkov

Lahko [izvozite podatke na zahtevo](export-destinations.md). Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov prek SFTP-ja, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da cilj za izvoz izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.
