---
title: Uporabite svoje Azure Data Lake Storage Račun 2. generacije
author: mukeshpo
description: Preberite več o zahtevah za uporabo lastnega Azure Data Lake Storage račun za shranjevanje podatkov Customer Insights.
ms.author: mukeshpo
ms.date: 05/30/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 9fcd7645e34bf310ac3a1b98a0dd9a60598b19dc
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833956"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Uporabite svoje Azure Data Lake Storage Račun 2. generacije

Dynamics 365 Customer Insights vam omogoča shranjevanje vseh vaših podatkov [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction)

S shranjevanjem podatkov v Data Lake Storage se strinjate, da bodo podatki preneseni in shranjeni na ustrezni geografski lokaciji za ta račun za shranjevanje Azure. Za več informacij glejte [Microsoftov center zaupanja](https://www.microsoft.com/trust-center).

Skrbniki v Customer Insights lahko [ustvarjati okolja](create-environment.md) in [določite možnost shranjevanja podatkov](create-environment.md#step-2-configure-data-storage) v postopku.

## <a name="prerequisites-to-use-your-storage-account"></a>Predpogoji za uporabo vašega računa za shranjevanje

- Azure Data Lake Storage računi morajo biti v isti regiji Azure, ki ste jo izbrali pri ustvarjanju okolja Customer Insights. Območje okolja Customer Insights lahko preverite pod **Admin** > **sistem** > **O**.
- Shramba podatkovnega jezera mora biti Gen2 in imeti [Imenski prostor hierarhičen je omogočen](/azure/storage/blobs/create-data-lake-storage-account). Računi za shranjevanje Gen1 niso podprti.
- Posoda z imenom`customerinsights` mora obstajati na računu za shranjevanje. Ustvariti ga morate, preden v storitvi Customer Insights uporabite lastno shrambo podatkovnega jezera. Skrbnik, ki nastavi okolje Customer Insights, potrebuje vlogo Storage Blob Data sodelavec ali Storage Blob Data Owner v računu za shranjevanje ali`customerinsights` posoda. Za več informacij o dodelitvi dovoljenj v računu za shranjevanje glejte [Ustvarite račun za shranjevanje](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Povežite Customer Insights s svojim računom za shranjevanje

Ko ustvarite novo okolje, se prepričajte, da račun Data Lake Storage obstaja in da so izpolnjeni vsi predpogoji.

1. V **Shranjevanje podatkov** korak med ustvarjanjem okolja, set **Shranite izhodne podatke** do **Azure Data Lake Storage Gen2**.
1. Izberite, kako **Povežite svoj prostor za shranjevanje**. Za preverjanje pristnosti lahko izbirate med možnostjo, ki temelji na virih, in možnostjo, ki temelji na naročnini. Za več informacij glejte [Povežite se z an Azure Data Lake Storage račun z uporabo principala storitve Azure](connect-service-principal.md).
   - Za **Naročnina na Azure**, izberite **Naročnina**, **virov**, in **Račun za shranjevanje** ki vsebuje`customerinsights` posoda.
   - Za **Ključ računa**, zagotovite **Ime računa** in **Ključ računa** za račun Data Lake Storage. Uporaba te metode preverjanja pristnosti pomeni, da ste obveščeni, če vaša organizacija vrti ključe. Moraš [posodobite konfiguracijo okolja](manage-environments.md#edit-an-existing-environment) z novim ključem, ko ga zavrtite.

Ko se sistemski procesi, kot je vnos podatkov, zaključijo, sistem ustvari ustrezne mape v računu za shranjevanje. Ustvarijo se podatkovne datoteke in datoteke *model.json*, ki so na podlagi imena procesa dodane v mape.

Če ustvarite več okolij Customer Insights in se odločite shraniti izhodne entitete iz teh okolij v svoj račun za shrambo, storitev Customer Insights ustvari ločene mape za vsako okolje z lastnostjo `ci_environmentID` v vsebniku.
