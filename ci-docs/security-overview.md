---
title: Varnostne nastavitve v Dynamics 365 Customer Insights
description: Več o varnostnih nastavitvah v Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653809"
---
# <a name="security-overview-page"></a>Stran s pregledom varnosti

The **Varnost** stran navaja možnosti za konfiguriranje uporabniških dovoljenj in funkcij, ki pomagajo pri ustvarjanju Dynamics 365 Customer Insights bolj varno. Do te strani lahko dostopajo samo skrbniki. 

Pojdi do **Admin** > **Varnost** da konfigurirate nastavitve.

The **Varnost** stran vključuje naslednje zavihke:
- [Uporabniki](#users-tab)
- [API-ji](#apis-tab)
- [Key Vault](#key-vault-tab)

## <a name="users-tab"></a>Zavihek Uporabniki

Dostop do Customer Insights je omejen na uporabnike v vaši organizaciji, ki jih je v aplikacijo dodal skrbnik. The **Uporabniki** zavihek vam omogoča upravljanje dostopa uporabnikov in njihovih dovoljenj. Za več informacij glejte [Uporabniška dovoljenja](permissions.md).

## <a name="apis-tab"></a>Zavihek API-ji

Oglejte si in upravljajte ključe za uporabo [API-ji Customer Insights](apis.md) s podatki vašega okolja.

Z izbiro lahko ustvarite nove primarne in sekundarne ključe **Regenerirajte primarno** oz **Regenerirajte sekundarno**. 

Če želite blokirati dostop API-ja do okolja, izberite **Onemogoči**. Če so API-ji onemogočeni, lahko izberete **Omogoči** za ponovno odobritev dostopa.

## <a name="key-vault-tab"></a>Zavihek Trezor ključev

The **Trezor ključev** zavihek vam omogoča povezovanje in upravljanje lastnega [Azurni trezor ključev](/azure/key-vault/general/basic-concepts) okolju.
Dodeljena shramba ključev se lahko uporablja za pripravo in uporabo skrivnosti na meji zagotavljanja skladnosti organizacije. Customer Insights lahko uporabi skrivnosti v Azure Key Vault za [vzpostaviti povezave](connections.md) na sisteme tretjih oseb.

Za več informacij glejte [Uporaba lastne shrambe ključev Azure](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
