---
title: Obogatitev z uvozom po meri SFTP
description: Splošne informacije o obogatitvi uvoza po meri SFTP.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896301"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Obogatite profile strank s podatki po meri (predogled)

Uvoz po meri s protokolom za varen prenos datotek (SFTP) omogoča uvoz podatkov, za katere ni potreben postopek poenotenja podatkov. To je prilagodljiv, varen in enostaven način za vnos podatkov. Uvoz po meri SFTP se lahko uporablja v kombinaciji z [izvozom SFTP](export-sftp.md), ki vam omogoča izvoz podatkov o profilih strank, ki so potrebni za obogatitev. Podatke lahko nato obdelamo in obogatimo ter uporabimo uvoz po meri SFTP, da obogatene podatke vrnemo nazaj k zmogljivosti vpogledov v občinstvo Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Zahteve

Za konfiguracijo uvoza po meri SFTP morajo biti izpolnjeni naslednji predpogoji:

- Imate ime in lokacijo (pot) datoteke, ki jo želite uvoziti v gostitelja SFTP.
- Obstaja datoteka z obliko zapisa *model.json*, ki določa [shemo za podatkovni model Common Data Model](/common-data-model/) za uvoz podatkov. Ta datoteka mora biti v istem imeniku kot datoteka za uvoz.
- Skrbnik je že konfiguriral povezavo SFTP *oziroma* imate vi [skrbniška](permissions.md#administrator) dovoljenja. Potrebujete uporabniške poverilnice, URL in številko vrat za lokacijo SFTP, iz katere želite uvoziti podatke.


## <a name="configure-the-import"></a>Konfiguriranje uvoza

1. Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.

1. Na **ploščici za uvoz po meri SFTP** izberite možnost **Obogatitev podatkov** in nato izberite možnost **Začetek**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Ploščica za uvoz po meri SFTP.":::

1. Na spustnem seznamu izberite [povezavo](connections.md). Če ni na voljo nobena povezava, se obrnite na skrbnika. Če ste skrbnik, lahko vzpostavite povezavo tako, da izberete možnost **Dodaj povezavo** in na spustnem meniju izberete možnost **Uvoz po meri SFTP**.

1. Izberite možnost **Poveži z uvozom po meri** za potrditev izbrane povezave.

1.  Izberite možnost **Naprej** in vnesite **Ime datoteke** in **Pot** podatkovne datoteke, ki jo želite uvoziti.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Posnetek zaslona vnosa lokacije podatkov.":::

1. Izberite možnost **Naprej** ter navedite ime obogatitve in izhodne entitete. 

1. Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Konfiguriranje povezave za uvoz uvoz po meri SFTP 

Za konfiguriranje povezav morate biti skrbnik. Pri konfiguriranju obogatitve izberite možnost **Dodaj povezavo** *ali* odprite razdelek **Skrbnik** > **Povezave** in na ploščici Uvoz po meri izberite možnost **Nastavitev**.

1. Vnesite ime povezave v polje za **prikazno ime**.

1. Vnesite veljavno uporabniško ime, geslo in URL gostitelja strežnika STFP, na katerem so podatki, ki jih želite uvoziti.

1. Preberite in podajte soglasje za **Zasebnost podatkov in skladnost** tako, da potrdite polje **Strinjam se**.

1. Izberite možnost **Potrdi** za potrditev konfiguracije.

1. Ko je preverjanje končano, lahko povezavo shranite s klikom možnosti **Shrani**.

> [!div class="mx-imgBorder"]
   > ![Stran za konfiguriranje povezave z Experian](media/enrichment-SFTP-connection.png "Stran za konfiguriranje povezave z Experian")


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
