---
title: Začetek uporabe zmogljivosti vpogledov v interakcije
description: Pregled virov za pomoč za hiter začetek.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 644b125f5d140627d357630ded88dd6838d6edb7
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494614"
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

1. Preglejte **Pogoje uporabe vpogledov v interakcije (predogledna različica)** in **Izjavo o zasebnosti** in nato izberite **Raziščite predstavitev**, da sprejmete te nastavitve.

1. Raziskujte izdelek z naborom vzorčnih podatkov.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>3. korak: Nastavitev delovnega prostora in dodajanje kode na spletno mesto

Delovni prostor je kraj, kjer si lahko v realnem času ogledate dejavnosti uporabnika ter shranite in upravljate poročila. Za začetek zbiranja *dogodkov*, tj. dejavnosti, ki prihajajo od uporabnikov, dodajte kodo na spletno mesto.

1. [Ustvarite delovni prostor](create-workspace.md) in dodajte člane.

1. [Dodajte kodo na svoje spletno mesto](instrument-website.md) ali v [mobilno aplikacijo](developer-resources.md#capture-events-from-mobile-apps) in si oglejte, kako se dejavnost uporabnikov namešča v vaš delovni prostor.

1. Oglejte si [sprotno poročilo](view-reports.md), ki prikazuje aktivne uporabnike glede na brskalnik, napravo, operacijski sistem, lokacijo in jezik. Lahko tudi ustvarjate [poročila po meri](custom-reports.md), da ustvarite lastne vizualizacije.
    
## <a name="step-4-export-data-to-other-channels"></a>4. korak: izvoz podatkov v druge kanale

Lahko ustvarjate *izboljšane dogodke* (virtualni pogled) vaših podatkov spletne analitike. Nato podatke filtrirajte in izvozite v Azure Data Lake Storage. Izvožene podatke lahko uvozite kot vir podatkov. Za več informacij glejte [Ustvarjanje povezave med vpogledi občinstva in vpogledi v interakcije](integrate-audience-insights-engagement-insights.md).

1. [Ustvarite izboljšane dogodke](refined-events.md) za izvoz.

1. [Izvozite podatke](export-events.md) v Data Lake Storage.

1. [Ustvarite povezavo med vpogledi v občinstvo in vpogledi v interakcije](integrate-audience-insights-engagement-insights.md) za skupno rabo podatkov med obema zmogljivostma.

1. Naučite se [izbrisati in izvoziti podatke o dogodkih, ki vsebujejo osebne podatke](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>5. korak: Ostanite povezani

Zahvaljujemo se vam za aktivno udeležbo in upoštevamo vse pomembne povratne informacije pri razvoju prihodnjih izdaj. Delite svoje povratne informacije in prijavite težave po enem od teh kanalov:
- [»Skupnost](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Posredovanje povratnih informacij](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Zahteva za podporo](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
