---
title: Vzpostavljanje povezave s tabelami v storitvi Microsoft Dataverse
description: Uvozite podatke iz upravljanega jezera podatkov Microsoft Dataverse.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: ffeccffd0e353cb5490b537552d585c184ad672f9c806e673bd04743214ad068
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033100"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Povezovanje s podatki v upravljanem jezeru podatkov Microsoft Dataverse

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Ta članek vsebuje informacije o tem, kako hitro se uporabniki storitve Dataverse lahko povežejo s svojimi analitičnimi entitetami v jezeru, ki ga upravlja Dataverse. Biti morate skrbnik organizacije Dataverse, da lahko nadaljujete in si ogleda seznam entitet, ki so na voljo v upravljanem jezeru.

## <a name="important-considerations"></a>Pomembni premisleki

Lokacija za shranjevanje podatkov, shranjenih v spletnih storitvah, kot je Azure Data Lake Storage, se lahko razlikuje od lokacije za obdelovanje ali shranjevanje v storitvi Dynamics 365 Customer Insights. Z uvažanjem podatkov ali povezovanjem s podatki, shranjenimi v spletnih storitvah, se strinjate, da se podatki lahko prenesejo in shranijo v storitvi Dynamics 365 Customer Insights. [Več o tem preberite v Microsoftovem središču zaupanja.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>Povezava z upravljanim jezerom Dataverse

1. Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.

2. Izberite **Dodaj vir podatkov**.

3. Izberite **Poveži z upravljanim jezerom Microsoft Dataverse** in izberite **Naprej**.

4. Vnesite **ime** za vir podatkov in izberite **Naprej**. Smernice za poimenovanje: 
   - Začnite s črko.
   - Uporabljajte samo črke in številke. Posebni znaki in presledki niso dovoljeni.
   - Uporabite od 3 do 64 znakov.

5. Navedite **Naslov strežnika** za organizacijo Dataverse in izberite **Vpis**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Zaslon v koraku uvoza podatkov, v katerega lahko uporabnik vnese URL okolja Dataverse.":::

6. S seznama, ki je na voljo, izberite tabele, ki jih želite uvoziti kot entitete v vpoglede občinstva.    

   > [!NOTE]
   > Če so nekatere tabele že izbrane, jih morda uporabljajo druge aplikacije Dynamics 365 (na primer Dynamics 365 Sales Insights ali Customer Service Insights). Tega izbora ni mogoče spremeniti. Te tabele bodo na voljo kot entitete, ko bo ustvarjen vir podatkov.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Pogovorno okno s seznamom entitet v okolju Dataverse.":::

7. Shranite svoj izbor, da začnete sinhronizacijo izbranih tabel iz Dataverse. Novo dodano povezavo najdete na strani **Viri podatkov**. Dodane bodo v čakalno vrsto za osvežitev, število entitet pa bo prikazano kot 0, dokler se ne sinhronizirajo vse izbrane tabele.

Samo en vir podatkov okolja lahko istočasno uporablja isto upravljano jezero Dataverse.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Urejanje vira podatkov upravljanega jezera Dataverse

Izbor entitet uredite šele po ustvarjanju vira podatkov. Če bi bili na primer dodane dodatne entitete v Dataverse in želite uvoziti tudi njih.    
Če se želite povezati z drugim podatkovnim jezerom Dataverse, [ustvarite nov vir podatkov](#connect-to-a-dataverse-managed-lake).

1. Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.

2. Izberite tri pike poleg vira podatkov, ki ga želite posodobiti.

3. Na seznamu izberite možnost **Uredi**.

4. Izberite dodatne entitete z razpoložljivega seznama entitet in izberite **Shrani**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]