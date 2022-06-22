---
title: Obogatite profile strank s podatki iz Microsoft Office 365
description: Uporabite lastniške podatke iz Microsoft Office obogatiti svoje profile strank s podatki o angažiranosti.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 7192b7680e73a581dd603de174c57b20bec996dd
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954153"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Obogatite profile strank s podatki o angažiranosti (predogled)

Uporabite podatke iz Microsoft Office 365 obogatiti profile računa strank z vpogledi v dejavnosti prek Office 365 aplikacije. Podatki o udeležbi so sestavljeni iz e-pošte in dejavnosti sestankov, ki so združeni na ravni računa. Na primer število e-poštnih sporočil iz poslovnega računa ali število sestankov z računom. Podatki o posameznih uporabnikih niso na voljo.

## <a name="supported-countries-or-regions"></a>Podprte države ali regije

Trenutno podpiramo naslednje regije: Združeno kraljestvo, Evropa, Severna Amerika.

## <a name="prerequisites"></a>Zahteve

- Aktiven Office 365 licenca v oblaku.
- [Poenoteni profili strank](customer-profiles.md) temelji na [poslovne račune](work-with-business-accounts.md).
- A [Microsoft Dataverse organizacija priložena](create-environment.md#step-3-connect-to-microsoft-dataverse) v vašem okolju Customer Insights.
- [skrbnik](permissions.md#admin) dovoljenja.
- Soglasje vašega Office 365 skrbnik najemnika za uporabo Office 365 podatke, ki jih je treba zagotoviti **Vpogled v organizacijo** znotraj aplikacij Dynamics 365.

## <a name="configure-the-enrichment"></a>Konfiguriranje obogatitve

1. Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.

1. Izberite **Obogatite moje podatke** na **Dejavnost računa** ploščice.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Ploščica za sodelovanje v računu.":::

1. Preglejte pregled in nato izberite **Naslednji**.

1. Vnesite e-poštne naslove vaše organizacije, za katero bodo zbrani podatki Officea. Za ustrezno komunikacijo se obdelujejo samo podatki z navedenih e-poštnih naslovov. Najboljša praksa je uporaba e-poštnih skupin, npr.*Ameriška prodajna ekipa*, v katerem lahko upravljate Office 365. Število e-poštnih naslovov v skupinah je razrešeno in prikazano. Skupno število e-poštnih naslovov mora biti vsaj 2 in ne sme presegati 2500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="E-poštni naslovi za sodelovanje v računu.":::

1. Preglejte in podajte svoje soglasje za [Office 365 soglasje skrbnika najemnika](#office-365-tenant-administrator-consent) z izbiro **strinjam se**.

1. Izberite **Naprej**.

1. Izberite **Kontaktirajte nabor podatkov** in izberite profil, ki ga želite obogatiti. Izberite **Naprej**.

1. Preslikajte polje e-poštnega naslova za stik in izberite **Naslednji**.

1. Zagotovite a **ime** za obogatitev in **Izhodna entiteta**.

1. Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.

1. Izberite **Zapri** da se vrnem na **Obogatitve** stran.

### <a name="office-365-tenant-administrator-consent"></a>Office 365 soglasje skrbnika najemnika

Privolitev od Office 365 Za aktiviranje obogatitve je potreben skrbnik najemnika. E-poštno sporočilo je poslano na Office 365 skrbnike najemnikov, ko je obogatitev shranjena, kar jih zahteva, da pregledajo in soglašajo z dovoljenjem aplikacijam Dynamics 365, da uporabljajo vaše podjetje Office 365 podatke, ki jih je treba zagotoviti **Vpogled v organizacijo**. The Office 365 skrbnik najemnika lahko privoli tudi neposredno v svojih Office 365 skrbniško konzolo, tako da izberete **Vpogled v organizacijo**.

## <a name="running-the-enrichment-for-the-first-time"></a>Izvajanje obogatitve prvič

Ko se obogatitev začne prvič, po Office 365 skrbnik najemnika je dal soglasje, prenos podatkov iz Office 365 se začne. Ta postopek traja nekaj časa. Prva obogatitvena vožnja bo predvidoma izvedena s šesturno zamudo. Število dni, ki jih zajemajo podatki, si lahko ogledate na strani s pregledom dejavnosti računa po končani obogatitvi. Če imate veliko količino podatkov, po nekaj dneh znova zaženite obogatitev. Zagotavlja, da so podatki popolni za celotno časovno okno, ki je eno leto.

Odvisno od velikosti vaših Officeovih podatkov lahko traja nekaj ur, da se dokončanje obogatitve.

Ko zaženete obogatitev, bo Microsoft obdelal podatke v Office 365 meja skladnosti, da ustvarite združene vpoglede, ki se nato dodajo v vaše okolje Customer Insights. Noben podatek na posamezni ravni (na primer telo katerega koli e-poštnega sporočila ali koledarskega povabila) ne postane na voljo uporabnikom Customer Insights.

Izberite **teci** za začetek procesa obogatitve.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Rezultati obogatitve

[!INCLUDE [enrichment-results](includes/enrichment-results.md)] To je *Pisarna* entiteta. The *Office_UserEntity* vsebuje ID-je Active Directory za e-poštne naslove, ki so bili izbrani med konfiguracijo obogatitve.

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Predogled rezultatov po zagonu postopka obogatitve.":::

Vsi podatki so združeni do ravni računa. Sistem izračuna oceno angažiranosti, ki se giblje od 0 do 100, za vsak račun. Ocena angažiranosti zagotavlja sestavljeno merilo dejavnosti računa med e-poštnimi sporočili in sestanki glede na vaše druge račune. Naslednji seznam vsebuje združene podatke, ki jih zagotavlja obogatitev dejavnosti računa:

| Podatki                                                                              | Ime stolpca                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Ocena obveznosti                                                                  |  EngagementScore                         |
| Število e-poštnih sporočil na račun                                                       |  NoOfEmails_ToAccount                    |
| Število e-poštnih sporočil iz računa                                                     |  NoOfEmails_FromAccount                  |
| Število sestankov, ki jih je sprožil račun                                           |  NoOfMeetings_FromAccount                |
| Število sestankov, ki jih je začela vaša organizacija                                 |  NoOfMeetings_ToAccount                  |
| Število oseb iz vaše organizacije na sestankih z računom                  |  NoOfContactsInvolved_Meetings           |
| Število oseb iz vaše organizacije v e-poštnih pogovorih z računom       |  NoOfContactsInvolved_Emails             |
| Število oseb iz računa na sestankih z vašo organizacijo                  |  NoOfAccountContactsInvolved_Meetings    |
| Število oseb iz računa v e-poštnih pogovorih z vašo organizacijo       |  NoOfAccountContactsInvolved_Emails      |
| Datum začetka sodelovanja (prvo e-pošto ali sestanek v podatkih)                        |  Engagement StartDate                     |
| Dnevi od zadnjega e-poštnega sporočila                                                             |  DaysSinceLastEmail                      |
| Dnevi od zadnjega srečanja                                                           |  Dnevi od zadnjega srečanja                    |
| Povprečno trajanje sestankov                                                      |  Povprečno trajanje_sestankov             |
| Povprečno trajanje e-poštnih odgovorov iz računa                                    |  AverageDuration_Of_AccountEmailReplies  |
| Datum začetka združevanja                                                            |  Datum začetka združevanja                    |
| Raven združevanja (leto, mesec ali teden)                                          |  Raven združevanja                        |

## <a name="see-enrichment-data-on-the-customer-card"></a>Glejte podatke o obogatitvi na kartici stranke

Dejavnost računa si lahko ogledate tudi na karticah posameznih strank. Odprite možnost **Stranke** in izberite profil stranke. Na kartici stranke boste našli oceno angažiranosti računa, skupno število e-poštnih sporočil in skupno število sestankov, združenih v zadnjem letu. Najdete tudi grafikone, ki prikazujejo zgodovino e-pošte in sestankov.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kartica stranke z obogatenimi podatki.":::

## <a name="next-steps"></a>Naslednji koraki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
Na primer, segment, ki vsebuje vse stranke, ki imajo vrednost nad 60 for *dni od zadnjega e-pošte* in *dni od zadnjega srečanja*. Ta segment vsebuje zastarele račune, ki jih lahko poskusite znova aktivirati.

[!INCLUDE [footer-include](includes/footer-banner.md)]
