---
title: Obogatite profile strank s podatki iz Microsoft Office 365
description: Uporabite lastniške podatke iz Microsoft Office obogatiti svoje profile strank s podatki o angažiranosti.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 47239bd7f0c89742cf9c673bb2ebe4c41d853233
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376850"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Obogatite profile strank s podatki o angažiranosti (predogled)

Uporabite podatke iz Microsoft Office 365 obogatiti profile računa strank z vpogledi v dejavnosti prek Office 365 aplikacije. Podatki o udeležbi so sestavljeni iz e-pošte in dejavnosti sestankov, ki so združeni na ravni računa. Na primer število e-poštnih sporočil iz poslovnega računa ali število sestankov z računom. Podatki o posameznih uporabnikih niso na voljo. 

Ta obogatitev je na voljo v naslednjih regijah: Združeno kraljestvo, Evropa, Severna Amerika.

## <a name="prerequisites"></a>Zahteve

Za konfiguracijo obogatitve morajo biti izpolnjeni naslednji predpogoji:

- Imate aktivno Office 365 licenca v oblaku.
- Imaš [enotni profili strank](customer-profiles.md) temelji na [poslovne račune](work-with-business-accounts.md).
- Vaše okolje Customer Insights mora imeti a [Microsoft Dataverse organizacija priložena](create-environment.md#step-3-connect-to-microsoft-dataverse).
- Imaš [skrbnik](permissions.md#admin) dovoljenja.
- Imate ali lahko dobite soglasje od svojega Office 365 skrbnik najemnika za uporabo Office 365 podatke, ki jih je treba zagotoviti **Vpogled v organizacijo** znotraj aplikacij Dynamics 365.

## <a name="configure-the-enrichment"></a>Konfiguriranje obogatitve

1. Pri vpogledih v občinstvo izberite **Podatki** > **Obogatitev**.

1. Pojdite na **Odkrij** zavihek in izberite **Obogatite moje podatke** na **Dejavnost računa** ploščice.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Ploščica za sodelovanje v računu.":::
   
1. Izberite **Naslednji** v **Pregled** korak in vnesite e-poštne naslove vaše organizacije, za katero bodo zbrani podatki Officea. Za ustrezno komunikacijo se obdelujejo samo podatki z navedenih e-poštnih naslovov. Najboljša praksa je uporaba e-poštnih skupin, npr.*Ameriška prodajna ekipa*, ki jih je enostavno upravljati Office 365. Število e-poštnih naslovov v skupinah je razrešeno in prikazano. Skupno število e-poštnih naslovov mora biti vsaj 2 in ne sme presegati 2500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="E-poštni naslovi za sodelovanje v računu.":::

1. Preglejte izjavo o soglasju, izberite **strinjam se** potrdite polje in izberite **Naslednji**.

1. Izberite stranko nabor podatkov in izberite **Naslednji**.

1. Preslikajte polje e-poštnega naslova za stik in izberite **Naslednji**.

1. Preglejte konfiguracijo obogatitve, dajte obogatitvi ime in izberite **Shrani obogatitev** prihraniti obogatitev.

## <a name="office-365-tenant-administrator-consent"></a>Office 365 soglasje skrbnika najemnika

Privolitev od Office 365 Za aktiviranje obogatitve je potreben skrbnik najemnika. E-poštno sporočilo je poslano na Office 365 skrbnike najemnikov, ko je obogatitev shranjena, kar jih zahteva, da pregledajo in soglašajo z dovoljenjem aplikacijam Dynamics 365, da uporabljajo vaše podjetje Office 365 podatke, ki jih je treba zagotoviti **Vpogled v organizacijo**. The Office 365 skrbnik najemnika lahko privoli tudi neposredno v svojih Office 365 skrbniško konzolo, tako da izberete **Vpogled v organizacijo**.

## <a name="running-the-enrichment-for-the-first-time"></a>Izvajanje obogatitve prvič

Ko se obogatitev začne prvič, po Office 365 skrbnik najemnika je dal soglasje, prenos podatkov iz Office 365 se začne. Ta postopek traja nekaj časa. Prva obogatitvena vožnja bo predvidoma izvedena s šesturno zamudo. Število dni, ki jih zajemajo podatki, si lahko ogledate na strani s pregledom dejavnosti računa po končani obogatitvi. Če imate veliko količino podatkov, po nekaj dneh znova zaženite obogatitev. Zagotavlja, da so podatki popolni za celotno časovno okno, ki je eno leto.

Za začetek postopka izberite **teci** na strani za konfiguracijo dejavnosti računa. Poleg tega lahko dovolite sistemu, da samodejno zažene obogatitev kot del a [načrtovana osvežitev](system.md#schedule-tab). Privzeto se obogatitev izvaja enkrat na teden.

Odvisno od velikosti vaših Officeovih podatkov lahko traja nekaj ur, da se dokončanje obogatitve.

Ko zaženete obogatitev, bo Microsoft obdelal podatke v Office 365 meja skladnosti, da ustvarite združene vpoglede, ki se nato dodajo v vaše okolje Customer Insights. Noben podatek na posamezni ravni (na primer telo katerega koli e-poštnega sporočila ali koledarskega povabila) ne postane na voljo uporabnikom Customer Insights. 

[!INCLUDE [progress-details-pane](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Rezultati obogatitve

Ko zaženete postopek obogatitve, pojdite na **Moje obogatitve** za pregled rezultatov obogatitve. Našli boste skupno število obogatenih strank in pregled rezultatov obogatitve. Vključuje število obdelanih e-poštnih sporočil in sestankov, število dni, za katere so bili podatki združeni, in drugo.

Našli boste tudi grafikon s številom obogatenih strank skozi čas in predogled podatkov o obogatitvi.  

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


Preglejte obogatene podatke z izbiro **Poglej več** v razdelku za predogled. Odpre se *Pisarna* entiteta. Prav tako lahko najdete subjekt, ki je naveden v **Obogatitev** skupina v **Podatki** > **Entitete**. Našli boste tudi *Office_UserEntity*, ki vsebuje ID-je Active Directory za e-poštne naslove, ki so bili izbrani med konfiguracijo obogatitve 

## <a name="see-enrichment-data-on-the-customer-card"></a>Glejte podatke o obogatitvi na kartici stranke

Dejavnost računa si lahko ogledate tudi na karticah posameznih strank. Odprite možnost **Stranke** in izberite profil stranke. Na kartici stranke boste našli oceno angažiranosti računa, skupno število e-poštnih sporočil in skupno število sestankov, združenih v zadnjem letu. Najdete tudi grafikone, ki prikazujejo zgodovino e-pošte in sestankov.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kartica stranke z obogatenimi podatki.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Na podlagi obogatenih podatkov ustvarite segmente in meritve

Obogatene podatke lahko uporabite za ustvarjanje segmentov in meritev, kot je podrobno opisano spodaj. Na primer, segment, ki vsebuje vse stranke, ki imajo vrednost nad 60 for *dni od zadnjega e-pošte* in *dni od zadnjega srečanja*. Ta segment vsebuje zastarele račune, ki jih lahko poskusite znova aktivirati. 

## <a name="next-steps"></a>Naslednji koraki

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
