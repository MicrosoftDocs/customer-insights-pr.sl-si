---
title: Obogatitev z uvozom po meri SFTP
description: Splošne informacije o obogatitvi uvoza po meri SFTP.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 657afb6fcb68429680eb677734b4115e69769008
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953739"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Obogatite profile strank s podatki po meri (predogled)

Uvoz po meri s protokolom za varen prenos datotek (SFTP) vam omogoča uvoz podatkov, ki jim ni treba iti skozi postopek poenotenja podatkov. To je prilagodljiv, varen in enostaven način za vnos podatkov. Uvoz po meri SFTP se lahko uporablja v kombinaciji z [izvozom SFTP](export-sftp.md), ki vam omogoča izvoz podatkov o profilih strank, ki so potrebni za obogatitev. Podatke je mogoče nato obdelati in obogatiti, uvoz po meri SFTP pa se lahko uporabi za vrnitev obogatenih podatkov v Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Zahteve

- Znano je ime datoteke in lokacija (pot) datoteke, ki jo je treba uvoziti na gostitelja SFTP.

- A *model.json* na voljo je datoteka, ki določa shemo skupnega podatkovnega modela za podatke, ki jih je treba uvoziti. Ta datoteka mora biti v istem imeniku kot datoteka za uvoz.

- SFTP [povezavo](connections.md) je [konfiguriran](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Primer datotečne sheme

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

Moraš biti [skrbnik](permissions.md#admin) v Customer Insights in imejte uporabniške poverilnice, URL in številko vrat za lokacijo SFTP, iz katere želite uvoziti podatke.

1. Izberite **Dodajte povezavo** ko konfigurirate obogatitev ali pojdite na **Admin** > **Povezave** in izberite **Nastaviti** na ploščici Uvoz po meri.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Stran za konfiguracijo povezave za uvoz po meri.":::

1. Vnesite ime za povezavo.

1. Vnesite veljavno uporabniško ime, geslo in URL gostitelja za strežnik SFTP, v katerem se nahajajo podatki, ki jih želite uvoziti.

1. Preglejte in podajte soglasje, tako da v razdelku [Zasebnost in skladnost podatkov](#data-privacy-and-compliance) izberete možnost **Strinjam se**.

1. Izberite **Preverite** da preverite konfiguracijo in nato izberite **Shrani**.

### <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov z uporabo uvoza po meri dovolite prenos podatkov izven meja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo takšne podatke prenesel po vašem navodilu, vendar ste odgovorni za zagotovitev, da podatki izpolnjujejo morebitne obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadarkoli odstrani, s čimer je uporaba te funkcije prekinjena.

## <a name="configure-the-import"></a>Konfiguriranje uvoza

1. Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.

1. Izberite **Obogatite moje podatke** na **Uvoz po meri SFTP** ploščice.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Ploščica za uvoz po meri SFTP.":::

1. Preglejte pregled in nato izberite **Naslednji**.

1. Izberite povezavo. Obrnite se na skrbnika, če ta ni na voljo.

1. Izberite **Stranka nabor podatkov** in izberite profil ali segment, ki ga želite obogatiti. The *Stranka* entiteta obogati vse vaše profile strank, medtem ko segment obogati samo profile strank, ki jih vsebuje ta segment.

1. Izberite **Naprej**.

1. Vnesite **Pot** in **Ime datoteke** podatkovne datoteke, ki jo želite uvoziti.

1. Izberite **Naprej**.

1. Zagotovite a **ime** za obogatitev in **Ime izhodne entitete**.

1. Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.

1. Izberite **teci** za začetek procesa obogatitve ali blizu vrnitve na **Obogatitve** stran.

## <a name="enrichment-results"></a>Rezultati obogatitve

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Naslednji koraki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
