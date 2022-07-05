---
title: Izvozi podatke v gostitelje SFTP (predogled) (vsebuje video)
description: Naučite se, kako konfigurirati povezavo in izvažati na lokacijo SFTP.
ms.date: 06/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 67789a87cf0ff1b0d9933f2c0adde37762c83476
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082774"
---
# <a name="export-data-to-sftp-preview"></a>Izvozi podatke v SFTP (predogled)

Uporabite svoje podatke o strankah v aplikacijah drugih ponudnikov tako, da jih izvozite na lokacijo protokola za varen prenos datotek (SFTP).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites-for-connection"></a>Predpogoji za povezavo

- Razpoložljivost gostitelja SFTP in ustreznih poverilnic

## <a name="known-limitations"></a>Znane omejitve

- Cilji SFTP za požarnimi zidovi trenutno niso podprti. 
- Trajanje izvoza je odvisno od zmogljivosti vašega sistema. Kot minimalno konfiguracijo strežnika priporočamo dvojedrni procesor in 1 Gb pomnilnika.
- Izvoz entitet z do 100 milijoni profilov strank lahko traja 90 minut, če uporabite priporočeno minimalno konfiguracijo dvojedrnega procesorja in 1 Gb pomnilnika.

## <a name="set-up-connection-to-sftp"></a>Nastavitev povezave s storitvijo SFTP

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajanje povezave** in izberite **SFTP** za konfiguracijo povezave.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vnesite **uporabniško ime**, **geslo**, **ime gostitelja** in **izvozno mapo** za vaš račun SFTP.

1. Če želite preskusiti povezavo, izberite **Preveri**.

1. Izberite, ali želite izvoziti podatke z možnostjo **Gzipped** ali **Razširjeno** in **ločilo polja** za izvožene datoteke.

1. Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Za ustvarjanje novega izvoza izberite **Dodaj cilj**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku SFTP. Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.

1. Izberite entitete, na primer segmente, ki jih želite izvoziti.

   > [!NOTE]
   > Vsaka izbrana entiteta bo ob izvozu razdeljena na do pet izhodnih datotek.

1. Izberite **Shrani**.

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).
Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).

> [!TIP]
> Izvoz entitet, ki vsebujejo veliko količino podatkov, lahko pri vsakem izvozu povzroči več datotek CSV v isti mapi. Delitev izvozov se zgodi zaradi učinkovitosti, da se zmanjša čas, potreben za dokončanje izvoza.

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov prek SFTP-ja, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da cilj za izvoz izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
