---
title: Delo s poslovnimi računi
description: Več o poslovnih računih kot glavnem cilju občinstvo v Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: abb77a720ab737520a905b0c93b65573e669109f
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303936"
---
# <a name="work-with-business-accounts"></a>Delo s poslovnimi računi

The Dynamics 365 Customer Insights vam omogoča, da konfigurirate svoje okolje za različne primarne ciljne skupine: posamezne potrošnike (B-to-C) in poslovne račune (B-to-B). V scenarijih »Prodaja strankam« podatki temeljijo na posameznikih. V scenarijih »Prodaja podjetjem« so primarna ciljna občinstva kupci – organizacije ali podjetja – in stiki. Ta članek vam pomaga začeti z okoljem za poslovne kupce. Navaja razlike za področja funkcij v Customer Insights, odvisno od osredotočenosti na vaše okolje. Če želite več informacij o razlikah, preglejte dokumente o območjih funkcij. 

## <a name="create-an-environment-for-business-accounts"></a>Ustvarjanje okolja za poslovne kupce

Skrbniki lahko [ustvarijo okolje v obstoječi organizaciji](create-environment.md). Korak v postopku ustvarjanja novega okolja od skrbnikov zahteva primarno ciljno občinstvo okolja. Če gre za začetno nastavitev po nakupu licence, vam vodena izkušnja pomaga pri ustvarjanju prvega okolja.

Potem lahko [uvozite podatke](data-sources.md) za poslovne kupce in povezane stike kot vire podatkov iz vseh podprtih virov.

 [Poenotiti](data-unification.md) podatki vašega računa, ki jim sledijo vaši kontaktni podatki, da povežete subjekte stika in računa.

## <a name="switch-between-primary-target-audience"></a>Preklop med primarnim ciljnim občinstvom

Če vaša organizacija vzdržuje okolja za posamezne stranke in poslovne kupce, lahko s preklopnikom v levem podoknu izberete primarno ciljno občinstvo.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Preklopnik za spremembo primarnega ciljnega občinstva med posameznimi strankami in poslovnimi kupci.":::

## <a name="supported-feature-areas"></a>Podprta območja funkcij

- [Dejavnosti](activities.md): podpora za kupce in povezane stike za ustvarjanje dejavnosti in njihovo prikazovanje na časovnici.
- [Odnosi](relationships.md): čarovnik za dejavnosti pomaga ustvariti odnose med entitetami tako, da lahko pogled kupca prikaže vse dejavnosti iz stikov. Stiki se lahko poglobijo, da si ogledate pogled stikov, hierarhije pa lahko uporabite za združevanje dejavnosti kupca.
- [Mere](measures.md): podpira mere, ustvarjene z graditeljem mer, z enim izračunom. Izbirna nastavitev omogoča zbiranje podračunov pri ustvarjanju mer.
- [Segmenti](segments.md): podpira segmente, ki so ustvarjeni od začetka z graditeljem segmentov. Segmenti lahko temeljijo na računih ali stikih.
- [Uvoz podatkov](data-sources.md): vse funkcije na tem področju so enake za poslovne kupce in posamezne stranke.
- Združevanje podatkov B-to-B je zelo podobno združevanju podatkov B-to-C, vendar ima dodaten korak za poenotenje stikov po združevanju računov. glej [Poslovni računi (B-to-B)](data-unification.md).
- [Obogatitev](enrichment-hub.md): nekatere vrste obogatitev so na voljo samo za scenarije posameznih strank, druge pa so na voljo izključno za poslovne stranke.
- [Predvidevanja in pripravljeni modeli](predictions-overview.md): predvidevanje izgube transakcij vsebuje dodatne korake za poslovne kupce. Druga predvidevanja so na voljo samo za posamezne stranke.
- [Aktiviranje in izvoz](export-destinations.md): izvozi so na voljo za poslovne kupce in posamezne stranke. Nekateri izvozi zahtevajo dodatno konfiguracijo in podatke za stik, predvidene v temeljnih segmentih, da veljajo za poslovne kupce.
- [Sistemske nastavitve](system.md) in [upravljanje uporabnikov](permissions.md): vse funkcije na tem področju so enake za poslovne kupce in posamezne stranke.

[!INCLUDE [footer-include](includes/footer-banner.md)]
