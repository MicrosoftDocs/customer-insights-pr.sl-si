---
title: Dodajanje kode na spletno mesto
description: Kako dodati izrezek kode za beleženje dogodkov na vašem spletnem mestu.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035114"
---
# <a name="install-the-code-snippet-on-a-website"></a>Nameščanje izrezka kode na spletno mesto

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ta članek opisuje, kako skrbnik namesti izrezek kode na spletno mesto. Dogodke v delovnem prostoru boste začeli videti kmalu po dodajanju skripta na svoje spletno mesto. Za več informacij glejte [Upravljanje delovnih prostorov in okolja](manage-environments-workspaces.md). Če želite zajeti dogodke v mobilnih aplikacijah, glejte [Pregled virov za razvijalce](developer-resources.md).


### <a name="prerequisites"></a>Zahteve

* Za shranjevanje podatkov morate imeti skrbniška dovoljenja za delovni prostor.
* Za pošiljanje podatkov o dejavnosti mora vaše spletno mesto ali projekt gostovati na spletu. Podatkov, poslanih iz lokalne datoteke, strežnik ne bo sprejel.


## <a name="add-code-to-your-website"></a>Dodajanje kode na spletno mesto
1.  Pojdi na **Skrbnik** > **Delovni prostor** in nato izberite **Vodnik za namestitev**.
1. Izberite **Kopiraj kodo** za kopiranje izrezka kode. Privzeto je ključ za uvoz za delovni prostor vdelan v izrezek kode.
:::image type="content" source="media/copy-code.png" alt-text="Posnetek zaslona strani z izrezkom kode.":::
3. Kopirani izrezek kode dodajte na svoje spletno mesto, blizu <head> oznake in pred katerim koli drugim skriptom oz. oznako CSS.
4.  Objavite posodobljeno spletno mesto in počakajte nekaj minut, da zabeležite dohodni spletni promet.
5.  Če si želite ogledati podatke, izberite delovni prostor v preklopniku za delovni prostor v podoknu za krmarjenje. Nato izberite eno od poročil v razdelku **Odkrivanje**.

## <a name="configuration-options"></a>Možnosti konfiguracije

V izrezku kode lahko spremenite naslednje konfiguracijske možnosti:

- **ingestionKey**: ključ za uvoz, ki se uporablja za pošiljanje dogodkov v vaš delovni prostor. Spremenite lahko ključ za sprejemanje, če želite dogodke poslati v drug delovni prostor. Ključ za sprejemanje je edinstven za vsak delovni prostor. 
- **autoCapture**: določa, ali bodo zabeleženi ogledi strani in interakcije s spletnim mestom. Na voljo sta dve možnosti:
    - **view**: nastavite na *true* za beleženje ogledov strani. Ogledi strani so zabeleženi kot [dogodki](glossary.md#event) *ogleda*, tj. vrsta [osnovnega dogodka](glossary.md#base-event).
    - **click**: nastavite na *true* za beleženje interakcij obiskovalcev na spletnem mestu. Interakcije so zabeležene kot [dogodki](glossary.md#event) *dejanja*, tj. vrsta [osnovnega dogodka](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
