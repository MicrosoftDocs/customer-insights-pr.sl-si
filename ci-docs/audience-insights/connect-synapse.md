---
title: Prevzemi podatke iz Azure Synapse Analytics
description: Uporabite bazo podatkov v Azure Synapse kot vir podatkov v Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 163bef897880f0497bf00e90fd095621a2d14378
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/25/2022
ms.locfileid: "8356056"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Povežite an Azure Synapse vir podatkov (predogled)

Azure Synapse Analytics je analitična storitev podjetja, ki pospeši čas do vpogledov v podatkovna skladišča in sisteme velikih podatkov. Azure Synapse Analytics združuje najboljše tehnologije SQL, ki se uporabljajo pri skladiščenju podatkov v podjetju, tehnologije Spark, ki se uporabljajo za velike podatke, Data Explorer za analitiko dnevnikov in časovnih serij, cevovode za integracijo podatkov in ETL/ELT ter globoko integracijo z drugimi storitvami Azure, kot je npr.Power BI,Cosmos DB in AzureML.

Za več informacij glejte [Azure Synapse pregled](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Zahteve

Za konfiguriranje povezave iz rešitve Customer Insights v storitev Azure Synapse morajo biti izpolnjene naslednje zahteve.

> [!IMPORTANT]
> Prepričajte se, da ste nastavili vse **dodelitve vlog**, kot je opisano.  

## <a name="prerequisites-in-customer-insights"></a>Zahteve v rešitvi Customer Insights

* Imate **skrbnik** vlogo v storitvi Customer Insights. Preberite več o [uporabniških dovoljenjih v vpogledih v občinstvo](permissions.md#assign-roles-and-permissions).

V storitvi Azure: 

- Aktivna naročnina na Azure.

- Če uporabljate nov račun za Azure Data Lake Storage Gen2, *glavno ime storitve za vpoglede v občinstvo* potrebuje dovoljenja **sodelujočega za podatke shrambe zbirke dvojiških podatkov**. Več o tem [povezovanje z an Azure Data Lake Storage z ravnateljem storitve za občinstvo vpoglede](connect-service-principal.md). Data Lake Storage Gen2 **mora imeti** omogočen [hierarhičen imenski prostor](/azure/storage/blobs/data-lake-storage-namespace).

- V skupini virov se nahaja delovni prostor Azure Synapse, *glavno ime storitve* in *uporabnik za vpoglede v občinstvo* pa morajo imeti dodeljena vsaj dovoljenja za **branje**. Če želite več informacij, glejte razdelek [Dodelitev vlog Azure s portalom Azure](/azure/role-based-access-control/role-assignments-portal).

- *Uporabnik* potrebuje dovoljenje **sodelujočega v shrambi zbirke dvojiških podatkov** za račun Azure Data Lake Storage Gen2, kjer se nahajajo podatki, ki so povezani z delovnim prostorom Azure Synapse. Preberite več o [uporabi portala Azure za dodelitev vloge Azure za dostop do zbirke dvojiških podatkov in podatkov o čakalni vrsti](/azure/storage/common/storage-auth-aad-rbac-portal) ter [sodelujočem v shrambi zbirke dvojiških podatkov](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Upravljana identiteta za delovni prostor Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* potrebuje dovoljenje **sodelujočega v shrambi zbirke dvojiških podatkov** za račun Azure Data Lake Storage Gen2, kjer se nahajajo podatki, ki so povezani z delovnim prostorom Azure Synapse. Preberite več o [uporabi portala Azure za dodelitev vloge Azure za dostop do zbirke dvojiških podatkov in podatkov o čakalni vrsti](/azure/storage/common/storage-auth-aad-rbac-portal) ter [sodelujočem v shrambi zbirke dvojiških podatkov](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *Glavno ime storitve za vpoglede v občinstvo* potrebuje v delovnem prostoru Azure Synapse dodeljeno vlogo **skrbnika za Synapse**. Če želite več informacij, glejte razdelek [Kako nastaviti nadzor dostopa za delovni prostor Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Povežite se z bazami podatkov podatkovnega jezera v Azure Synapse Analytics

1. Pojdite na **Podatki** > **Viri podatkov**.

1. Izberite **Dodaj vir podatkov**.

1. Izberite **Azure Synapse Analytics (predogled)** metoda.

1. Vnesite **Ime** za vir podatkov in izberite **Naprej**, da ustvarite vir podatkov. 

1. Izberite [razpoložljiva povezava](connections.md) do Azure Synapse Analytics ali ustvarite novega.

1. Izberite a **Jezerska baza podatkov** iz delovnega prostora, povezanega v izbranem Azure Synapse Analytics povezavo in izberite **Naslednji**.

1. Izberite entitete, ki jih želite vnesti iz povezane baze podatkov. 

1. Po želji izberite podatkovne entitete, na katerih želite omogočiti profiliranje podatkov. 

1. Izberite **Shrani** da uporabite vaš izbor in začnete vnos podatkov iz vaše novo ustvarjene vir podatkov, povezanih s tabelami baze podatkov Lake v Azure Synapse Analytics.
