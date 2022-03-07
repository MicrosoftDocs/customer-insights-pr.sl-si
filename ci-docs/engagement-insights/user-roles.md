---
title: Vloge in dovoljenja
description: Pregled razpoložljivih vlog in dovoljenj za člane delovnega prostora.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ccc6a1b87b4cc28701e276b6e35432356e7647c4
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227559"
---
# <a name="roles-and-permissions"></a>Vloge in dovoljenja

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Delovni prostor je prostor, kjer shranjujete in upravljate dogodke in poročila. Za več informacij glejte razdelek [Ustvarjanje delovnega prostora in dodajanje članov](create-workspace.md). 

Delovni prostor lahko vključuje naslednje vloge in dovoljenja:

- Vloge *Član* so uporabniki, ki lahko dostopajo do delovnega prostora. V delovni prostor lahko dodelite člane ter določite njihove vloge in dovoljenja. 
- Vloge *Skrbnik* upravljajo delovne prostore in okolja ter konfigurirajo vpoglede v interakcijo za druge uporabnike. 
- Vloge *Sodelavec* so namenjene analitikom, ki jim ni treba konfigurirati vpogledov v interakcije, ampak želijo ustvariti lastna poročila, lijake ali segmente.

## <a name="permissions"></a>Dovoljenja
  
Naslednja tabela določa dovoljenja za vsako vlogo. 

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
