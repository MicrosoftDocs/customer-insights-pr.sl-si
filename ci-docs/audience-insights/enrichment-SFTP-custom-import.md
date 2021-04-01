---
title: Obogatitev z uvozom po meri SFTP
description: Splošne informacije o obogatitvi uvoza po meri SFTP.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d9e095ef793cbd25415864f76a541dce68fafe47
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595875"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Obogatite profile strank s podatki po meri (predogled)

Uvoz po meri s protokolom za varen prenos datotek (SFTP) vam omogoča uvoz podatkov, ki jim ni treba iti skozi postopek poenotenja podatkov. To je prilagodljiv, varen in enostaven način za vnos podatkov. Uvoz po meri SFTP se lahko uporablja v kombinaciji z [izvozom SFTP](export-sftp.md), ki vam omogoča izvoz podatkov o profilih strank, ki so potrebni za obogatitev. Podatke lahko nato obdelamo in obogatimo ter uporabimo uvoz po meri SFTP, da obogatene podatke vrnemo nazaj k zmogljivosti vpogledov v občinstvo Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Zahteve

Za konfiguracijo uvoza po meri SFTP morajo biti izpolnjeni naslednji predpogoji:

- Imate uporabniške poverilnice (uporabniško ime in geslo) za lokacijo SFTP, od koder bodo uvoženi podatki.
- Imate URL in številko vrat (običajno 22) za gostitelja STFP.
- Pri gostitelju SFTP imate ime in lokacijo datoteke, ki jo želite uvoziti.
- Tam je datoteka *model.json*, ki določa shemo za podatke, ki jih želite uvoziti. Ta datoteka mora biti v istem imeniku kot datoteka za uvoz.
- Imate [skrbniško](permissions.md#administrator) dovoljenje.

## <a name="configuration"></a>Konfiguracija

1. Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.

1. V **ploščici za uvoz po meri SFTP** izberite **Obogatitev podatkov**.

   > [!div class="mx-imgBorder"]
   > ![Ploščica za uvoz po meri SFTP](media/SFTP_Custom_Import_tile.png "Ploščica za uvoz po meri SFTP")

1. Izberite **Začetek** in vnesite poverilnice in naslov strežnika SFTP. Na primer sftp://mysftpserver.com:22.

1. Vnesite ime datoteke, ki vsebuje podatke in pot do datoteke v strežniku SFTP, če ni v korenski mapi.

1. Potrdite vse vnose z izbiro možnosti **Povezovanje z uvozom po meri**.

   > [!div class="mx-imgBorder"]
   > ![Pojavni meni za konfiguracijo uvoza po meri SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Pojavni meni za konfiguracijo uvoza po meri SFTP")

## <a name="defining-field-mappings"></a>Opredelitev preslikav polja 

Imenik, ki vsebuje datoteko za uvoz v strežnik SFTP, mora vsebovati tudi datoteko *model.json*. Ta datoteka definira shemo za uvoz podatkov. Shema mora uporabiti [Common Data Model](/common-data-model/) za določanje preslikave polja. Preprost primer datoteke model.json je videti takole:

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

Nadgradite svoje obogatene podatke o strankah. Ustvarite [segmente](segments.md), [mere](measures.md) in [izvozite podatke](export-destinations.md), da svojim strankam zagotovite prilagojene izkušnje.




[!INCLUDE[footer-include](../includes/footer-banner.md)]