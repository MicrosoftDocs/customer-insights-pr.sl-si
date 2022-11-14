---
title: Povežite an Azure Synapse vir podatkov (predogled)
description: Uporabite bazo podatkov v Azure Synapse kot vir podatkov v Dynamics 365 Customer Insights.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 675fd03c44a7a7a492b111895d79c2e77f93a5b5
ms.sourcegitcommit: 4ba74816ebfa46412c64c40a61e1f31c4ccc40f2
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/03/2022
ms.locfileid: "9738176"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Povežite an Azure Synapse Analytics vir podatkov (predogled)

Azure Synapse Analytics je podjetniška analitična storitev, ki pospeši čas do vpogledov v podatkovna skladišča in velike podatkovne sisteme. Azure Synapse Analytics združuje najboljše tehnologije SQL, ki se uporabljajo pri skladiščenju podatkov podjetja, tehnologije Spark, ki se uporabljajo za velike podatke, Data Explorer za analitiko dnevnikov in časovnih vrst, cevovode za integracijo podatkov in ETL/ELT ter globoko integracijo z drugimi storitvami Azure, kot je npr.Power BI ,Cosmos DB in AzureML.

Za več informacij glejte [Azure Synapse pregled](/azure/synapse-analytics/overview-what-is) .

## <a name="prerequisites"></a>Zahteve

> [!NOTE]
> Synapse Workspaces, ki imajo [požarni zid omogočen](/azure/synapse-analytics/security/synapse-workspace-ip-firewall) trenutno niso podprti.
> [!IMPORTANT]
> Prepričajte se, da ste nastavili vse **dodelitve vlog**, kot je opisano.  

**V Customer Insights** :

* Imate **Administrator** vlogo v Customer Insights. Izvedite več o [uporabniška dovoljenja v Customer Insights](permissions.md#add-users) .

**V Azuru** :

- Aktivna naročnina na Azure.

- Če uporabljate novo Azure Data Lake Storage Račun Gen2, *vodja storitve za Customer Insights* ki je potrebe "Dynamics 365 AI for Customer Insights".**Podatki bloba za shranjevanje sodelavec** dovoljenja. Izvedite več o [povezovanje z an Azure Data Lake Storage z glavnim serviserjem za Customer Insights](connect-service-principal.md) . Data Lake Storage Gen2 **mora imeti** omogočen [hierarhičen imenski prostor](/azure/storage/blobs/data-lake-storage-namespace).

- Na skupini virov the Azure Synapse delovni prostor se nahaja, v *glavni servis* ki je "Dynamics 365 AI for Customer Insights" in *uporabnik za Customer Insights* je treba dodeliti vsaj **Uporabnik z dovoljenjem za branje** dovoljenja. Če želite več informacij, glejte razdelek [Dodelitev vlog Azure s portalom Azure](/azure/role-based-access-control/role-assignments-portal).

- *Uporabnik* potrebuje dovoljenje **sodelujočega v shrambi zbirke dvojiških podatkov** za račun Azure Data Lake Storage Gen2, kjer se nahajajo podatki, ki so povezani z delovnim prostorom Azure Synapse. Preberite več o [uporabi portala Azure za dodelitev vloge Azure za dostop do zbirke dvojiških podatkov in podatkov o čakalni vrsti](/azure/storage/common/storage-auth-aad-rbac-portal) ter [sodelujočem v shrambi zbirke dvojiških podatkov](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Upravljana identiteta za delovni prostor Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* potrebuje dovoljenje **sodelujočega v shrambi zbirke dvojiških podatkov** za račun Azure Data Lake Storage Gen2, kjer se nahajajo podatki, ki so povezani z delovnim prostorom Azure Synapse. Preberite več o [uporabi portala Azure za dodelitev vloge Azure za dostop do zbirke dvojiških podatkov in podatkov o čakalni vrsti](/azure/storage/common/storage-auth-aad-rbac-portal) ter [sodelujočem v shrambi zbirke dvojiških podatkov](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Na Azure Synapse delovni prostor, *vodja storitve za Customer Insights* ki je potrebe "Dynamics 365 AI for Customer Insights".**Skrbnik Synapse** dodeljena vloga. The **uporabnik** potrebuje vsaj a **Sinapsa sodelavec** vloga, dodeljena delovnemu prostoru. Če želite več informacij, glejte razdelek [Kako nastaviti nadzor dostopa za delovni prostor Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

- Če vaše okolje Customer Insights shranjuje podatke v vašem [lasten Azure Data Lake Storage](own-data-lake-storage.md) , uporabnik, ki vzpostavi povezavo z Azure Synapse Analytics potrebuje vsaj vgrajeno **Uporabnik z dovoljenjem za branje** vlogo v računu Data Lake Storage. Če želite več informacij, glejte razdelek [Dodelitev vlog Azure s portalom Azure](/azure/role-based-access-control/role-assignments-portal).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Povežite se z bazo podatkov podatkovnega jezera v Azure Synapse Analytics

1. Pojdite na **Podatki** > **Viri podatkov**.

1. Izberite **Dodaj vir podatkov**.

1. Izberite **Azure Synapse Analytics (predogled)** metoda.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Pogovorno okno za povezavo s podatki Synapse Analytics":::
  
1. Vnesite a **Ime** za vir podatkov in neobvezno **Opis** .

1. Izberite [razpoložljiva povezava](connections.md) do Azure Synapse Analytics oz [ustvarite novo](export-azure-synapse-analytics.md#set-up-connection-to-azure-synapse) .

1. Izberite a **Baza podatkov** iz delovnega prostora, povezanega v izbranem Azure Synapse Analytics povezavo in izberite **Naslednji** . Trenutno podpiramo samo vrsto baze podatkov *Jezerska baza podatkov* .

1. Izberite entitete za vnos iz povezane baze podatkov in izberite **Naslednji**.

1. Po želji izberite podatkovne entitete, na katerih želite omogočiti profiliranje podatkov.

1. Izberite **Shrani** da uveljavite svojo izbiro in začnete zajemanje podatkov iz vašega na novo ustvarjenega vir podatkov, povezanega s tabelami zbirke podatkov Lake v Azure Synapse Analytics. The **Viri podatkov** odpre se stran, ki prikazuje novo vir podatkov v **Osvežujoče** stanje.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Nalaganje podatkov lahko traja nekaj časa. Po uspešni osvežitvi lahko vnesene podatke pregledate iz [**Entitete**](entities.md) strani.

[!INCLUDE [footer-include](includes/footer-banner.md)]
