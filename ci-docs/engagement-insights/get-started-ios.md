---
title: Začnite z uporabo kompleta za razvoj programske opreme za iOS
description: Naučite se, kako prilagoditi in zagnati komplet za razvoj programske opreme za iOS
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 09/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 879a71175a2e7d44a54d25fd8efb9f12927cea5a
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977543"
---
# <a name="get-started-with-the-ios-sdk"></a>Začnite z uporabo kompleta za razvoj programske opreme za iOS

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Vadnica vam nudi pregled postopka opremljanja vaše aplikacije za iOS z vpogledi v interakcije kompleta za razvoj programske opreme Dynamics 365 Customer Insights. Dogodki se vam bodo na portalu prikazali v največ petih minutah.

## <a name="configuration-options"></a>Možnosti konfiguracije

Naslednje možnosti konfiguracije lahko posredujete v komplet za razvoj programske opreme s pomočjo datotek `EIConfig.plist`, ki so priložene:

- **ingestionKey**: ključ za sprejemanje omogoča pošiljanje dogodkov v vaše projekte.
- **autocollectAction**: logična vrednost za omogočanje ali onemogočanje samodejne instrumentacije dogodka z dejanjem.
- **autocollectAction**: logična vrednost za omogočanje ali onemogočanje samodejne instrumentacije ogleda dogodka.
- **endpointUrl**: URL končne točke, kamor bodo usmerjeni dogodki.

## <a name="prerequisites"></a>Zahteve

- Različica Xcode 9+
- Različica iOS 8.2+
- Ključ za sprejemanje (navodila o tem, kako ga pridobiti, se nahajajo spodaj)

## <a name="integrate-the-sdk-into-your-application"></a>V svojo aplikacijo integrirajte komplet za razvoj programske opreme

Za začetek postopka izberite delovni prostor, ki ga boste uporabljali pri delu, ter mobilno platformo iOS in prenesite komplet za razvoj programske opreme.

- Svoj delovni prostor izberite v levem podoknu za krmarjenje, s preklopnikom med delovnimi prostori.

- Če nimate obstoječega delovnega prostora, izberite možnost  **Nov delovni prostor** in sledite korakom za ustvarjanje [novega delovnega prostora](create-workspace.md).

- Ko ustvarite delovni prostor, izberite možnost **Skrbnik** > **Delovni prostor**, nato pa **Navodila za namestitev**.

## <a name="configure-the-sdk"></a>Konfigurirajte komplet za razvoj programske opreme

Ko prenesete komplet za razvoj programske opreme, ga lahko uporabite za delo v okolju Xcode ter tako omogočite in opredelite dogodke. Za to obstajata dva načina

### <a name="option-1-using-cocoapods-recommended"></a>1. možnost: uporaba upravitelja CocoaPods (priporočeno)
CocoaPods je upravitelj odvisnosti za projekte Swift in Objective-C Cocoa. Z njegovo uporabo je lažje vključiti vpoglede v interakcije kompleta za razvoj programske opreme za sistem iOS. CocoaPods omogoča tudi nadgradnjo na najnovejšo različico vpogledov v interakcije kompleta za razvoj programske opreme. Tukaj je opisano, kako uporabiti CocoaPods za vključitev vpogledov v interakcije kompleta za razvoj programske opreme v vaš projekt Xcode. 

1. Namestite rešitev CocoaPods. 

1. V korenskem imeniku svojega projekta ustvarite novo datoteko, imenovano Podfile, in ji dodajte naslednje izjave.Zamenjajte YOUR_TARGET_PROJECT_NAME z imenom vašega projekta Xcode. 
```objectivec
platform :ios, '9.0'  

 target '${YOUR_TARGET_PROJECT_NAME}' do 

     use_frameworks!   

     pod 'EIObjC.framework.debug' 

     pod 'EIObjC.framework.release' 

 end 
```
Zgornja konfiguracija za pod vsebuje različice za odpravljanje napak in komplet za razvoj programske opreme. Izberite tisto, ki je najboljša za vaš projekt.

1. Namestite pod tako, da izvedete naslednji ukaz: `pod install --repo-update `

### <a name="option-2-using-download-link"></a>2. možnost: uporaba povezave za prenos

1. Prenesite [vpoglede v interakcije kompleta za razvoj programske opreme za iOS](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) in datoteko `EIObjC.xcframework` prenesite v mapo `Frameworks`.

1. Če mape `Frameworks` ni, jo ustvarite v projektni mapi.

## <a name="enable-auto-instrumentation"></a>Omogočite samodejno instrumentacijo
 
Samodejno instrumentacijo lahko omogočite enostavno, brez kodiranja. Ko se projekt zažene, bo samodejno spremljal dogodka `view` in `action` z uporabo konfiguriranega ključa za spremljanje. 

1. Posodobite priloženo datoteko `EIConfig.plist` in jo vključite v mapo imenika projekta za naslednja polja:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = DA
    - autocollectAction = DA

2. Nato v svoj projekt v okolju Xcode dodajte datoteko `EIConfig.plist`. 



Če želite onemogočiti samodejno instrumentacijo, posodobite naslednja polja v priloženi datoteki `EIConfig.plist`, ki se nahaja v mapi imenika projekta. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Izvedite dogodke po meri

1. Odprite projekt v okolju Xcode in se pomaknite na **Splošne** informacije. 
1. V projekt dodajte `EIObjC.xcframework`, ki se nahaja v razdelku »Okviri, knjižnice in vdelana vsebina«.

1. Uvozite datoteko z glavo okvira v AppDelegate.m z naslednjim izrezkom:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Inicializirajte vpoglede v interakcije kompleta za razvoj programske opreme iz aplikacije: didFinishLaunchingWithOptions.
1. Iz **Navodil za namestitev** kopirajte izrezek XML.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Spremljanje dogodka

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Nastavite podatke o uporabniku za svoj dogodek

Komplet za razvoj programske opreme vam omogoča, da določite podatke o uporabniku, ki jih je mogoče poslati z vsakim dogodkom. Podatke o uporabniku lahko določite s klicem API `setUser:(nonnull EIUser *)user` v kompletu za razvoj programske opreme.

Navedite podatkov o uporabniku na ravni storitve `Analytics` pomeni, da bodo vse telemetrije vsebovale te podatke. Če pa so določene na ravni dogodka s klicem API `setUser:(nonnull EIUser *)user` na predmetu EIEvent, bo podatke vseboval le ta določen dogodek.

Podatkovni razred `EIUser` vsebuje naslednje lastnosti NSString:

- **localId**: uporabnikov lokalni ID.
- **authId**: ID s preverjeno pristnostjo uporabnika.
- **authType**: vrsta preverjanja pristnosti, ki se uporablja za pridobitev ID-ja s preverjeno pristnostjo uporabnika.
- **name**: ime uporabnika.
- **email**: e-poštni naslov uporabnika.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
