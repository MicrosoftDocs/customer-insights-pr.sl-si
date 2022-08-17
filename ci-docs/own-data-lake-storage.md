---
title: Uporabite svojega Azure Data Lake Storage Gen2 račun
author: mukeshpo
description: Spoznajte zahteve za uporabo svojega Azure Data Lake Storage račun za shranjevanje podatkov Customer Insights.
ms.author: mukeshpo
ms.date: 06/08/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: d2ff49c324c5c5c28213f362ff330d441fcb6052
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246221"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Uporabite svojega Azure Data Lake Storage Gen2 račun

Dynamics 365 Customer Insights vam omogoča shranjevanje vseh vaših podatkov [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction).

S shranjevanjem podatkov v Data Lake Storage se strinjate, da bodo podatki preneseni in shranjeni na ustrezni geografski lokaciji za ta račun za shranjevanje Azure. Za več informacij glejte [Microsoftovo središče zaupanja](https://www.microsoft.com/trust-center).

Skrbniki v Customer Insights lahko [ustvarite okolja](create-environment.md) in [določite možnost shranjevanja podatkov](create-environment.md#step-2-configure-data-storage) v postopku.

## <a name="prerequisites-to-use-your-storage-account"></a>Predpogoji za uporabo vašega računa za shranjevanje

- Azure Data Lake Storage računi morajo biti v isti regiji Azure, ki ste jo izbrali pri ustvarjanju okolja Customer Insights. Območje okolja Customer Insights lahko preverite pod **skrbnik** > **Sistem** > **O tem**.
- Data Lake Storage mora biti Gen2 in imeti [hierarhičen imenski prostor omogočen](/azure/storage/blobs/create-data-lake-storage-account). Gen1 računi za shranjevanje niso podprti.
- Vsebnik z imenom`customerinsights` mora obstajati na računu za shranjevanje. Ustvariti ga morate, preden začnete uporabljati lastno Data Lake Storage v Customer Insights. Skrbnik, ki nastavlja okolje Customer Insights, potrebuje vlogo Storage Blob Data sodelavec ali Storage Blob Data Owner v računu za shranjevanje ali`customerinsights` posoda. Za več informacij o dodeljevanju dovoljenj v računu za shranjevanje glejte [Ustvarite račun za shranjevanje](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Povežite Customer Insights s svojim računom za shranjevanje

Ko ustvarite novo okolje, se prepričajte, da račun Data Lake Storage obstaja in da so izpolnjeni vsi predpogoji.

1. V **Shranjevanje podatkov** korak med ustvarjanjem okolja, set **Shranite izhodne podatke** do **Azure Data Lake Storage Gen2**.
1. Izberite, kako **Povežite svojo shrambo**. Za preverjanje pristnosti lahko izbirate med možnostjo, ki temelji na virih, in možnostjo, ki temelji na naročnini. Za več informacij glejte [Povežite se z Azure Data Lake Storage računa z uporabo principala storitve Azure](connect-service-principal.md).
   - Za **Naročnina na Azure**, izberite **Naročnina**, **virov**, in **Račun za shranjevanje** ki vsebuje`customerinsights` posoda.
   - Za **Ključ računa**, zagotoviti **Ime računa** in **Ključ računa** za račun Data Lake Storage. Uporaba te metode preverjanja pristnosti pomeni, da ste obveščeni, če vaša organizacija rotira ključe. Moraš [posodobite konfiguracijo okolja](manage-environments.md#edit-an-existing-environment) z novim ključem, ko se obrne.
1. Izberite, ali želite uporabiti zasebno povezavo Azure za povezavo z računom za shranjevanje in [ustvarite povezavo z zasebno povezavo](security-overview.md#set-up-an-azure-private-link) z dvostopenjskim postopkom.

Ko so sistemski procesi, kot je vnos podatkov, končani, sistem ustvari ustrezne mape v računu za shranjevanje. Ustvarijo se podatkovne datoteke in datoteke *model.json*, ki so na podlagi imena procesa dodane v mape.

Če ustvarite več okolij Customer Insights in se odločite shraniti izhodne entitete iz teh okolij v svoj račun za shrambo, storitev Customer Insights ustvari ločene mape za vsako okolje z lastnostjo `ci_environmentID` v vsebniku.
