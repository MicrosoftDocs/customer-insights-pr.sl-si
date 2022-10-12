---
title: Pregled predvidevanj
description: Scenariji in možnosti predvidevanja, ki jih zajema aplikacija Dynamics 365 Customer Insights.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610210"
---
# <a name="predictions-overview"></a>Pregled predvidevanj

Dynamics 365 Customer Insights vsebuje različne možnosti, ki uporabljajo AI in strojno učenje za napovedovanje podatkov.

## <a name="out-of-box-models"></a>Vnaprej pripravljeni modeli

Najlažji način za začetek napovedovanja podatkov predstavljajo vnaprej določeni modeli, ki jih pogosto imenujemo vnaprej pripravljeni modeli. Za hitro ustvarjanje vpogledov potrebujejo le določene podatke in strukturo. Na voljo so naslednji modeli:

# <a name="individual-consumers-b-to-c"></a>[Posamezni potrošniki (prodaja strankam)](#tab/b2c)

- [Vrednost življenjske dobe stranke](predict-customer-lifetime-value.md): napoveduje potencialni prihodek stranke v celotni interakciji s podjetjem.
- [Priporočilo izdelka](predict-product-recommendation.md): predlaga nabore napovednih priporočil za izdelke, ki temeljijo na nakupnem vedenju in strankah s podobnimi vzorci nakupovanja.
- [Izguba naročnin](predict-subscription-churn.md): predvidi, ali za stranko obstaja tveganje, če ne bo več uporabljala naročniških izdelkov ali storitev vašega podjetja.
- [Transakcijski odliv](predict-transactional-churn.md) : Predvidi, ali posamezna stranka ne bo več kupovala vaših izdelkov ali storitev v določenem časovni okvir.
- [Analiza razpoloženja](sentiment-analysis.md) : Analizira razpoloženje povratnih informacij strank in identificira poslovne vidike, ki se pogosto omenjajo.

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (podjetja podjetjem)](#tab/b2b)

- [Transakcijski odliv](predict-transactional-churn.md) : Predvidi, ali račun stranke ne bo več kupoval vaših izdelkov ali storitev v določenem časovni okvir.

---

> [!TIP]
> Priporočamo, da redno osvežujete že pripravljene modele s posodobljenimi podatki, da zagotovite, da bodo pravilno informirali vaš poslovni primer uporabe. Podatki se ad hoc osvežijo, ko sistem zaužije nove ali posodobljene vire podatkov. Vendar bodo modeli samo v tem primeru ponovno ocenili in še naprej uporabljali obstoječe podatke o usposabljanju.
>
> Konfigurirajte an **Posodobi urnik** z nastavitvijo razporeda preusposabljanja modela med konfiguracijo. Model se bo znova usposobil in ponovno ocenil po tem urniku, ki ga lahko kadar koli spremenite.

## <a name="azure-machine-learning-integration"></a>Integracija strojnega učenja Azure

Če organizacija že uporablja scenarije strojnega učenja, ki temeljijo na poskusih strojnega učenja Azure, bo funkcija modelov po meri v Customer Insights pomagala povezovati pike. Ustvarite poteke dela, ki vam pomagajo izbrati podatke, iz katerih želite ustvariti vpogled, in rezultate preslikajte v svoje poenotene profile strank. Za več informacij glejte [Modeli strojnega učenja po meri](custom-models.md).

## <a name="manage-existing-predictions"></a>Upravljajte obstoječe napovedi

Pojdi na **Inteligenca** > **Napovedi** strani. Na **Moje napovedi** si oglejte napovedi, ki ste jih ustvarili, njihov tip predvidevanje, ime izhodne entitete, stanje, čas zadnjega urejanja predvidevanje in čas zadnje osvežitve podatkov. Seznam napovedi lahko razvrstite po kateremkoli stolpcu.

Za ogled razpoložljivih dejanj izberite predvidevanje.

:::image type="content" source="media/predictions.png" alt-text="Moja stran z napovedmi.":::

- **Uredi** predvidevanje, da spremenite njegove lastnosti.
- [**Osveži**](#refresh-a-prediction) predvidevanje za vključitev najnovejših podatkov.
- **Pogled** podrobnosti predvidevanje.
- [**Poročilo o uporabnosti vhodnih podatkov**](#view-the-input-data-usability-report) za ogled napak, opozoril in priporočil.
- **Izbriši** predvidevanje.

### <a name="refresh-a-prediction"></a>Osveževanje predvidevanja

Napovedi je mogoče osvežiti po samodejnem urniku ali ročno na zahtevo. Če želite ročno osvežiti vsa predvidevanja, izberite **Osveži vse**. Če želite ročno osvežiti predvidevanje, ga izberite in izberite **Osveži**. Za [načrtujte samodejno osveževanje](schedule-refresh.md), Pojdi do **skrbnik** > **Sistem** > **Urnik**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>Ogled poročila o uporabnosti vhodnih podatkov

Poročilo o uporabnosti vhodnih podatkov ponuja strnjen prikaz napak in opozoril, ki jih lahko ustvarijo vaše vnaprej pripravljene napovedi. Ponuja tudi priporočila za izboljšanje delovanja modela.

Poročilo je na voljo, ko model zaključi s postopkom kvalificiranja. Izdela se za vsak model posebej, ne glede na to, ali je šolanje opravil uspešno ali ne.

Na **Moje napovedi** zavihek izberite predvidevanje in izberite **Poročilo o uporabnosti vhodnih podatkov**. Ali v pogledu podrobnosti predvidevanje izberite **Poročilo o uporabnosti vhodnih podatkov**.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Primer poročila o uporabnosti vhodnih podatkov, ki prikazuje tabelo z napakami, opozorili in priporočili.":::

Poročilo vključuje:

- **ime:** Opisno ime napake, opozorila ali priporočila.
- **korak:** Faza modela, vlak ali rezultat, informacije se nanašajo na.
- **Država:** Resnost informacije (napaka, opozorilo, priporočilo).
- **Ime stolpca:** Stolpec v entiteti, ki ga je treba spremeniti za izboljšanje zmogljivosti modela.
- **Ime subjekta:** Ime entitete, ki jo je treba spremeniti za izboljšanje zmogljivosti modela.
- **podrobnosti:** Podrobnosti o napaki, opozorilu ali priporočilu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
