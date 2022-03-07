---
title: Vzorec kompleta za razvoj programske opreme za Android
description: Vzorčni projekt za spoznavanje kompleta za razvoj programske opreme za Android
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 2ee29a98192bb53bd92241d71c1a76ec2b7bf846
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229938"
---
# <a name="run-the-android-sdk-sample"></a>Zaženi vzorec kompleta za razvoj programske opreme za Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Z vzorčnim projektom Android boste lažje razumeli, kako komplet za razvoj programske opreme deluje v aplikaciji. Kode vam ne bo treba navajati. Dogodke v delovnem prostoru boste lahko videli, takoj ko dodate svoj ključ za sprejemanje.

## <a name="prerequisites"></a>Zahteve

- [Android Studio](https://developer.android.com/studio)
- [Ključ za sprejemanje](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Prenos vzorca kompleta za razvoj programske opreme za Android

1. [Prenesite vpogled v interakcije vzorca kompleta za razvoj programske opreme za Android](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Razširite stisnjeno datoteko `ei-android-sample.zip`.
1. Stisnjeno mapo, ki ste jo razširili, odprite v okolju Android Studio.
1. V datoteki `AndroidManifest.xml` niz `"Your-Ingestion-Key"` zamenjajte s svojim ključem za sprejemanje v delovnem prostoru iz vpogledov v interakcije, in sicer pod **skrbnik** > **delovni prostor** > **navodila za namestitev**. 

   > [!NOTE]
   > Razdelka `${applicationId}` vam ni treba zamenjati. Dopolnjen je samodejno.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Če želite zagnati vzorčni projekt, izberite **Zaženi**.
1. Oglejte si dogodke v svojem delovnem prostoru.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
