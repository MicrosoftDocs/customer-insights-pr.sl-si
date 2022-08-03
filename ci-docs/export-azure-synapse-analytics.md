---
title: Izvozi podatke v Azure Synapse Analytics (predogled)
description: Naučite se konfigurirati povezavo z Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f9c9ee55f2874ae1dcaf82f2ff17ed0fbbb7804d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196414"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Izvozi podatke v Azure Synapse Analytics (predogled)

Azure Synapse je analitična storitev, ki pospeši čas za vpogled v podatkovna skladišča in sisteme masovnih podatkov. Podatke iz rešitve Customer Insights lahko uvozite in uporabite v storitvi [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Zahteve

> [!NOTE]
> Prepričajte se, da ste nastavili vse **dodelitve vlog**, kot je opisano.

- V Customer Insights, vaš Azure Active Directory (AD) uporabniški račun mora imeti [Vloga skrbnika](permissions.md#assign-roles-and-permissions).

V storitvi Azure:

- Aktivna naročnina na Azure.

- Če uporabljate novo Azure Data Lake Storage Račun Gen2, [vodja storitve za Customer Insights](connect-service-principal.md) ima **Podatki bloba za shranjevanje sodelavec** dovoljenja. Data Lake Storage Gen2 **mora imeti** omogočen [hierarhičen imenski prostor](/azure/storage/blobs/data-lake-storage-namespace).

- V skupini virov, kjer je Azure Synapse delovni prostor se nahaja, v *glavni servis* in *Azure AD uporabnik s skrbniškimi dovoljenji v Customer Insights* je treba dodeliti vsaj **Uporabnik z dovoljenjem za branje**[dovoljenja](/azure/role-based-access-control/role-assignments-portal).

- The *Azure AD uporabnik s skrbniškimi dovoljenji v Customer Insights* ima **Podatki bloba za shranjevanje sodelavec** dovoljenja za Azure Data Lake Storage Račun Gen2, kjer se podatki nahajajo in so povezani z Azure Synapse delovni prostor. Preberite več o [uporabi portala Azure za dodelitev vloge Azure za dostop do zbirke dvojiških podatkov in podatkov o čakalni vrsti](/azure/storage/common/storage-auth-aad-rbac-portal) ter [sodelujočem v shrambi zbirke dvojiških podatkov](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- The *[Azure Synapse upravljana identiteta delovnega prostora](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* ima **Podatki bloba za shranjevanje sodelavec** dovoljenja za Azure Data Lake Storage Račun Gen2, kjer se podatki nahajajo in so povezani z Azure Synapse delovni prostor. Preberite več o [uporabi portala Azure za dodelitev vloge Azure za dostop do zbirke dvojiških podatkov in podatkov o čakalni vrsti](/azure/storage/common/storage-auth-aad-rbac-portal) ter [sodelujočem v shrambi zbirke dvojiških podatkov](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Na Azure Synapse delovni prostor, *vodja storitve za Customer Insights* ima **Skrbnik Synapse**[dodeljena vloga](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-connection-to-azure-synapse"></a>Nastavite povezavo z Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **Azure Synapse Analytics**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto jo lahko uporabljajo samo skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Izberite ali poiščite naročnino, v kateri želite uporabiti podatke Customer Insights. Takoj ko je naročnina izbrana, lahko izberete tudi **Delovni prostor**, **Račun za shranjevanje** in **Vsebnik**.

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)] Če želite konfigurirati izvoz s skupno povezavo, potrebujete vsaj **sodelavec** dovoljenja v Customer Insights.

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz**.

1. V **Povezava za izvoz** polju izberite povezavo med Azure Synapse Analytics razdelek. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Zagotovite prepoznavno **prikazno ime** za vaš izvoz in **ime baze podatkov**. Izvoz bo ustvaril nov [Azure Synapse baza podatkov o jezerih](/azure/synapse-analytics/database-designer/concepts-lake-database) v delovnem prostoru, določenem v povezavi.

1. Izberite, v katere entitete želite izvoziti Azure Synapse Analytics.
   > [!NOTE]
   > Viri podatkov na podlagi [mape Common Data Model](connect-common-data-model.md) niso podprti.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Za poizvedbo po podatkih, ki so bili izvoženi v Synapse Analytics, potrebujete **Podatki bloba za shranjevanje Uporabnik z dovoljenjem za branje** dostop do ciljnega pomnilnika v delovnem prostoru izvozov.

## <a name="update-an-export"></a>Posodobitev izvoza

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite možnost **Uredi** za izvoz, ki ga želite posodobiti.

   - **Dodajte** ali **odstranite** entitete iz izbora. Če iz izbora odstranite entitete, se te ne izbrišejo iz baze podatkov Synapse Analytics. Vendar prihodnje osvežitve podatkov ne bodo posodobile odstranjenih entitet v tej bazi podatkov.

   - **Spreminjanje imena baze podatkov** ustvari novo bazo podatkov Synapse Analytics. Baza podatkov z imenom, ki je bilo konfigurirano prej, v prihodnjih osvežitvah ne bo prejemala nobenih posodobitev.

[!INCLUDE [footer-include](includes/footer-banner.md)]
