---
title: Zaženi vzorec kompleta za razvoj programske opreme za iOS
description: Vzorčni projekt za spoznavanje kompleta za razvoj programske opreme za iOS
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bbe4ba648952a8081af4c8f2610276809fa5efeb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232862"
---
# <a name="run-the-ios-sdk-sample"></a>Zaženi vzorec kompleta za razvoj programske opreme za iOS

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

S pomočjo vzorčnega projekta iOS boste lažje razumeli, kako komplet za razvoj programske opreme deluje v aplikaciji. Kode vam ne bo treba navajati. Dogodke v delovnem prostoru boste lahko videli, takoj ko dodate svoj ključ za sprejemanje.

## <a name="prerequisites"></a>Zahteve

- [Različica Xcode 9+](https://developer.apple.com/xcode/downloads/)
- [Ključ za sprejemanje](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>Prenos vzorca kompleta za razvoj programske opreme za iOS

1. [Prenesite vzorec vpogledov v interakcije kompleta za razvoj programske opreme za iOS](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. Razširite stisnjeno datoteko `ei-ios-sample.zip`.
1. V okolju Xcode odprite vzorčni projekt aplikacije.
1. V datoteki `EIConfig.plist` zamenjajte niz `“YOUR-INGESTION-KEY”` v polju `ingestionKey` s svojim ključem za sprejemanje v delovnem prostoru iz vpogledov v interakcije, in sicer pod **Skrbnik** > **Delovni prostor** > **Navodila za namestitev**.
1. Če želite zagnati vzorčni projekt, izberite **Zaženi**.
1. Oglejte si dogodke v svojem delovnem prostoru.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
