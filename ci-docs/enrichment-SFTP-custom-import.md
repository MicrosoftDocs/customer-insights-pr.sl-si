---
title: Obogatite profile strank z uvozom po meri SFTP (predogled)
description: Splošne informacije o obogatitvi uvoza po meri SFTP.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 81ef6c62240e26cb5c9475e6306e08edc7e5eb31
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195816"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>Obogatite profile strank z uvozom po meri SFTP (predogled)

Uvoz po meri s protokolom za varen prenos datotek (SFTP) vam omogoča uvoz podatkov, ki jim ni treba iti skozi postopek poenotenja podatkov. To je prilagodljiv, varen in enostaven način za vnos podatkov. Uvoz po meri SFTP se lahko uporablja v kombinaciji z [izvozom SFTP](export-sftp.md), ki vam omogoča izvoz podatkov o profilih strank, ki so potrebni za obogatitev. Podatke je nato mogoče obdelati in obogatiti, uvoz po meri SFTP pa je mogoče uporabiti za prenos obogatenih podatkov nazaj v Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Zahteve

- Ime datoteke in lokacija (pot) datoteke za uvoz na gostitelju SFTP sta znana.

- A *model.json* Na voljo je datoteka, ki določa shemo skupnega podatkovnega modela za podatke, ki jih želite uvoziti. Ta datoteka mora biti v istem imeniku kot datoteka za uvoz.

- SFTP [povezava](connections.md) je [konfiguriran](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Primer sheme datoteke

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>Konfiguriranje povezave za uvoz uvoz po meri SFTP

Morate biti [skrbnik](permissions.md#admin) v Customer Insights in imejte uporabniške poverilnice, URL in številko vrat za lokacijo SFTP, od koder želite uvoziti podatke.

1. Izberite **Dodajte povezavo** ko konfigurirate obogatitev ali pojdite na **skrbnik** > **Povezave** in izberite **Nastaviti** na ploščici Uvoz po meri.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Stran za konfiguracijo uvozne povezave po meri.":::

1. Vnesite ime za povezavo.

1. Vnesite veljavno uporabniško ime, geslo in URL gostitelja za strežnik SFTP, v katerem se nahajajo podatki, ki jih želite uvoziti.

1. Preglejte in podajte soglasje, tako da v razdelku [Zasebnost in skladnost podatkov](#data-privacy-and-compliance) izberete možnost **Strinjam se**.

1. Izberite **Preveri** za potrditev konfiguracije in nato izberite **Shrani**.

### <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov z uporabo uvoza po meri dovolite prenos podatkov izven meje skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vaših navodilih, vendar ste vi odgovorni za zagotovitev, da podatki izpolnjujejo morebitne obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadarkoli odstrani, s čimer je uporaba te funkcije prekinjena.

## <a name="configure-the-import"></a>Konfiguriranje uvoza

1. Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.

1. Izberite **Obogati moje podatke** na **Uvoz po meri SFTP** ploščica.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Ploščica za uvoz po meri SFTP.":::

1. Preglejte pregled in nato izberite **Naslednji**.

1. Izberite povezavo. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Izberite **Stranka nabor podatkov** in izberite profil ali segment, ki ga želite obogatiti. The *Stranka* entiteta obogati vse vaše profile strank, medtem ko segment obogati samo profile strank v tem segmentu.

1. Izberite **Naprej**.

1. Vnesite **Pot** in **Ime datoteke** podatkovne datoteke, ki jo želite uvoziti.

1. Izberite **Naprej**.

1. Zagotovite a **Ime** za obogatitev in **Ime izhodne entitete**.

1. Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.

1. Izberite **Teči** za začetek procesa obogatitve ali zapiranje za vrnitev v **Obogatitve** strani.

## <a name="view-enrichment-results"></a>Oglejte si rezultate obogatitve

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Naslednji koraki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
