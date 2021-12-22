---
title: Aktivirajte pravila soglasja za segmente
description: Sledite tem korakom, da povežete podatke o privolitvi in aktivirate preverjanja privolitve v občinstvo Insights. Skrbnik lahko tudi onemogoči preverjanja privolitve.
ms.date: 11/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 552cb0739c4d17266dd028638df067f3384b738a
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884094"
---
# <a name="activate-consent-rules"></a>Aktivirajte pravila o soglasju

The [Center za soglasje (predogled)](../consent-management/overview.md) vam pomaga uskladiti podatke o privolitvi iz različnih virov. Uporabite poenoteno *soglasje* subjekt za uporabo privzetih preverjanj privolitve. Po uvozu podatkov o privolitvi v center za privolitev in konfiguriranju pravil za podatke, se *soglasje* entiteta se samodejno sinhronizira z občinstvo vpogledi.

## <a name="enable-consent-checks"></a>Omogočanje preverjanja soglasja

Če so podatki o privolitvi uvoženi v središče za soglasje (predogled) in nastavljena pravila, lahko omogočite preverjanja privolitve. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Zavihek za privolitev v nastavitvah vpogledov občinstvo z aktiviranimi podatki o privolitvi.":::

1. Pri vpogledih v občinstvo izberite **Skrbnik** > **Sistem**.

1. Izberite **Soglasje (predogled)** zavihek.

1. V **Omogoči preverjanje privolitve** razdelku, nastavite preklop na **Vklopljeno** za vsa področja, ki jih želite omogočiti.

1. Izberite **Dovoli preglasitev privzetih pravil za soglasje** potrditveno polje za odstranitev privzetih preverjanj privolitve, uveljavljenih za določen segment. 

1. V spustnem meniju izberite, kje želite dovoliti preglasitve.     

1. V **Povežite soglasje s profili strank** v razdelku izberite atribut, ki se uporablja kot identifikator za povezavo podatkov o privolitvi s podatki strank. Verjetno bo to telefonska številka ali e-poštni naslov. 

1. Izberite **Shrani** da uporabite svoje nastavitve.

## <a name="disable-consent-checks"></a>Onemogoči preverjanje privolitve

Če želite prenehati uporabljati podatke o soglasju v občinstvo Insights, mora skrbnik ustrezno posodobiti sistemske nastavitve.

1. Pri vpogledih v občinstvo izberite **Skrbnik** > **Sistem**.

1. Izberite **Soglasje (predogled)** zavihek.

1. V **Omogoči preverjanje privolitve** razdelku, nastavite preklop na **Izklopljeno**.

> [!TIP]
> Če želite prenehati uporabljati zmožnost upravljanja privolitve, glejte [Sistemske nastavitve v središču za soglasje (predogled)](../consent-management/system-settings.md).
