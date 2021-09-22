---
title: Začnite z uporabo kompleta za razvoj programske opreme za Android
description: Naučite se, kako prilagoditi in zagnati komplet za razvoj programske opreme za Android
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 77e63929bbcc7ecff34a3839af525b76ec3c7f21173ddc5f8f2d69f11c25c441
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036938"
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

## <a name="step-1-integrate-the-sdk-into-your-application"></a>1. korak: V svojo aplikacijo integrirajte komplet za razvoj programske opreme
Za začetek postopka izberite delovni prostor ter mobilno platformo Android in prenesite komplet za razvoj programske opreme za Android.

- Svoj delovni prostor izberite v levem podoknu za krmarjenje, s preklopnikom med delovnimi prostori.

- Če nimate obstoječega delovnega prostora, izberite možnost  **Nov delovni prostor** in sledite korakom za ustvarjanje [novega delovnega prostora](create-workspace.md).

## <a name="step-2-configure-the-sdk"></a>2. korak: Konfigurirajte komplet za razvoj programske opreme

1. Ko ustvarite delovni prostor, izberite možnost **Skrbnik** > **Delovni prostor**, nato pa  **Navodila za namestitev**. 

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

1. Vpoglede v interakcije kompleta za razvoj programske opreme nastavite s pomočjo datoteke `AndroidManifest.xml`, ki se nahaja v mapi `manifests`. 
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

1. (Izbirno.) Druge konfiguracije vključujejo nastavitev URL-ja končne točke povezovalnika. Dodati jih je mogoče pod `AndroidManifest.xml`, in sicer med metapodatki ključa za sprejemanje:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="step-3-initialize-the-sdk-from-mainactivity"></a>3. korak: Inicializirajte komplet za razvoj programske opreme iz MainActivity 

Po inicializaciji kompleta za razvoj programske opreme je mogoče v okolju MainActivity delati z dogodki in njihovimi lastnostmi.

    
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

### <a name="set-user-details-for-your-event-optional"></a>Nastavite podrobnosti uporabnika za svoj dogodek (neobvezno)

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
