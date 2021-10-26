---
title: Podatke iz storitve Customer Insights izvozite v Sendinblue
description: Naučite se, kako konfigurirati povezavo in podatke izvoziti v Sendinblue.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5924b2d4e7f0b11ce6478a31015fcbaaf44ff93
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617805"
---
# <a name="export-segments-to-sendinblue-preview"></a>Izvoz segmentov v Sendinblue (predogledna različica)

Za ustvarjanje akcij, zagotovitev e-poštnega trženja in uporabo določenih skupin strank s storitvijo Sendinblue izvozite segmente poenotenih profilov strank.

## <a name="prerequisites-for-connection"></a>Predpogoji za povezavo

-   Imate [račun Sendinblue](https://www.sendinblue.com/) in ustrezne poverilnice skrbnika.
-   Obstoječi seznami so v storitvi Sendinblue in ustreznih ID-jih.
-   Imate [konfigurirane segmente](segments.md).
-   Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="known-limitations"></a>Znane omejitve

- Do 1 milijon profilov strank na izvoz v storitev Sendinblue.
- Pri izvažanju v Sendinblue ste omejeni na segmente.
- Izvoz segmentov s skupno 1 milijonom profilov strank lahko traja do 90 minut. 
- Število profilov strank, ki jih lahko izvozite v storitev Sendinblue, je odvisno in omejeno glede na vašo pogodbo s storitvijo Sendinblue.

## <a name="set-up-connection-to-sendinblue"></a>Vzpostavite povezavo s storitvijo Sendinblue

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Za konfiguriranje povezave izberite možnost **Dodaj povezavo**, nato pa **Sendinblue**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto je storitev namenjena samo skrbnikom. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vnesite svoj **[ključ vmesnika API storitve Sendinblue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.

1. Izberite možnost **Strinjam se**, s čimer potrdite, da se strinjate z možnostjo **Zasebnost in skladnost podatkov**, ter izberite možnost **Poveži** in tako inicializirajte povezavo s storitvijo Sendinblue.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Za ustvarjanje novega izvoza izberite **Dodaj cilj**.

1. V polju **Povezava za izvoz**, in sicer v razdelku Sendinblue, izberite povezavo. Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.

1. Vnesite svoj ID seznam za **Sendinblue** 

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje, ki predstavlja e-poštni naslov stranke. 

1. Za bolj prilagojena e-poštna sporočila vam je na voljo možnost izvoza **imena**, **priimka** in **vsebine telefona**. Izberite **Dodaj atribut** za preslikavo teh polj.

1. Izberite segmente, ki jih želite izvoziti. 

1. Izberite **Shrani**.

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab). Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

S tem ko dovolite, da storitev Dynamics 365 Customer Insights podatke prenese storitvi Sendinblue, omogočite prenos podatkov zunaj omejitve skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo tovrstne podatke prenesel skladno z vašimi navodili, vendar ste vi odgovorni za to, da Sendinblue izpolni morebitne obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
