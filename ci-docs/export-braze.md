---
title: Izvoz segmentov v Braze (predogled)
description: Naučite se konfigurirati povezavo in izvoziti v Braze.
ms.date: 10/06/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 2f52eb8196e057f934c8d2b5ac0518ce121606b6
ms.sourcegitcommit: 003c1929f730d7d505c108aba84f6269f4c98978
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 10/12/2022
ms.locfileid: "9655307"
---
# <a name="export-segments-to-braze-preview"></a>Izvoz segmentov v Braze (predogled)

Izvozite segmente poenotenih profilov strank v Braze in jih uporabite za marketinške dejavnosti.

## <a name="prerequisites"></a>Zahteve

- A [Braze račun](https://www.braze.com/) in ustrezne skrbniške poverilnice.
- A [Braze API ključ](https://www.braze.com/docs/api/basics/)
- Vaš [Braze REST končna točka](https://www.braze.com/docs/api/basics/#api-definitions) 
- [Konfigurirani segmenti](segments.md) v Customer Insights.
- Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov in ID stranke Braze.

## <a name="known-limitations"></a>Znane omejitve

- Do 1 milijon profilov strank za Braze, ki lahko traja do 40 minut. Število profilov strank, ki jih lahko izvozite v Braze, je odvisno od vaše pogodbe z Braze.
- Samo segmenti.
- Azure Private Link ni podprt za izvoz Braze.

## <a name="set-up-connection-to-braze"></a>Nastavite povezavo z Braze

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **Spajkanje**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto jo lahko uporabljajo samo skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Za nadaljevanje prijave vnesite svoj ključ API-ja Braze.

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite **Povežite se** za inicializacijo povezave.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz**.

1. V **Povezava za izvoz** izberite povezavo v razdelku Braze. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Vnesite svoj REST končna točka v **Ime gostitelja** polje v naslednji obliki:`rest.iad-03.braze.com`.

1. Vnesite ime za izvoz.

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje, ki predstavlja e-poštni naslov stranke. V **identifikacijska številka stranke** izberite polje, ki predstavlja kupčev ID Braze. Segmenti v Braze bodo ustvarjeni z istim imenom segmenta kot v Dynamics 365 Customer Insights. Za ujemanje podatkov lahko izberete več neobveznih polj.

1. Izberite entitete ali segmente, ki jih želite izvoziti.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
