---
title: Upravljajte privzeta pravila za soglasje za segmente
description: Z zmožnostjo upravljanja privolitve lahko onemogočite ali spremenite privzeta pravila za privolitev, če so preglasitve omogočene.
ms.date: 12/01/2021
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 764eeca9d99c95a34d9bd4c11d79f8b8e90701e2
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755236"
---
# <a name="disable-or-change-default-consent-rules"></a>Onemogočite ali spremenite privzeta pravila za soglasje

Če vaša organizacija uporablja [sposobnost upravljanja privolitve](consent-management/overview.md) z Dynamics 365 Customer Insights,[skrbniki lahko uveljavljajo pravila o soglasju](activate-consent.md) za segmente. 

Z uveljavljenimi pravili privolitve v segmentnem območju vsak segment obvešča o stanju preverjanja soglasja in pravilih. Če so preglasitve dovoljene, so privzeta pravila za soglasje izklopljena za določene segmente. Vsak ustvarjalec segmenta lahko segmentu doda več pravil za privolitev na privzeta pravila. 

## <a name="for-administrators"></a>Za skrbnike

:::image type="content" source="consent-management/media/consent-rules-segment.png" alt-text="Ustvarjalnik segmentov z možnostmi pravil za soglasje.":::

**Če želite deaktivirati privzeta pravila za soglasje:**

1. V **Pravila o soglasju** obvestilo, izberite **Oglejte si podrobnosti**. 

1. Nastavite **Privzeta pravila za soglasje** preklopi na **Izklopljeno**.

**Če želite dodati več pravil za soglasje:**

1. V **Pravila o soglasju** obvestilo, izberite **Oglejte si podrobnosti**. 

1. Izberite **Dodajte pravila za soglasje** in izberite pravilo za soglasje med **Izberite vrsto podatkov o soglasju** spustni meni.

1. Izberite **Shrani** za uporabo novega pravila za segment.

## <a name="for-contributors"></a>Za sodelavce

Če želite ustvariti segment brez uveljavljenih pravil za soglasje, jih morate v sodelovanju s skrbnikom onemogočiti v svojem segmentu. Lahko pa dodate svoja pravila za soglasje segmentom, ki ste jih lastnik in upravljate.

Gre za tristopenjski postopek: 
1. [Ustvarite segment](segments.md) v Customer Insights in ga shranite. 

1. Delite ime segmenta s skrbnikom in ga prosite [omogočite preglasitve za svoj segment](activate-consent.md). 

1. Znova odprite svoje segmente. V **Pravila o soglasju** obvestilo, izberite **Oglejte si podrobnosti** in dodajte pravila o soglasju, ki jih želite uporabiti. potem **Shrani** in **teci** vaš segment.



[!INCLUDE [footer-include](includes/footer-banner.md)] 
