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
ms.openlocfilehash: fb97b721cc82ccd23cfd1df74a0712b8fc277b8a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082123"
---
# <a name="enrichment-for-data-sources-preview"></a>Obogatitev za vire podatkov (predogled)

Uporabite podatke iz virov, kot so Microsoft in drugi partnerji, da obogatite svoje podatke o strankah pred poenotenjem podatkov. Obogatitve vir podatkov pomagajo ustvariti večjo popolnost in kakovost podatkov, kar lahko pomaga doseči boljše rezultate, ko poenotite svoje podatke. Na primer, uporaba normalizirane in standardizirane oblike za naslove poveča kakovost rezultatov ujemanja. Za seznam podprtih obogatitev glejte [podprte možnosti obogatitve vir podatkov](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Obogatite vir podatkov

Za ustvarjanje ali urejanje obogatitev morate imeti dovoljenja sodelavec ali skrbnika. Za več informacij glejte razdelek [Dovoljenja](permissions.md).  

1. Pojdi do **Podatki** > **Poenoti**. Izberite entiteto, ki jo želite obogatiti, in izberite en atribut kot primarni ključ za entiteto. Za več informacij glejte [Izberite primarni ključ](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Pojdite na **Podatki** > **Viri podatkov**.

1. Izberite navpično elipso (&vellip;) poleg vir podatkov, ki ga želite obogatiti in izbrati **Obogatite**.

   :::image type="content" source="media/data_sources_enrich.png" alt-text="Stran z viri podatkov z označeno Obogati":::

   The **Odkrijte** zavihek prikaže [podprte možnosti obogatitve vir podatkov](#supported-data-source-enrichments).

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Stran za obogatitev virov podatkov.":::

1. Izberite **Obogatite moje podatke** za konfiguriranje obogatitve vir podatkov. Ime izhodne entitete se samodejno izpolni.

## <a name="supported-data-source-enrichments"></a>Podprte obogatitve vir podatkov

Za vire podatkov so trenutno na voljo naslednje obogatitve. Oglejte si podrobne korake za obogatitev, da se naučite, kako jo konfigurirati.

- [Izboljšani naslovi](enrichment-enhanced-addresses.md)
- [Izboljšani podatki podjetja](enrichment-enhanced-company-data.md)
- [Podatki o identiteti iz LiveRamp](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Upravljajte obstoječe obogatitve vir podatkov

Za ogled vseh konfiguriranih obogatitev odprite zavihek **Moje obogatitve**.

Izberite obogatitev, da si ogledate razpoložljive možnosti. Izberete lahko tudi navpično elipso (&vellip;) na element seznama, da si ogledate možnosti. Če ste konfigurirali več obogatitev, jih lahko hitro poiščete v polju za iskanje.

Ogledate si lahko, uredite, zaženete ali izbrišete obogatitev vir podatkov. Za več informacij glejte [Upravljajte obstoječe obogatitve](enrichment-hub.md).
