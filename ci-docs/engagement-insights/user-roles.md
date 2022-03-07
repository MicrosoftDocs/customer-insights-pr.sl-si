---
title: Vloge in dovoljenja
description: Pregled razpoložljivih vlog in dovoljenj za člane delovnega prostora.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036713"
---
# <a name="roles-and-permissions"></a>Vloge in dovoljenja

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Delovni prostor je način shranjevanja ter upravljanja dogodkov in poročil. Član je uporabnik, ki lahko dostopa do delovnega prostora. V delovni prostor lahko dodelite člane ter določite njihove vloge in dovoljenja. Skrbniške vloge upravljajo delovne prostore in okolja ter konfigurirajo vpoglede v interakcijo za druge uporabnike. Vloge sodelavcev so usmerjene na analitike, ki jim ni treba konfigurirati vpogledov v interakcije, ampak želijo ustvariti lastna poročila, lijake ali segmente.

## <a name="permissions"></a>Dovoljenja
  
Naslednji grafikon določa dovoljenja za vsako vlogo. 

| Dovoljenje | Skrbnik okolja | Skrbnik delovnega prostora | Sodelavec za okolje | Sodelavec za delovni prostor | 
|--|--|--|--|--|
| Ustvarjanje okolja (ustvarjalec samodejno postane skrbnik okolja) | X* | X* | X* | X* |  
| Konfiguriranje okolja (člani okolja, brisanje okolja) | X |  |  |  |  
| Ustvarjanje delovnih prostorov | X |  |  |  |  
| Konfiguriranje delovnih prostorov (člani delovnega prostora, brisanje delovnega prostora) | X | X |  |  |  
| Konfiguriranje dogodkov in izboljšanih dogodkov | X | X | |  |  
| Ogled dogodkov in izboljšanih dogodkov v delovnem prostoru | X | X | |  |  
| Ogled virov delovnega prostora (poročila, segmenti in meritve)| X | X | X | X |  
| Ustvarjanje poročil in lijakov po meri | X | X | X | X |  
| Ustvarjanje osnovnih meritev in dimenzij| X | X |  |  |  
| Ustvari segmente| X | X | X | X |  

*V predogledni različici lahko ustvarite samo poskusne različice okolja. 

## <a name="add-members"></a>Dodaj člane

Člane lahko dodajate in odstranjujete iz delovnih prostorov in okolij. Za več informacij glejte [Okolja in delovni prostori](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
