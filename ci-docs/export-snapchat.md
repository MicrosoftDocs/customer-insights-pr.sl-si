---
title: Izvoz segmentov v Snapchat (predogledna različica)
description: Naučite se, kako konfigurirati povezavo in izvažati v Snapchat.
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: abe04cd1464c3f7df969da3c769329382d603d7e
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051933"
---
# <a name="export-segments-to-snapchat-preview"></a>Izvoz segmentov v Snapchat (predogledna različica)

Izvozite segmente poenotenih profilov strank v Snapchat in jih uporabite za oglaševanje. 

## <a name="prerequisites-for-a-connection"></a>Predpogoji za povezavo

-   Imate [račun za Snapchat Business](https://business.snapchat.com/), [račun za Snapchat Ads](https://ads.snapchat.com/) in pripadajoče skrbniške poverilnice. Biti morate vsaj član organizacijskega računa in upravitelj podatkov določenega računa oglasov. 
-   V Snapchatu imate vsaj enega upravitelja občinstvo občinstvo tipa SAM (Snap občinstvo Match). 
-   Imaš [konfigurirani segmenti](segments.md) v Customer Insights.
-   Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="known-limitations"></a>Znane omejitve

- Izvoz v Snapchat je omejen na segmente.
- Izvoz do 1 milijon profilov strank v Snapchat lahko traja do 15 minut. 

## <a name="set-up-connection-to-snapchat"></a>Nastavitev povezave s storitvijo Snapchat

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajanje povezave** in izberite **Snapchat** za konfiguracijo povezave.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.

1. Izberite **Poveži** za inicializiranje povezave s storitvijo Snapchat.

1. Izberite **Preverjanje pristnosti z aplikacijo Snapchat** in vnesite skrbniške poverilnice za Snapchat. 

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Za ustvarjanje novega izvoza izberite **Dodaj cilj**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku Snapchat. Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.

1. Vnesite [**ID segmenta Snapchat/občinstvo**](https://businesshelp.snapchat.com/s/article/custom-audiences). ID občinstvo lahko najdete v URL-ju, ko izberete občinstvo v upravitelju Snapchat občinstvo. 

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje, ki predstavlja e-poštni naslov stranke. To je obvezno za izvoz segmentov Snapchat.

1. Izberite segmente, ki jih želite izvoziti. 

1. Izberite **Shrani**.

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab). Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite, da Dynamics 365 Customer Insights prenese podatke v Snapchat, dovolite prenos podatkov zunaj meja zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno potencialno občutljivih podatkov, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Snapchat izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti, ki jih morda imate. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.
