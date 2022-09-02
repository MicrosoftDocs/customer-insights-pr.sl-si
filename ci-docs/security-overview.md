---
title: Konfigurirajte varnostne nastavitve
description: Več o varnostnih nastavitvah v Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: d20d57e9b7724e9921f9341eeaa39141b4555ff1
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387278"
---
# <a name="configure-security-settings"></a>Konfigurirajte varnostne nastavitve

Upravljajte ključe API, dostopajte do podatkov o strankah in nastavite zasebno povezavo Azure.

## <a name="manage-api-keys"></a>Upravljanje ključev API

Ogled in upravljanje ključev za uporabo [API-ji Customer Insights](apis.md) s podatki v vašem okolju.

1. Pojdi do **skrbnik** > **Varnost** in izberite **API-ji** zavihek.

1. Če API dostop do okolja ni nastavljen, izberite **Omogoči** . Če želite blokirati dostop API-ja do okolja, izberite **Onemogoči** in potrdite.

1. Upravljanje primarnih in sekundarnih ključev API:

   1. Če želite prikazati primarni ali sekundarni ključ API, izberite **Prikaži** simbol.

   1. Če želite kopirati primarni ali sekundarni ključ API, izberite **Kopirati** simbol.

   1. Če želite ustvariti nove primarne ali sekundarne ključe API, izberite **Regeneriraj primarno** oz **Regeneriraj sekundarno** .

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Varen dostop do podatkov strank s Customer Lockbox (predogled)

Customer Insights uporablja Power Platform Zmogljivost Customer Lockbox. Customer Lockbox ponuja vmesnik za pregled in odobritev (ali zavrnitev) zahtev za dostop do podatkov. Te zahteve se pojavijo, ko je za razrešitev primera podpore potreben dostop do podatkov o strankah. Za uporabo te funkcije mora imeti Customer Insights obstoječo povezavo z a Microsoft Dataverse okolje v vašem najemniku.

Za več informacij o Customer Lockbox glejte [povzetek](/power-platform/admin/about-lockbox#summary) od Power Platform Ključavnica za stranke. Članek opisuje tudi [potek dela](/power-platform/admin/about-lockbox#workflow) in zahtevano [nastaviti](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) da omogočite Customer Lockbox.

> [!IMPORTANT]
> Globalni skrbniki za Power Platform oz Power Platform skrbniki lahko odobrijo zahteve Customer Lockbox, izdane za Customer Insights.

## <a name="set-up-an-azure-private-link"></a>Nastavite zasebno povezavo Azure

[Zasebna povezava Azure](/azure/private-link/private-link-overview) omogoča, da se Customer Insights poveže z vašim Azure Data Lake Storage računa prek zasebnega končna točka v vašem virtualnem omrežju. Za podatke v računu za shranjevanje, ki ni izpostavljen javnemu internetu, Zasebna povezava omogoča povezavo s tem omejenim omrežjem.

> [!IMPORTANT]
> Minimalne zahteve glede vloge za nastavitev povezave zasebne povezave:
>
> - Customer Insights: Administrator
> - Vgrajena vloga Azure: [Račun za shranjevanje sodelavec](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Dovoljenja za vlogo Azure po meri: [Microsoft.Storage/storageAccounts/read in Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. V Customer Insights pojdite na **skrbnik** > **Varnost** in izberite **Zasebne povezave** zavihek.

1. Izberite **Dodaj zasebno povezavo** .

   The **Dodaj zasebno povezavo** v podoknu so navedeni računi za shranjevanje vašega najemnika, za ogled katerih imate dovoljenja.

1. Izberite naročnino, skupino virov in račun za shranjevanje.

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se** .

1. Izberite **Shrani**.

1. Pojdite na svoj račun Data Lake Storage in odprite povezavo na zaslonu.

1. Odobrite zasebno povezavo.


[!INCLUDE [footer-include](includes/footer-banner.md)]
