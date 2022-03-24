---
title: Vir podatkov obogatitev
description: Obogatite vire podatkov, preden greste skozi postopek poenotenja podatkov.
ms.date: 03/02/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 56f6a8ad20224922f9968f0ad3b6a0e0a400214b
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376599"
---
# <a name="enrichment-for-data-sources-preview"></a>Obogatitev za vire podatkov (predogled)

Uporabite podatke iz virov, kot so Microsoft in drugi partnerji, da obogatite svoje podatke o strankah pred poenotenjem podatkov. Obogatitve vir podatkov pomagajo ustvariti večjo popolnost in kakovost podatkov, kar lahko pomaga doseči boljše rezultate, ko poenotite svoje podatke. Na primer, uporaba normalizirane in standardizirane oblike za naslove poveča kakovost rezultatov ujemanja. Za seznam podprtih obogatitev glejte [podprte možnosti obogatitve vir podatkov](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Obogatite vir podatkov

Za ustvarjanje ali urejanje obogatitev morate imeti dovoljenja sodelavec ali skrbnika. Za več informacij glejte razdelek [Dovoljenja](permissions.md).  

1. Pojdi do **Podatki** > **Poenoti**. Izberite entiteto, ki jo želite obogatiti, in izberite en atribut kot primarni ključ za entiteto. Za več informacij glejte [Izberite primarni ključ](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Pojdite na **Podatki** > **Viri podatkov**.
 
1. Izberite navpično tritočko poleg vir podatkov, ki jo želite obogatiti, in izberite **Obogatite**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Stran za obogatitev virov podatkov.":::

   The **Odkrij** zavihek prikaže [podprte možnosti obogatitve vir podatkov](#supported-data-source-enrichments).

1. Izberite **Obogatite moje podatke** da konfigurirate obogatitev vir podatkov. Ime izhodne entitete se samodejno izpolni.

## <a name="supported-data-source-enrichments"></a>Podprte obogatitve vir podatkov

Za vire podatkov so trenutno na voljo naslednje obogatitve. Preglejte podrobne korake za obogatitev, da se naučite, kako jo konfigurirati.

- [Izboljšani naslovi](enrichment-enhanced-addresses.md)
- [Izboljšani podatki podjetja](enrichment-enhanced-company-data.md)

## <a name="manage-existing-data-source-enrichments"></a>Upravljajte obstoječe vir podatkov obogatitve

Za ogled vseh konfiguriranih obogatitev odprite zavihek **Moje obogatitve**.

Izberite obogatitev, da si ogledate razpoložljive možnosti. Za ogled možnosti lahko izberete tudi treh pik (...) na elementu seznama. Če ste konfigurirali več obogatitev, jih lahko hitro poiščete v polju za iskanje.

Ogledate si lahko, uredite, zaženete ali izbrišete obogatitev vir podatkov. Za več informacij glejte [Upravljajte obstoječe obogatitve](enrichment-hub.md).
