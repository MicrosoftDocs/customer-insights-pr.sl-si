---
title: Povežite an Azure Synapse vir podatkov (predogled)
description: Uporabite bazo podatkov v Azure Synapse kot vir podatkov v Dynamics 365 Customer Insights.
ms.date: 03/25/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c4ae65613a02df38a30f907dae72d413bf1a702f
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052719"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Povežite an Azure Synapse Analytics vir podatkov (predogled)

Azure Synapse Analytics je analitična storitev podjetja, ki pospeši čas do vpogledov v podatkovna skladišča in sisteme velikih podatkov. Azure Synapse Analytics združuje najboljše tehnologije SQL, ki se uporabljajo pri skladiščenju podatkov v podjetju, tehnologije Spark, ki se uporabljajo za velike podatke, Data Explorer za analitiko dnevnikov in časovnih vrst, cevovode za integracijo podatkov in ETL/ELT ter globoko integracijo z drugimi storitvami Azure, kot je npr.Power BI,Cosmos DB in AzureML.

Za več informacij glejte [Azure Synapse pregled](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Zahteve

> [!IMPORTANT]
> Prepričajte se, da ste nastavili vse **dodelitve vlog**, kot je opisano.  

**V storitvi Customer Insights**:

* Imate **skrbnik** vlogo v Customer Insights. Več o tem [uporabniška dovoljenja v Customer Insights](permissions.md#assign-roles-and-permissions).

**V Azure**:

- Aktivna naročnina na Azure.

- Če uporabljate novo Azure Data Lake Storage Račun Gen2, *vodja storitve za vpogled v stranke* potrebe **Podatki blobov za shranjevanje sodelavec** dovoljenja. Več o tem [povezovanje z an Azure Data Lake Storage z ravnateljem storitve za vpogled v stranke](connect-service-principal.md). Data Lake Storage Gen2 **mora imeti** omogočen [hierarhičen imenski prostor](/azure/storage/blobs/data-lake-storage-namespace).

- V skupini virov Azure Synapse delovni prostor se nahaja, *ravnatelja storitve* in *uporabnik za Customer Insights* je treba vsaj dodeliti **Uporabnik z dovoljenjem za branje** dovoljenja. Če želite več informacij, glejte razdelek [Dodelitev vlog Azure s portalom Azure](/azure/role-based-access-control/role-assignments-portal).

- *Uporabnik* potrebuje dovoljenje **sodelujočega v shrambi zbirke dvojiških podatkov** za račun Azure Data Lake Storage Gen2, kjer se nahajajo podatki, ki so povezani z delovnim prostorom Azure Synapse. Preberite več o [uporabi portala Azure za dodelitev vloge Azure za dostop do zbirke dvojiških podatkov in podatkov o čakalni vrsti](/azure/storage/common/storage-auth-aad-rbac-portal) ter [sodelujočem v shrambi zbirke dvojiških podatkov](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Upravljana identiteta za delovni prostor Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* potrebuje dovoljenje **sodelujočega v shrambi zbirke dvojiških podatkov** za račun Azure Data Lake Storage Gen2, kjer se nahajajo podatki, ki so povezani z delovnim prostorom Azure Synapse. Preberite več o [uporabi portala Azure za dodelitev vloge Azure za dostop do zbirke dvojiških podatkov in podatkov o čakalni vrsti](/azure/storage/common/storage-auth-aad-rbac-portal) ter [sodelujočem v shrambi zbirke dvojiških podatkov](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Na Azure Synapse delovni prostor, *vodja storitve za vpogled v stranke* potrebe **Synapse Administrator** dodeljena vloga. Če želite več informacij, glejte razdelek [Kako nastaviti nadzor dostopa za delovni prostor Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Povežite se z bazo podatkov podatkovnega jezera v Azure Synapse Analytics

1. Pojdite na **Podatki** > **Viri podatkov**.

1. Izberite **Dodaj vir podatkov**.

1. Izberite **Azure Synapse Analytics (predogled)** metoda.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Pogovorno okno za povezavo s podatki Synapse Analytics":::
  
1. Vnesite a **ime** za vir podatkov in izbirno **Opis**.

1. Izberite [razpoložljiva povezava](connections.md) do Azure Synapse Analytics ali ustvarite novega.

1. Izberite a **Zbirka podatkov** iz delovnega prostora, povezanega v izbranem Azure Synapse Analytics povezavo in izberite **Naslednji**. Trenutno podpiramo samo vrsto baze podatkov *Baza podatkov jezera*.

1. Izberite entitete, ki jih želite vnesti iz povezane baze podatkov, in izberite **Naslednji**.

1. Po želji izberite podatkovne entitete, za katere želite omogočiti profiliranje podatkov.

1. Izberite **Shrani** da uporabite vaš izbor in začnete vnos podatkov iz vaše novo ustvarjene vir podatkov, povezanih s tabelami baze podatkov Lake v Azure Synapse Analytics. The **Viri podatkov** odpre se stran z novim vir podatkov v **Osvežujoče** stanje.
