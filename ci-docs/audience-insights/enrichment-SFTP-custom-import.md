---
title: Obogatitev z uvozom po meri SFTP
description: Splošne informacije o obogatitvi uvoza po meri SFTP.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: e4b9a65eb50f75e0243fabfc10b501cf7acf4490
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229658"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Obogatite profile strank s podatki po meri (predogled)

Uvoz po meri s protokolom za varen prenos datotek (SFTP) vam omogoča uvoz podatkov, ki jim ni treba iti skozi postopek poenotenja podatkov. To je prilagodljiv, varen in enostaven način za vnos podatkov. Uvoz po meri SFTP se lahko uporablja v kombinaciji z [izvozom SFTP](export-sftp.md), ki vam omogoča izvoz podatkov o profilih strank, ki so potrebni za obogatitev. Podatke je nato mogoče obdelati in obogatiti, s pomočjo uvoza po meri SFTP pa obogatene podatke vrniti nazaj k možnosti vpogledov občinstva Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Zahteve

Za konfiguracijo uvoza po meri SFTP morajo biti izpolnjeni naslednji predpogoji:

- Ime in mesto (pot) datoteke, ki jo je treba uvoziti, se nahajata v gostitelju SFTP .
- Obstaja datoteka z obliko zapisa *model.json*, ki določa [shemo za podatkovni model Common Data Model](/common-data-model/) za uvoz podatkov. Ta datoteka mora biti v istem imeniku kot datoteka za uvoz.
- Skrbnik je že konfiguriral povezavo SFTP *oziroma* imate vi [skrbniška](permissions.md#administrator) dovoljenja. Potrebujete uporabniške poverilnice, URL in številko vrat za lokacijo SFTP, iz katere želite uvoziti podatke.


## <a name="configure-the-import"></a>Konfiguriranje uvoza

1. Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.

1. Na **ploščici za uvoz po meri SFTP** izberite možnost **Obogatitev podatkov** in nato izberite možnost **Začetek**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Ploščica za uvoz po meri SFTP.":::

1. Na spustnem seznamu izberite možnost [povezava](connections.md). Če ni na voljo nobena povezava, se obrnite na skrbnika. Če ste skrbnik, lahko povezavo vzpostavite tako, da na spustnem seznamu izberete možnost **Dodaj povezavo**, nato pa **Uvoz po meri SFTP**.

1. Izberite možnost **Poveži z uvozom po meri** za potrditev izbrane povezave.

1.  Izberite **Naprej** in vnesite **Pot** ter **Ime podatkovne datoteke**, ki jo želite uvoziti.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Posnetek zaslona vnosa lokacije podatkov.":::

1. Izberite možnost **Naprej** in izberite nabor podatkov o strankah. To so lahko vsi profili strank ali segment.

1. Izberite možnost **Naprej** ter navedite ime obogatitve in izhodne entitete. 

1. Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Konfiguriranje povezave za uvoz uvoz po meri SFTP 

Za konfiguriranje povezav morate biti skrbnik. Pri konfiguriranju obogatitve izberite možnost **Dodaj povezavo** *ali* odprite razdelek **Skrbnik** > **Povezave** in na ploščici Uvoz po meri izberite možnost **Nastavitev**.

1. Vnesite ime povezave v polje za **prikazno ime**.

1. Vnesite veljavno uporabniško ime, geslo in URL gostitelja za strežnik SFTP, v katerem se nahajajo podatki, ki jih želite uvoziti.

1. Preberite in podajte soglasje za **Zasebnost podatkov in skladnost** tako, da potrdite polje **Strinjam se**.

1. Izberite možnost **Potrdi** za potrditev konfiguracije.

1. Ko zaključite s preverjanjem, lahko povezavo shranite tako, da izberete možnost **Shrani**.

   > [!div class="mx-imgBorder"]
   > ![Stran za konfiguracijo povezave Experian.](media/enrichment-SFTP-connection.png "Experian – stran za konfiguracijo povezave")


## <a name="defining-field-mappings"></a>Opredelitev preslikav polja 

Imenik, ki vsebuje datoteko za uvoz v strežnik SFTP, mora vsebovati tudi datoteko *model.json*. Ta datoteka definira shemo za uvoz podatkov. Da bi določili preslikavo polja, mora biti za shemo uporabljen [Common Data Model](/common-data-model/). Preprost primer datoteke model.json je videti takole:

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a>Rezultati obogatitve

Če želite začeti postopek obogatitve, izberite **Zaženi** v ukazni vrstici. Sistem lahko obogatitev samodejno zažene tudi kot del [načrtovane osvežitve](system.md#schedule-tab). Čas obdelave bo odvisen od velikosti podatkov, ki jih želite uvoziti, in povezave s strežnikom SFTP.

Po končanem postopku obogatitve lahko svoje novo uvožene podatke obogatitve po meri pregledate v razdelku **Moje obogatitve**. Poleg tega boste našli čas zadnje posodobitve in število obogatenih profilov.

Do podrobnega prikaza vsakega obogatenega profila lahko dostopate tako, da izberete **Ogled obogatenih podatkov**.

## <a name="next-steps"></a>Naslednji koraki

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
