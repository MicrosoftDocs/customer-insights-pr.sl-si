---
title: Izvoz podatkov iz storitve Customer Insights v storitev Azure Synapse Analytics
description: Naučite se konfigurirati povezavo z Azure Synapse Analytics.
ms.date: 04/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 8ace9fbee4fbd8822629a39d5902e176f8511cb5
ms.sourcegitcommit: 9f6733b2f2c273748c1e7b77f871e9b4e5a8666e
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/11/2022
ms.locfileid: "8560407"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Izvozi podatke v Azure Synapse Analytics (predogled)

Azure Synapse je analitična storitev, ki pospeši čas za vpogled v podatkovna skladišča in sisteme masovnih podatkov. Podatke iz rešitve Customer Insights lahko uvozite in uporabite v storitvi [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Zahteve

Za konfiguriranje povezave iz rešitve Customer Insights v storitev Azure Synapse morajo biti izpolnjene naslednje zahteve.

> [!NOTE]
> Prepričajte se, da ste nastavili vse **dodelitve vlog**, kot je opisano.  

## <a name="prerequisites-in-customer-insights"></a>Zahteve v rešitvi Customer Insights

* Vaš Azure Active Directory (AD) uporabniški račun ima **skrbnik** vlogo v Customer Insights. Preberite več o [nastavitvi uporabniških dovoljenj v vpogledih v občinstvo](permissions.md#assign-roles-and-permissions)

V storitvi Azure: 

- Aktivna naročnina na Azure.

- Če uporabljate novo Azure Data Lake Storage Račun Gen2, *vodja storitve za Customer Insights* potrebe **Podatki blobov za shranjevanje sodelavec** dovoljenja. Preberite več o [povezovanju z računom za Azure Data Lake Storage Gen2 z glavnim imenom storitve Azure za vpoglede v občinstvo](connect-service-principal.md). Data Lake Storage Gen2 **mora imeti** omogočen [hierarhičen imenski prostor](/azure/storage/blobs/data-lake-storage-namespace).

- V skupini virov, kjer je Azure Synapse delovni prostor se nahaja, *ravnatelja storitve* in *Azure AD uporabnik s skrbniškimi dovoljenji v Customer Insights* je treba vsaj dodeliti **Uporabnik z dovoljenjem za branje** dovoljenja. Če želite več informacij, glejte razdelek [Dodelitev vlog Azure s portalom Azure](/azure/role-based-access-control/role-assignments-portal).

- The *Azure AD uporabnik s skrbniškimi dovoljenji v Customer Insights* potrebe **Podatki blobov za shranjevanje sodelavec** dovoljenja za Azure Data Lake Storage Račun Gen2, kjer se podatki nahajajo in so povezani z Azure Synapse delovni prostor. Preberite več o [uporabi portala Azure za dodelitev vloge Azure za dostop do zbirke dvojiških podatkov in podatkov o čakalni vrsti](/azure/storage/common/storage-auth-aad-rbac-portal) ter [sodelujočem v shrambi zbirke dvojiških podatkov](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Upravljana identiteta za delovni prostor Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* potrebuje dovoljenje **sodelujočega v shrambi zbirke dvojiških podatkov** za račun Azure Data Lake Storage Gen2, kjer se nahajajo podatki, ki so povezani z delovnim prostorom Azure Synapse. Preberite več o [uporabi portala Azure za dodelitev vloge Azure za dostop do zbirke dvojiških podatkov in podatkov o čakalni vrsti](/azure/storage/common/storage-auth-aad-rbac-portal) ter [sodelujočem v shrambi zbirke dvojiških podatkov](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Na Azure Synapse delovni prostor, *vodja storitve za Customer Insights* potrebe **Skrbnik Synapse** dodeljena vloga. Če želite več informacij, glejte razdelek [Kako nastaviti nadzor dostopa za delovni prostor Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Nastavitev povezave in izvoz v storitev Azure Synapse

### <a name="configure-a-connection"></a>Konfiguriranje povezave

Za ustvarjanje povezave potrebujeta principal storitve in uporabniški račun v Customer Insights **Uporabnik z dovoljenjem za branje** dovoljenja za *skupina virov* kjer se nahaja delovni prostor Synapse Analytics. Poleg tega potrebujeta principal storitve in uporabnik v delovnem prostoru Synapse Analytics **Skrbnik Synapse** dovoljenja. 

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **Azure Synapse Analytics** ali izberite **Nastaviti** na **Azure Synapse Analytics** ploščico za konfiguracijo povezave.

1. Svoji povezavi dodelite prepoznavno ime v polju Prikazno ime. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Izberite ali poiščite naročnino, v kateri želite uporabiti podatke Customer Insights. Takoj ko je naročnina izbrana, lahko izberete tudi **Delovni prostor**, **Račun za shranjevanje** in **Vsebnik**.

1. Izberite možnost **Shrani**, da shranite povezavo.

### <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Če želite konfigurirati izvoz s povezavo v skupni rabi, potrebujete vsaj **sodelavec** dovoljenja v Customer Insights. Če želite več informacij, glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite možnost **Dodaj izvoz** za ustvarjanje novega izvoza.

1. V **Povezava za izvoz** polje, izberite povezavo med **Azure Synapse Analytics** oddelek. Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna [povezava](connections.md).

1. Zagotovite prepoznavno **prikazno ime** za vaš izvoz in **ime baze podatkov**.

1. Izberite, v katere entitete želite izvoziti Azure Synapse Analytics.
   > [!NOTE]
   > Viri podatkov na podlagi [mape Common Data Model](connect-common-data-model.md) niso podprti.

2. Izberite **Shrani**.

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab). Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).

Za poizvedbo po podatkih, ki so bili izvoženi v Synapse Analytics, potrebujete **Podatki blobov za shranjevanje Uporabnik z dovoljenjem za branje** dostop do ciljne shrambe na delovnem prostoru izvozov. 

### <a name="update-an-export"></a>Posodobitev izvoza

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite možnost **Uredi** za izvoz, ki ga želite posodobiti.

   - **Dodajte** ali **odstranite** entitete iz izbora. Če iz izbora odstranite entitete, se te ne izbrišejo iz baze podatkov Synapse Analytics. Vendar prihodnje osvežitve podatkov ne bodo posodobile odstranjenih entitet v tej bazi podatkov.

   - **Spreminjanje imena baze podatkov** ustvari novo bazo podatkov Synapse Analytics. Baza podatkov z imenom, ki je bilo konfigurirano prej, v prihodnjih osvežitvah ne bo prejemala nobenih posodobitev.
