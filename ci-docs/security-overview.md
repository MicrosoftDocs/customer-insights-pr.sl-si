---
title: Varnostne nastavitve v Customer Insights
description: Več o varnostnih nastavitvah v Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947435"
---
# <a name="security-settings-in-customer-insights"></a>Varnostne nastavitve v Customer Insights

The **Varnost** stran navaja možnosti za konfiguriranje uporabniških dovoljenj in funkcij, ki pomagajo pri ustvarjanju Dynamics 365 Customer Insights bolj varno. Do te strani lahko dostopajo samo skrbniki.

Pojdi do **Admin** > **Varnost** da konfigurirate nastavitve.

The **Varnost** stran vključuje naslednje zavihke:

- [Uporabniki](#users-tab)
- [API-ji](#apis-tab)
- [Zasebne povezave](#private-links-tab)
- [Key Vault](#key-vault-tab)
- [Varen dostop do podatkov strank s ključavnico za stranke (predogled)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Zavihek Uporabniki

Dostop do Customer Insights je omejen na uporabnike v vaši organizaciji, ki jih je v aplikacijo dodal skrbnik. The **Uporabniki** zavihek vam omogoča upravljanje dostopa uporabnikov in njihovih dovoljenj. Za več informacij glejte [Uporabniška dovoljenja](permissions.md).

## <a name="apis-tab"></a>Zavihek API-ji

Oglejte si in upravljajte ključe za uporabo [API-ji Customer Insights](apis.md) s podatki vašega okolja.

Z izbiro lahko ustvarite nove primarne in sekundarne ključe **Regenerirajte primarno** oz **Regenerirajte sekundarno**. 

Če želite blokirati dostop API-ja do okolja, izberite **Onemogoči**. Če so API-ji onemogočeni, lahko izberete **Omogoči** za ponovno odobritev dostopa.

## <a name="private-links-tab"></a>Zavihek Zasebne povezave

[Zasebna povezava Azure](/azure/private-link/private-link-overview) naj se Customer Insights poveže z vašim Azure Data Lake Storage račun prek zasebnega končna točka v vašem virtualnem omrežju. Za podatke v računu za shranjevanje, ki ni izpostavljen javnemu internetu, Zasebna povezava omogoča povezavo s tem omejenim omrežjem.

> [!IMPORTANT]
> Minimalna zahteva za vlogo za nastavitev povezave zasebne povezave:
>
> - Vpogled v stranke: skrbnik
> - Vgrajena vloga Azure: [Račun za shranjevanje sodelavec](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Dovoljenja za vlogo Azure po meri: [Microsoft.Storage/storageAccounts/read in Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

Nastavitev zasebne povezave v storitvi Customer Insights je postopek v dveh korakih. Najprej začnete ustvarjanje zasebne povezave iz **Admin** > **Varnost** > **Zasebne povezave** v Customer Insights. The **Dodaj zasebno povezavo** podokno navaja račune za shranjevanje vašega najemnika, za ogled katerih imate dovoljenja. Izberite račun za shranjevanje in podajte soglasje za ustvarjanje zasebne povezave.

Nato morate odobriti zasebno povezavo na strani računa Data Lake Storage. Odprite povezavo, prikazano na zaslonu, da odobrite novo zasebno povezavo.

## <a name="key-vault-tab"></a>Zavihek Trezor ključev

The **Trezor ključev** zavihek vam omogoča povezovanje in upravljanje lastnega [Azurni trezor ključev](/azure/key-vault/general/basic-concepts) okolju.
Dodeljena shramba ključev se lahko uporablja za pripravo in uporabo skrivnosti na meji zagotavljanja skladnosti organizacije. Customer Insights lahko uporabi skrivnosti v Azure Key Vault za [vzpostaviti povezave](connections.md) na sisteme tretjih oseb.

Za več informacij glejte [Uporaba lastne shrambe ključev Azure](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Varen dostop do podatkov strank s ključavnico za stranke (predogled)

Customer Insights uporablja Power Platform Možnost zaklepanja za stranke. Customer Lockbox ponuja vmesnik za pregled in odobritev (ali zavrnitev) zahtev za dostop do podatkov. Te zahteve se pojavijo, ko je za rešitev primera podpore potreben dostop do podatkov o stranki. Za uporabo te funkcije mora imeti Customer Insights obstoječo povezavo z a Microsoft Dataverse okolje v vašem najemniku.

Za več informacij o Customer Lockbox si oglejte [povzetek](/power-platform/admin/about-lockbox#summary) od Power Platform Lockbox za stranke. Članek opisuje tudi [potek dela](/power-platform/admin/about-lockbox#workflow) in zahtevano [nastaviti](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) da omogočite Customer Lockbox.

> [!IMPORTANT]
> Globalni skrbniki za Power Platform oz Power Platform skrbniki lahko odobrijo zahteve Customer Lockbox, izdane za Customer Insights.

[!INCLUDE [footer-include](includes/footer-banner.md)]
