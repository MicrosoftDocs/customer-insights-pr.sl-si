---
title: Vključitev podatkov prek povezovalnika Power Query
description: Povezovalniki za podatkovne vire, ki temeljijo na Power Query.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 50c231070ff9930c1ea82971bf4f8541a89d5027
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305911"
---
# <a name="connect-to-a-power-query-data-source"></a>Povezava z virom podatkov Power Query

Power Query ponuja širok nabor povezovalnikov za uvoz podatkov. Dynamics 365 Customer Insights podpira večino teh povezovalnikov. Dodajanje virov podatkov na podlagi povezovalnikov Power Query običajno sledi korakom, opisanim v naslednjem razdelku. Vendar pa so glede na povezovalnik, ki ga uporabljate, potrebne drugačne informacije. Za več informacij glejte dokumentacijo o posameznih povezovalnikih v [sklicih na povezovalnike Power Query](/power-query/connectors/).

## <a name="create-a-new-data-source"></a>Ustvarjanje novega vira podatkov

1. Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.

1. Izberite **Dodaj vir podatkov**.

1. Izberite način **Uvozi podatke** in nato **Naprej**.

1. Vnesite **Ime** za vir podatkov in izberite **Naprej**, da ustvarite vir podatkov. Smernice za poimenovanje: 
   - Začnite s črko.
   - Uporabljajte samo črke in številke. Posebni znaki in presledki niso dovoljeni.
   - Uporabite od 3 do 64 znakov.

1. Izberite enega od [razpoložljivih povezovalnikov](#available-power-query-data-sources). Za ta primer izberemo povezovalnik **Besedilo/CSV**.

1. Vnesite zahtevane podrobnosti v **Nastavitve povezave** za izbrani povezovalnik in izberite **Naprej**, da si ogledate predogled podatkov.

1. Izberite **Pretvori podatke**. V tem koraku boste dodali entitete v vir podatkov. Entitete so nabori podatkov. Če imate zbirko podatkov, ki vključuje več naborov podatkov, je vsak nabor podatkov svoja entiteta.

1. Pogovorno okno **Power Query - Urejanje poizvedb** omogoča pregled in natančnejše določanje podatkov. Entitete, ki jih sistemi, opredeljeni v izbranem viru podatkov, prikažejo v levem podoknu.

   > [!div class="mx-imgBorder"]
   > ![Pogovorno okno urejanja poizvedb](media/data-manager-configure-edit-queries.png "Pogovorno okno urejanja poizvedb")

1. Podatke pa lahko tudi preoblikujete. Izberite entiteto, ki jo želite urediti ali preoblikovati. Uporabite možnosti v oknu Power Query, da uporabite pretvorbe. Vsaka pretvorba je navedena pod **Uporabljeni koraki**. Power Query ponuja številne vnaprej vgrajene možnosti preoblikovanja. Če želite več informacij, glejte razdelek [Pretvorbe Power Query](/power-query/power-query-what-is-power-query#transformations).

1. Virom podatkov lahko dodate dodatne entitete tako, da izberete **Pridobi podatke** v pogovornem oknu **Urejanje poizvedb**.

   Ta preoblikovanja so zelo priporočljiva:

   - Če vnašate podatke iz datoteke CSV, prva vrstica pogosto vsebuje glave. Pojdite na **Tabela pretvorb** in izberite **Uporabi glave kot prvo vrstico**.
   - Prepričajte se, da je vrsta podatkov pravilno nastavljena.

1. Izberite **Shrani** na dnu okna Power Query, da shranite pretvorbe. Po shranjevanju boste našli svoj vir podatkov pod **Podatki** > **Viri podatkov**.

1. Na strani **Viri podatkov** boste opazili, da ima nov vir podatkov stanje **Osveževanje**.

## <a name="available-power-query-data-sources"></a>Razpoložljivi viri podatkov Power Query

Glejte [sklicevanje na povezovalnik Power Query](/power-query/connectors/) za posodobljen seznam povezovalnikov, ki jih lahko izberete za uvoz podatkov v Customer Insights. 

Povezovalniki s kljukico v stolpcu **Customer Insights (podatkovni toki)** so na voljo za ustvarjanje novih virov podatkov, ki temeljijo na Power Query. Preglejte dokumentacijo določenega povezovalnika, če želite izvedeti več o njegovih predpogojih, omejitvah in drugih podrobnostih.

## <a name="edit-power-query-data-sources"></a>Urejanje virov podatkov Power Query

> [!NOTE]
> Morda ne bo mogoče spreminjati virov podatkov, ki se trenutno uporabljajo v enem od procesov aplikacije (na primer *segmentacija*, *ujemanje* ali *spajanje*). 
>
> Na strani **Nastavitve** lahko spremljate potek posameznih dejavnih procesov. Ko se proces zaključi, se lahko vrnete na stran **Viri podatkov** in opravite spremembe.

1. Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.

2. Izberite navpične tri pike poleg tistega vira podatkov, ki ga želite spremeniti, nato pa v spustnem meniju izberite **Uredi**.

   > [!div class="mx-imgBorder"]
   > ![Možnost urejanja](media/edit-option-data-sources.png "Možnost urejanja")

3. Uporabite svoje spremembe in pretvorbe v pogovornem oknu **Power Query - Urejanje poizvedb**, kot je opisano v razdelku [Ustvari nov vir podatkov](#create-a-new-data-source).

4. Izberite **Shrani** v Power Query po zaključitvi sprememb, da shranite spremembe.


[!INCLUDE[footer-include](../includes/footer-banner.md)]