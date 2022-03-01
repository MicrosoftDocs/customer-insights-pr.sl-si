---
title: Začetek uporabe zmogljivosti vpogledov v interakcije
description: Pregled virov za pomoč za hiter začetek.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405378"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Začetek uporabe zmogljivosti vpogledov v interakcije Dynamics 365 Customer Insights (predogledna različica za javnost)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Zmogljivost vpogledov v interakcije vam omogoča zbiranje in merjenje vedenja strank na vašem spletnem mestu. Integrira se s funkcijo vpogledov v interakcije, tako da si lahko poleg poročil o profilu strank ogledate bogato vedenjsko analizo v realnem času. Povezave v tem članku vam pomagajo hitro konfigurirati in nastaviti okolje.

## <a name="step-1-review-prerequisites"></a>1. korak: Pregled zahtev

Najprej morate imeti aktiven uporabniški račun za Microsoft Azure Active Directory. Nato preberite naslednje članke, preden nastavite delovni prostor za vpoglede v interakcije.

- Preglejte in sprejmite [pogoje storitve](terms-of-service.md) pri Microsoftu.  
- Preberite članek [Upravljanje piškotkov in soglasja uporabnika](user-consent-storage.md). Po pregledu tega članka ocenite, ali morate posodobiti obvestilo o soglasju uporabnika. Če prej niste imeli »nebistvenih« piškotkov, boste verjetno morali posodobiti pravilnik o svojem spletnem mestu.
- Preglejte [glosar](glossary.md) za hiter uvod v ključne pojme in koncepte.

## <a name="step-2-explore-engagement-insights"></a>2. korak: Raziskovanje vpogledov v interakcije

Ko prvič obiščete vpoglede v interakcije, lahko konfigurirate nastavitve, pregledate pravilnike in raziščete izdelek.

1. Vpišite se v [portal za zmogljivosti vpogledov v interakcije](https://pi.dynamics.com) z uporabo uporabniškega računa za Microsoft Azure Active Directory. (Lahko je vaš šolski ali službeni račun.)

1. Izberite svojo regijo in s potrditvenim poljem navedite, ali želite omogočiti prejemanje posodobitev in ponudb po e-pošti.

1. Preglejte **pogoje uporabe vpogledov v interakcije (predogled)** in **izjavo o zasebnosti** ter nato izberite **Razišči predstavitev**, da jih sprejmete.

1. Raziskujte izdelek z naborom vzorčnih podatkov.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>3. korak: Nastavitev delovnega prostora in dodajanje kode na spletno mesto

V delovnem prostoru si lahko v realnem času ogledate dejavnosti uporabnikov ter shranite in upravljate poročila. Za začetek zbiranja *dogodkov*, tj. dejavnosti, ki prihajajo od uporabnikov, dodajte kodo na spletno mesto.

1. [Ustvarite delovni prostor](create-workspace.md) in dodajte člane.

1. [Dodajte kodo na svoje spletno mesto](instrument-website.md) ali v [mobilno aplikacijo](developer-resources.md#capture-events-from-mobile-apps) in si oglejte, kako se dejavnost uporabnikov namešča v vaš delovni prostor.

1. Prikažite [poročilo v realnem času](view-reports.md), ki prikazuje aktivne uporabnike po brskalniku, napravi, operacijskem sistemu, lokaciji in jeziku. Lahko tudi ustvarjate [poročila po meri](custom-reports.md), da ustvarite lastne vizualizacije.
    
## <a name="step-4-export-data-to-other-channels"></a>4. korak: izvoz podatkov v druge kanale

Lahko ustvarjate *izboljšane dogodke* (virtualni pogled) vaših podatkov spletne analitike. Nato podatke filtrirajte in izvozite v Azure Data Lake Storage. Izvožene podatke lahko uvozite kot vir podatkov. Za več informacij glejte [Ustvarjanje povezave med vpogledi občinstva in vpogledi v interakcije](integrate-audience-insights-engagement-insights.md).

1. [Ustvarite izboljšane dogodke](refined-events.md) za izvoz.

1. [Izvozite podatke](export-events.md) v Data Lake Storage.

1. Naučite se [izbrisati in izvoziti podatke o dogodkih, ki vsebujejo osebne podatke](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>5. korak: Ostanite povezani

Cenimo vaše aktivno sodelovanje in načrtujemo, da bomo upoštevali vse ustrezne povratne informacije pri razvoju prihodnjih izdaj. Delite svoje povratne informacije in prijavite težave po enem od teh kanalov:
- [»Skupnost](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Posredovanje povratnih informacij](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Zahteva za podporo](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
