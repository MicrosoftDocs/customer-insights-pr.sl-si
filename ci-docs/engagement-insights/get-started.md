---
title: Začetek uporabe zmogljivosti vpogledov v interakcije
description: Pregled virov za pomoč za hiter začetek.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 3505c15c4319c8cc8823bcd89d3b8adc944a87dd
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623697"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Začetek uporabe zmogljivosti vpogledov v interakcije Dynamics 365 Customer Insights (predogledna različica za javnost)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Zmogljivost vpogledov v interakcije vam omogoča zbiranje in merjenje vedenja strank na vašem spletnem mestu. Integrira se s funkcijo vpogledov v interakcije, tako da si lahko poleg poročil o profilu strank ogledate bogato vedenjsko analizo v realnem času. Povezave v tem članku vam pomagajo hitro konfigurirati in nastaviti okolje.

## <a name="step-1-review-prerequisites"></a>1. korak: Pregled zahtev

Najprej morate imeti aktiven Microsoftov uporabniški račun za storitev Azure Active Directory (AAD). Nato preberite naslednje članke, preden nastavite delovni prostor za vpoglede v interakcije.

- Preglejte in sprejmite [pogoje storitve](terms-of-service.md) pri Microsoftu.  
- Preberite članek [Upravljanje piškotkov in soglasja uporabnika](user-consent-storage.md). Nato ocenite, ali morate posodobiti obvestilo o privolitvi uporabnika. Če prej niste imeli »nebistvenih« piškotkov, boste verjetno morali posodobiti pravilnik o svojem spletnem mestu.
- Preglejte [glosar](glossary.md) za hiter uvod v ključne pojme in koncepte.

## <a name="step-2-explore-engagement-insights"></a>2. korak: Raziskovanje vpogledov v interakcije

Ko prvič obiščete vpoglede v občinstvo, lahko konfigurirate nastavitve, pregledate pravilnike in raziščete možnost.

1. Vpišite se v [portal zmogljivosti vpogledov v interakcije](https://home.ci.ai.dynamics.com/app/engagement-insights) z Microsoftovim uporabniškim računom AAD (šolski ali službeni).

1. Izberite svojo regijo in potrdite polje, če se želite prijaviti za prejemanje e-poštnih sporočil o posodobitvah in ponudbah.

1. Preglejte **Pogoje uporabe** vpogledov v interakcije (predogledna različica) in **Izjavo o zasebnosti** in nato izberite **Raziščite predstavitev**, da sprejmete te nastavitve.

1. Raziskujte izdelek z naborom vzorčnih podatkov.

##  <a name="step-3-set-up-a-workspace-and-create-reports"></a>3. korak: nastavitev delovnega prostora in ustvarjanje poročil

Delovni prostor je kraj, kjer si lahko v realnem času ogledate dejavnosti uporabnika ter shranite in upravljate poročila. Za začetek zbiranja *dogodkov*, tj. dejavnosti, ki prihajajo od uporabnikov, dodajte kodo na spletno mesto.

1. [Ustvarite delovni prostor](create-workspace.md) in dodajte člane.

1. Dodajte kodo na svoje [spletno mesto](instrument-website.md) ali v [mobilno aplikacijo](developer-resources.md#capture-events-from-mobile-apps) in si oglejte, kako se dejavnost uporabnikov namešča v vaš delovni prostor.

1. Oglejte si [sprotno poročilo](view-reports.md), ki prikazuje aktivne uporabnike glede na brskalnik, napravo, operacijski sistem, lokacijo in jezik. Lahko tudi ustvarjate [poročila po meri](custom-reports.md), da ustvarite lastne vizualizacije.

1. Ustvarite [dimenzije](dimensions.md) za razvrščanje obiskovalcev po novih in povratnih uporabnikih, [meritve](metrics.md) za lažje razumevanje vedenja uporabnikov in [segmente](segments.md) za prepoznavanje podskupin obiskovalcev na podlagi značilnosti ali interakcij na spletnem mestu.
    
## <a name="step-4-export-data-to-other-channels"></a>4. korak: izvoz podatkov v druge kanale

Lahko ustvarjate *izboljšane dogodke* (virtualni pogled) vaših podatkov spletne analitike. Nato podatke filtrirajte in izvozite v Azure Data Lake Storage. Izvožene podatke lahko uvozite kot vir podatkov.

1. [Ustvarite izboljšane dogodke](refined-events.md) za izvoz.

1. [Izvozite podatke](export-events.md) v Azure Data Lake Storage.

1. [Ustvarite povezavo med vpogledi v občinstvo in vpogledi v interakcije](integrate-audience-insights-engagement-insights.md) za skupno rabo podatkov med obema zmogljivostma.

1. [Prepoznajte spletne dogodke uporabnikov s predhodno preverjeno pristnostjo](unknown-to-known.md), ki imajo funkcijo **iz neznanega v znano**.

1. Naučite se [izbrisati in izvoziti podatke o dogodkih, ki vsebujejo osebne podatke](delete-export-personal-data.md).

## <a name="step-5-create-and-manage-funnel-reports"></a>5. korak: ustvarjanje in upravljanje poročil o lijakih

V poročilo o lijakih so zbrane informacije o korakih, ki nastopijo med dejavnostmi strank na vaši spletni strani ali v vaši mobilni aplikaciji. Poleg ustvarjanja vnaprej pripravljenih poročil o profilu in poročil po meri lahko ustvarite tudi poročilo o lijaku, da ugotovite poti, ki jih vaše stranke opravijo pred nakupom. 

1. [Ustvarite poročilo o lijaku](funnel-reports.md) za obveščanje o odločitvah in opredelitev področij za optimizacijo in izboljšave procesov.

1. Ko ste svojo mobilno aplikacijo opremili z vpogledi v interakcije [kompleta za razvoj programske opreme za Android](get-started-android.md) ali [kompleta za razvoj programske opreme za iOS](get-started-ios.md), lahko pripravite poročila o lijakih v različnih kanalih.

1. Z [vpogledi v lijake](funnel-reports.md#funnel-insights) pridobite podrobnejši vpogled v vedenje strank glede korakov v vašem poročilu o lijaku.
 
## <a name="step-6-stay-connected"></a>6. korak: Ostanite povezani

Zahvaljujemo se vam za aktivno udeležbo in upoštevamo vse pomembne povratne informacije pri razvoju prihodnjih izdaj. Delite svoje povratne informacije in prijavite težave po enem od teh kanalov:
- [»Skupnost](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Posredovanje povratnih informacij](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Zahteva za podporo](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
