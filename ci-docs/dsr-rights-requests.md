---
title: Zahteve posameznikov, na katere se nanašajo podatki, (DSR) v skladu z uredbo GDPR | Microsoftovo gradivo
description: Odgovorite na zahteve posameznikov, na katere se nanašajo podatki, za zmogljivost vpogledov v občinstvo Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350289"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Zahteve posameznikov, na katere se nanašajo podatki, (DSR) v skladu z uredbo GDPR

Splošna uredba Evropske unije o varstvu podatkov (GDPR) velja od 25. maja 2018. Posameznikom daje pomembne pravice glede njihovih podatkov. Pri GDPR gre za zaščito in omogočanje pravic posameznikov do zasebnosti. Več informacij o Microsoftovi zavezanosti do varnosti in skladnosti lahko preberete v [Microsoftovem središču zaupanja](https://www.microsoft.com/trust-center).

Prizadevamo si, da svojim strankam pomagamo izpolniti zahteve uredbe GDPR. Vključuje pravico do brisanja in izvoza podatkov, kar vključuje osebne podatke, kot so ID-ji uporabnikov, telefonske številke in e-poštni naslovi. Skrbniki lahko izvajajo zahteve uporabnikov za brisanje ali izvoz osebnih podatkov.

## <a name="audience-insights"></a>Vpogledi v občinstvo

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Odgovorite na zahteve posameznikov, na katere se nanašajo podatki, za izbris za zmogljivost vpogledov v občinstvo Dynamics 365 Customer Insights, v skladu z uredbo GDPR.

»Pravica do izbrisa« z odstranitvijo osebnih podatkov iz podatkov o strankah, ki jih ima organizacija, je ključna zaščita v Splošni uredbi o varstvu podatkov (GDPR). Odstranitev osebnih podatkov vključuje odstranitev vseh osebnih podatkov in sistemsko ustvarjenih dnevnikov, razen informacij iz dnevnika spremljanja sprememb.

#### <a name="manage-data-subject-delete-requests"></a>Upravljanje zahtev posameznika, na katerega se nanašajo podatki, za izbris

Vpogledi v občinstvo nudijo naslednje izkušnje v izdelkih, s katerimi lahko izbrišete osebne podatke za določeno stranko ali uporabnika:

- **Upravljanje zahtev za izbris podatkov o strankah**: podatki o strankah v storitvi Customer Insights se uvozijo iz izvirnih virov podatkov zunaj storitve Customer Insights. Vse zahteve za izbris v skladu z uredbo GDPR morajo biti izvedene v izvirnem viru podatkov.
- **Upravljanje zahtev za izbris uporabniških podatkov storitve Customer Insights**: podatke za uporabnike je ustvaril Customer Insights. Vse zahteve za izbris v skladu z uredbo GDPR morajo biti izvedene v storitvi Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Upravljanje zahtev za izbris podatkov o strankah

Skrbnik storitve Customer Insights lahko upošteva te korake, da odstrani podatke stranke, ki so bili izbrisani iz vira podatkov:

1. Vpis v storitev Dynamics 365 Customer Insights.
2. Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.
3. Za vsak vir podatkov na seznamu, ki vsebuje izbrisane podatke strank:
   1. Izberite možnost (...) in nato **Osveži**.
   2. Preverite stanje vira podatkov v razdelku **Stanje**. Kljukica pomeni, da je bila osvežitev uspešna. Opozorilni trikotnik pomeni, da je prišlo do napake. Če se prikaže opozorilni trikotnik, pošljite sporočilo na naslov D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Obravnava zahtev za izbris podatkov o strankah v skladu z uredbo GDPR.](audience-insights/media/gdpr-data-sources.png "Obravnava zahtev za izbris podatkov o strankah v skladu z uredbo GDPR")

##### <a name="manage-delete-requests-for-user-data"></a>Upravljanje zahtev za izbris uporabniških podatkov

Skrbnik storitve Customer Insights lahko za izbris uporabniških podatkov storitve Customer Insights upošteva te korake:

1. Vpis v storitev Dynamics 365 Customer Insights.
2. Pri vpogledih v občinstvo izberite **Skrbnik** > **Dovoljenja**.
3. Potrdite polje za uporabnika, ki ga želite izbrisati.
4. Izberite **Odstrani**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Odziv na zahteve posameznikov, na katere se nanašajo podatki, za izvoz v skladu z uredbo GDPR

Kot del naše zaveze za sodelovanje z vami na vaši poti do uvedbe Splošne uredbe o varstvu podatkov (GDPR) smo ustvarili dokumentacijo, ki vam bo pomagala pri pripravi. Ta dokumentacija opisuje korake, ki jih lahko danes opravite za zagotavljanje skladnosti z uredbo GDPR pri uporabi vpogledov v občinstvo.

#### <a name="manage-export-and-view-requests"></a>Upravljajte izvoza in ogled zahtev

Zaradi pravice do prenosljivosti podatkov lahko posamezniki, na katere se nanašajo podatki, zahtevajo kopijo svojih osebnih podatkov v elektronski obliki (tj. »strukturirana, pogosto uporabljena, strojno berljiva in interoperabilna oblika«), ki se jo lahko pošlje drugemu upravljavcu podatkov.

##### <a name="export-customer-data-tenant-admin"></a>Izvoz podatkov o stranki (skrbnik najemnika)

Skrbnik najemnika lahko za izvoz podatkov upošteva ta navodila:

1. Pošljite e-poštno sporočilo na naslov D365CI@microsoft.com ter v zahtevi navedite e-poštni naslov stranke. Ekipa Customer Insights bo na registrirani e-poštni naslov skrbnika najemnika poslala e-poštno sporočilo s prošnjo za potrditev izvoza podatkov.
2. Potrdite potrditev izvoza podatkov za zahtevano stranko.
3. Prejmite izvožene podatke prek e-poštnega naslova skrbnika najemnika.

##### <a name="export-user-data-tenant-admin"></a>Izvoz uporabniških podatkov (skrbnik najemnika)

1. Pošljite e-poštno sporočilo na naslov D365CI@microsoft.com ter v zahtevi navedite e-poštni naslov uporabnika. Ekipa Customer Insights bo na registrirani e-poštni naslov skrbnika najemnika poslala e-poštno sporočilo s prošnjo za potrditev izvoza podatkov.
2. Potrdite potrditev izvoza podatkov za zahtevanega uporabnika.
3. Prejmite izvožene podatke prek e-poštnega naslova skrbnika najemnika.

## <a name="consent-management-preview"></a>Upravljanje privolitve (predogled)

Zmožnost upravljanja privolitve ne zbira uporabniških podatkov neposredno. Uvaža in obdeluje samo podatke o privolitvi, ki jih zagotovijo uporabniki v drugih aplikacijah.

Če želite odstraniti podatke o soglasju o določenih uporabnikih, jih odstranite v virih podatkov, ki jih prevzame zmožnost upravljanja privolitve. Po osvežitvi vir podatkov bodo odstranjeni podatki izbrisani tudi v središču za soglasje. Aplikacije, ki uporabljajo entiteto za soglasje, bodo izbrisale tudi podatke, ki so bili odstranjeni iz vira po a [osveži](audience-insights/system.md#refresh-processes). Priporočamo, da po odzivu na zahtevo posameznika, na katerega se osebni podatki nanašajo, hitro osvežite vire podatkov za odstranitev uporabnikovih podatkov iz vseh drugih procesov in aplikacij.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]