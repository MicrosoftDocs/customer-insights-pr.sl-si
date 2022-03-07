---
title: Dodajanje kode na spletno mesto
description: Dodajanje izrezka kode za zajemanje dogodkov aplikacije Dynamics 365 Customer Insights na vašem spletnem mestu.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 99e1c04877993a9cd81912e3d400402aab06a7de
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231042"
---
# <a name="install-the-web-sdk-on-a-website"></a>Nameščanje spletnega kompleta za razvoj programske opreme na spletno mesto

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ta članek opisuje, kako skrbnik namesti spletni komplet za razvoj programske opreme (SDK) na spletno mesto. Dogodke v svojem delovnem prostoru boste videli kmalu po instrumentiranju spletnega mesta. Za več informacij glejte [Upravljanje delovnih prostorov in okolja](manage-environments-workspaces.md). Če želite zajeti dogodke v mobilnih aplikacijah, glejte [Pregled virov za razvijalce](developer-resources.md).


### <a name="prerequisites"></a>Zahteve

* Za shranjevanje podatkov morate imeti skrbniška dovoljenja za delovni prostor.
* Za pošiljanje podatkov o dejavnosti mora vaše spletno mesto ali projekt gostovati na spletu. Podatkov, poslanih iz lokalne datoteke, strežnik ne bo sprejel.


## <a name="add-web-sdk-to-your-website"></a>Dodajanje spletnega kompleta za razvoj programske opreme na spletno mesto

Odprite razdelek **Skrbnik** > **Delovni prostor** in nato izberite **Vodnik za namestitev**. Obstajata dve možnosti za namestitev spletnega kompleta za razvoj programske opreme. Prva je uporaba povezave za prenos, druga pa namestitev paketa upravitelja paketov vozlišč (NPM).

### <a name="option-1-using-the-download-link"></a>1. možnost: uporaba povezave za prenos

1. Izberite **Kopiraj kodo** za kopiranje izrezka kode. Privzeto je ključ za uvoz za delovni prostor vdelan v izrezek kode.
  :::image type="content" source="media/copy-code.png" alt-text="Posnetek zaslona strani z izrezkom kode.":::

1. Kopirano kodo dodajte na svoje spletno mesto v bližini <head> oznake in pred katerim koli drugim skriptom oz. oznako CSS.
1. Objavite posodobljeno spletno mesto in počakajte nekaj minut, da zabeležite dohodni spletni promet.
1. Če si želite ogledati podatke, izberite delovni prostor v preklopniku za delovni prostor v podoknu za krmarjenje. Nato izberite eno od poročil v razdelku **Odkrivanje**.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>2. možnost: uporaba paketa upravitelja paketov vozlišč (priporočeno za spletne aplikacije, ki temeljijo na JavaScriptu)

1. Obiščite našo [spletno stran paketa upravitelja paketov vozlišč](https://www.npmjs.com/package/engagementinsights-web) in sledite navodilom za namestitev in nastavitev spletnega paketa SDK paketa upravitelja paketov vozlišč.
1. Objavite posodobljeno spletno mesto in počakajte nekaj minut, da zabeležite dohodni spletni promet.
1. Če si želite ogledati podatke, izberite delovni prostor v preklopniku za delovni prostor v podoknu za krmarjenje. Nato izberite eno od poročil v razdelku **Odkrivanje**.

## <a name="configuration-options"></a>Možnosti konfiguracije

V izrezku kode lahko spremenite naslednje konfiguracijske možnosti:

- **ingestionKey**: ključ za uvoz, ki se uporablja za pošiljanje dogodkov v vaš delovni prostor. Spremenite lahko ključ za sprejemanje, če želite dogodke poslati v drug delovni prostor. Ključ za sprejemanje je edinstven za vsak delovni prostor.
- **autoCapture**: določa, ali bodo zabeleženi ogledi strani in interakcije s spletnim mestom. Na voljo sta dve možnosti:
    - **view**: nastavite na *true* za beleženje ogledov strani. Ogledi strani so zabeleženi kot [dogodki](glossary.md#event) *ogleda*, tj. vrsta [osnovnega dogodka](glossary.md#base-event).
    - **click**: nastavite na *true* za beleženje interakcij obiskovalcev na spletnem mestu. Interakcije so zabeležene kot [dogodki](glossary.md#event) *dejanja*, tj. vrsta [osnovnega dogodka](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
