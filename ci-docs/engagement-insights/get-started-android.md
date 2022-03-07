---
title: Začnite z uporabo kompleta za razvoj programske opreme za Android
description: Naučite se, kako prilagoditi in zagnati komplet za razvoj programske opreme za Android
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 10/19/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: b06822b2c2d6a859bdf808f7800baef43c4ab874
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226189"
---
# <a name="get-started-with-the-android-sdk"></a>Začnite z uporabo kompleta za razvoj programske opreme Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Vadnica vam nudi pregled postopka opremljanja vaše aplikacije za Android z vpogledi v interakcije kompleta za razvoj programske opreme Dynamics 365 Customer Insights. Dogodki se vam bodo na portalu prikazali v največ petih minutah.

## <a name="configuration-options"></a>Možnosti konfiguracije
V komplet za razvoj programske opreme lahko prenesete naslednje možnosti konfiguracije:

- **ingestionKey**: ključ za sprejemanje omogoča pošiljanje dogodkov v vaš delovni prostor.

## <a name="prerequisites"></a>Zahteve

- Android Studio

- Najnižja stopnja API za Android: 16 (Jelly Bean)

- Ključ za sprejemanje (navodila o tem, kako ga pridobiti, se nahajajo spodaj)

## <a name="integrate-the-sdk-into-your-application"></a>V svojo aplikacijo integrirajte komplet za razvoj programske opreme
Za začetek postopka izberite delovni prostor ter mobilno platformo Android in prenesite komplet za razvoj programske opreme za Android.

- Svoj delovni prostor izberite v levem podoknu za krmarjenje, s preklopnikom med delovnimi prostori.

- Če nimate obstoječega delovnega prostora, izberite možnost  **Nov delovni prostor** in sledite korakom za ustvarjanje [novega delovnega prostora](create-workspace.md).

- Ko ustvarite delovni prostor, izberite možnost **Skrbnik** > **Delovni prostor**, nato pa  **Navodila za namestitev**.

## <a name="configure-the-sdk"></a>Konfigurirajte komplet za razvoj programske opreme

Ko prenesete komplet za razvoj programske opreme, ga lahko uporabite za delo v okolju Android Studio ter tako omogočite in opredelite dogodke. Za to obstajata dva načina:
### <a name="option-1-use-jitpack-recommended"></a>1. možnost: uporabite JitPack (priporočeno)
1. Dodajte shrambo JitPack svojemu korenu `build.gradle`:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. Dodajte odvisnost:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:v1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-use-download-link"></a>2. možnost: uporabite povezavo za prenos
1. Prenesite [vpoglede v interakcijo kompleta za razvoj programske opreme za Android](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) in datoteko `eiandroidsdk-debug.aar` prenesite v mapo `libs`.

1. Odprite datoteko `build.gradle` na projekti ravni in dodajte naslednje izrezke:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

## <a name="enable-auto-instrumentation"></a>Omogočite samodejno instrumentacijo

1. V svojo datoteko dodajte dovoljenje za omrežje in internet v datoteki `AndroidManifest.xml`, ki se nahaja pod mapo `manifests`.
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```

1. Vpoglede v interakcije kompleta za razvoj programske opreme nastavite s pomočjo datoteke `AndroidManifest.xml`.

1. Iz **Navodil za namestitev** kopirajte izrezek XML. `Your-Ingestion-Key` je mora biti izpolnjen samodejno.

   > [!NOTE]
   > Razdelka `${applicationId}` vam ni treba zamenjati. Dopolnjen je samodejno.


   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Omogočite ali onemogočite samodejno zajemanje prikaza dogodkov `View` tako, da zgornje polje `autoCapture` nastavite na `true` ali `false`. 

   >[!NOTE]
   >`Action` dogodke je treba dodati ročno.

1. (Izbirno.) Druge konfiguracije vključujejo nastavitev URL-ja končne točke povezovalnika. Lahko jih dodate pod metapodatke ključa za vstavljanje v `AndroidManifest.xml`.

   ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
   ```

## <a name="implement-custom-events"></a>Izvedite dogodke po meri

Po inicializaciji kompleta za razvoj programske opreme je mogoče v okolju `MainActivity` delati z dogodki in njihovimi lastnostmi.


Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Nastavite lastnost za vse dogodke (neobvezno)

Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Naslednje vrste so podprte za možnost lastnosti v okviru dogodkov:
- String
- Datum
- Dvojno
- Dolgo
- Logično
- UUID

### <a name="track-an-event"></a>Sledenje dogodku

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

## <a name="set-user-details-for-your-event-optional"></a>Nastavite podrobnosti uporabnika za svoj dogodek (neobvezno)

Komplet za razvoj programske opreme vam omogoča, da določite podatke o uporabniku, ki jih je mogoče poslati z vsakim dogodkom. Podatke o uporabniku lahko določite s klicem API `setUser(user: User)` na ravni `Analytics`.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

Podatkovni razred `User` vsebuje naslednje lastnosti nizov:

- **localId**: uporabnikov lokalni ID.
- **authId**: ID s preverjeno pristnostjo uporabnika.
- **authType**: Vrsta preverjanja pristnosti, ki se uporablja za pridobivanje preverjenega ID-ja uporabnika.
- **name**: ime uporabnika.
- **email**: e-poštni naslov uporabnika.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
