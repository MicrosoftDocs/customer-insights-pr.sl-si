---
title: Povezovanje z entitetami v upravljanem jezeru Common Data Service
description: Uvozite podatke iz upravljanega jezera podatkov Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596979"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Povezovanje s podatki v upravljanem jezeru podatkov Common Data Service

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Ta članek vsebuje informacije o tem, kako se lahko obstoječe stranke Dynamics 365 hitro povežejo s svojimi analitičnimi entitetami v Common Data Service upravljanem jezeru. Biti morate skrbnik organizacije Common Data Service, da lahko nadaljujete in si ogleda seznam entitet, ki so na voljo v upravljanem jezeru.

## <a name="important-considerations"></a>Pomembni premisleki

Lokacija za shranjevanje podatkov, shranjenih v spletnih storitvah, kot je Azure Data Lake Storage, se lahko razlikuje od lokacije za obdelovanje ali shranjevanje v storitvi Dynamics 365 Customer Insights. Z uvažanjem podatkov ali povezovanjem s podatki, shranjenimi v spletnih storitvah, se strinjate, da se podatki lahko prenesejo in shranijo v storitvi Dynamics 365 Customer Insights. [Več o tem preberite v Microsoftovem središču zaupanja.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Povezava z upravljanim jezerom Common Data Service

1. Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.

2. Izberite **Dodaj vir podatkov**.

3. Izberite **Vzpostavi povezavo z Common Data Service** in izberite **Naprej**.

4. Vnesite **ime** za vir podatkov in izberite **Naprej**. Smernice za poimenovanje: 
   - Začnite s črko.
   - Uporabljajte samo črke in številke. Posebni znaki in presledki niso dovoljeni.
   - Uporabite od 3 do 64 znakov.

5. Navedite **Naslov strežnika** za svojo organizacijo Common Data Service in izberite **Vpis**.

   > [!div class="mx-imgBorder"]
   > ![Pogovorno okno za vnos naslova strežnika za Common Data Service](media/enter-CDS-org-details.png)

6. Na seznamu razpoložljivih možnosti izberite entitete, ki jih želite vključiti.    

   > [!NOTE]
   > Če so nekatere entitete že izbrane, jih lahko uporabljajo druge aplikacije Dynamics 365 (kot so Dynamics 365 Sales Insights ali Customer Service Insights). Tega izbora ni mogoče spremeniti. Te entitete bodo na voljo, ko bo ustvarjen vir podatkov.

   > [!div class="mx-imgBorder"]
   > ![Pogovorno okno s seznamom entitet v organizaciji Common Data Service](media/select-analytical-entities.png)

7. Shranite izbor, da začnete sinhronizirati izbrane entitete v upravljano jezero Common Data Service. Novo dodano povezavo najdete na strani **Viri podatkov**. Dana bo v čakalno vrsto za osvežitev in število entitet bo prikazano kot 0, dokler niso vse entitete sinhronizirane.

Samo en vir podatkov okolja lahko istočasno uporablja isto upravljano jezero Common Data Service.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Urejanje vira podatkov upravljanega jezera Common Data Service

Izbor entitet uredite šele po ustvarjanju vira podatkov. Če bi bili na primer dodane dodatne entitete v Common Data Service in želite uvoziti tudi njih.    
Če se želite povezati v drugo Common Data Service, [ustvarite nov vir podatkov](#connect-to-a-common-data-service-managed-lake).

1. Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.

2. Izberite tri pike poleg vira podatkov, ki ga želite posodobiti.

3. Na seznamu izberite možnost **Uredi**.

4. Izberite dodatne entitete z razpoložljivega seznama entitet in izberite **Shrani**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]