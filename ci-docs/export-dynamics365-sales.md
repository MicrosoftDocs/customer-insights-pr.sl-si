---
title: Izvoz segmentov v Dynamics 365 Sales (predogled)
description: Naučite se, kako konfigurirati povezavo in izvažati v Dynamics 365 Sales.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196001"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Izvoz segmentov v Dynamics 365 Sales (predogled)

Na podlagi podatkov o strankah z aplikacijo Dynamics 365 Sales ustvarjajte sezname za trženje in postopke za nadaljnje delo ter pošiljajte promocijske vsebine.

## <a name="prerequisites"></a>Zahteve

Zapisi o stikih morajo biti prisotni v storitvi Dynamics 365 Sales, preden lahko izvozite segment iz rešitve Customer Insights v Sales. Preberite več o tem, kako vnesti stike iz [Dynamics 365 Sales z uporabo Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Z izvozom segmentov iz storitve Customer Insights v prodajo ne boste ustvarili novih zapisov stikov v primerih prodaje. Zapise stikov iz prodaje je treba vnesti v Customer Insights in uporabiti kot vir podatkov. Prav tako jih je treba vključiti v enotno entiteto stranke, da se ID-ji strank preslikajo v ID-je stikov, preden je segmente mogoče izvoziti.

## <a name="known-limitations"></a>Znane omejitve

Izvozi v Dynamics 365 Sales so omejeni na 100.000 na segment, kar lahko traja do 3 ure.

## <a name="set-up-connection-to-sales"></a>Nastavite povezavo s prodajo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **Dynamics 365 Sales**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto jo lahko uporabljajo samo skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vnesite URL za Sales vaše organizacije v polje **Naslov strežnika**.

1. V razdelku **Skrbniški račun strežnika** izberite **Vpis** in izberite račun Dynamics 365 Sales.

1. Polje za ID stranke preslikajte v ID stika za Dynamics 365.

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku Dynamics 365 Sales. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Vnesite ime za izvoz.

1. Izberite polje ID stika v entiteti stranke, ki se ujema z ID-jem stika Dynamics 365.

1. Izberite segmente, ki jih želite izvoziti.

1. Izberite **Shrani**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
