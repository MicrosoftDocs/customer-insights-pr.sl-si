---
title: Aktivirajte pravila za soglasje za segmente
description: Sledite tem korakom, da povežete podatke o privolitvi in aktivirate preverjanja privolitve v občinstvo Insights. Skrbnik lahko tudi onemogoči preverjanja privolitve.
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 45899738d39bd5caa433e123f9fe59020e831998
ms.sourcegitcommit: 79b09498d1328e5551fb8684c44af1fb149f9881
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/10/2021
ms.locfileid: "7790795"
---
# <a name="activate-consent-rules"></a>Aktivirajte pravila o soglasju

The [Center za soglasje (predogled)](../consent-management/overview.md) vam pomaga uskladiti podatke o privolitvi iz različnih virov. Uporabite poenoteno *soglasje* subjekt za uporabo privzetih preverjanj privolitve. Po uvozu podatkov o privolitvi v center za privolitev in konfiguriranju pravil za podatke, se *soglasje* entiteta se samodejno sinhronizira z občinstvo vpogledi.

## <a name="enable-consent-checks"></a>Omogočanje preverjanja soglasja

S podatki o privolitvi, uvoženimi v središče za soglasje (predogled) in nastavljenimi pravili, lahko omogočite preverjanja privolitve. 

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
