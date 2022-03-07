---
title: Podatke iz storitve Customer Insights izvozite v ActiveCampaign
description: Naučite se, kako konfigurirati povezavo in podatke izvoziti v ActiveCampaign.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 089b9b0d76437e695f797f941ed384734d8f772e
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227829"
---
# <a name="export-segments-to-activecampaign-preview"></a>Izvoz segmentov v ActiveCampaign (predogledna različica)

Segmente poenotenih profilov strank izvozite v ActiveCampaign in jih uporabite za trženjske dejavnosti.

## <a name="prerequisites"></a>Zahteve

-   Imate [račun ActiveCampaign](https://www.activecampaign.com/) in ustrezne poverilnice skrbnika.
-   Imate [konfigurirane segmente](segments.md) pri vpogledih v občinstvo.
-   Poenoteni profili strank v izvoženih segmentih vsebujejo polje z e-poštnim naslovom.

## <a name="known-limitations"></a>Znane omejitve

- Izvozite lahko do 1 milijon profilov strank na izvoz v storitev ActiveCampaign in to lahko traja do 90 minut.
- Pri izvažanju v ActiveCampaign ste omejeni na segmente.
- Število profilov strank, ki jih lahko izvozite v storitev ActiveCampaign, je odvisno od vaše pogodbe s storitvijo ActiveCampaign.

## <a name="set-up-connection-to-activecampaign"></a>Vzpostavite povezavo s storitvijo ActiveCampaign

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Za konfiguriranje povezave izberite možnost **Dodaj povezavo**, nato pa **ActiveCampaign**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto jo lahko uporabljajo samo skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vpišite [ključ API za ActiveCampaign in ime gostitelja končne točke REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key). Ime gostitelja za končno točko REST je samo ime gostitelja, brez https://. 

1. Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.

1. Za inicializiranje povezave z ActiveCampaign izberite možnost **Poveži**.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

Izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Za ustvarjanje novega izvoza izberite **Dodaj cilj**.

1. V polju **Povezava za izvoz**, in sicer v razdelku ActiveCampaign, izberite povezavo. Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.

1. Vnesite svoj [**ID seznama za ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).    

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje, ki predstavlja e-poštni naslov stranke. Segmente morate izvoziti v ActiveCampaign. Za bolj prilagojena e-poštna sporočila vam je na voljo možnost izvoza imena, priimka in vsebine telefona. Izberite Dodaj atribut za preslikavo teh polj.

1. Izberite **Shrani**.

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab). Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

S tem ko dovolite, da storitev Dynamics 365 Customer Insights podatke prenese storitvi ActiveCampaign, omogočite prenos podatkov zunaj omejitve skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo tovrstne podatke prenesel skladno z vašimi navodili, vendar ste vi odgovorni za to, da ActiveCampaign izpolni morebitne obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.
