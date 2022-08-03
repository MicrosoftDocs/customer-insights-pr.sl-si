---
title: Obogatitev za vire podatkov (predogled)
description: Obogatite vire podatkov, preden greste skozi postopek poenotenja podatkov.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 98e9e330e7ef9cf085caa94a506fa788cebdd67b
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207203"
---
# <a name="enrichment-for-data-sources-preview"></a>Obogatitev za vire podatkov (predogled)

Uporabite podatke iz virov, kot so Microsoft in drugi partnerji, da obogatite svoje podatke o strankah pred poenotenjem podatkov. Vir podatkov obogatitve pomagajo ustvariti višjo popolnost in kakovost podatkov, kar lahko pomaga doseči boljše rezultate, ko poenotite podatke. Na primer, uporaba normaliziranega in standardiziranega formata za naslove poveča kakovost rezultatov ujemanja. Za seznam podprtih obogatitev glejte [podprte možnosti obogatitve vir podatkov](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Obogatite vir podatkov

Imeti morate sodelavec ali skrbnika [dovoljenja](permissions.md) za ustvarjanje ali urejanje obogatitev.  

1. Pojdi do **podatki** > **Poenotiti**. Izberite entiteto, ki jo želite obogatiti, in izberite en atribut kot a [primarni ključ](map-entities.md#select-primary-key-and-semantic-type-for-attributes) za entiteto.

1. Pojdite na **Podatki** > **Viri podatkov**.

1. Izberite navpično elipso (&vellip;) poleg vir podatkov, ki ga želite obogatiti in izberite **Obogatiti**.

   :::image type="content" source="media/data_sources_enrich.png" alt-text="Stran z viri podatkov z označeno Obogati":::

   The **Odkrij** zavihek prikazuje [podprte možnosti obogatitve vir podatkov](#supported-data-source-enrichments).

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Stran za obogatitev virov podatkov.":::

1. Izberite **Obogati moje podatke** da konfigurirate obogatitev vir podatkov. Ime izhodne entitete se izpolni samodejno.

## <a name="supported-data-source-enrichments"></a>Podprte obogatitve vir podatkov

Za vire podatkov so trenutno na voljo naslednje obogatitve. Preglejte podrobne korake za obogatitev, da se naučite, kako jo konfigurirati.

- [Izboljšani naslovi](enrichment-enhanced-addresses.md)
- [Izboljšani podatki podjetja](enrichment-enhanced-company-data.md)
- [Podatki o identiteti iz LiveRamp](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Upravljajte obstoječe vir podatkov obogatitve

Pomaknite se na možnost **Podatki** > **Obogatitev**. Na **Moje obogatitve** si ogledate konfigurirane obogatitve, njihov status, število obogatenih strank in čas zadnje osvežitve podatkov. Seznam obogatitev lahko razvrstite po katerem koli stolpcu ali uporabite iskalno polje, da poiščete obogatitev, ki jo želite upravljati.

Izberite obogatitev, da si ogledate razpoložljive možnosti. Izberete lahko tudi navpično elipso (&vellip;) na element seznama, da si ogledate možnosti.

Obogatitev vir podatkov si lahko ogledate, uredite, zaženete ali izbrišete. Za več informacij glejte [Upravljajte obstoječe obogatitve](enrichment-hub.md#manage-existing-enrichments).
