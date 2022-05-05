---
title: Izvozi podatke Customer Insights v Facebook Upravitelj oglasov (vsebuje video)
description: Naučite se, kako konfigurirati povezavo in izvažati v Upravitelja oglasov za Facebook.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f610ab1af83bfd512ec1861e7dc76ebb2eecfcbb
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643781"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Izvoz seznamov segmentov v Upravitelja oglasov za Facebook (predogledna različica)

Izvozite segmente poenotenih profilov strank v Upravitelja oglasov za Facebook za ustvarjanje oglaševalskih akcij v storitvama Facebook in Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites-for-connection"></a>Predpogoji za povezavo

- Potrebujete račun [**Facebook oglaševalski račun**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), ki vključuje poslovni račun za [**Facebook**](https://business.facebook.com/).
- Morate biti skrbnik oglaševalskega računa [**Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Znane omejitve

- Do 10 milijonov profilov strank na izvoz v upravitelju oglaševanja Facebook.
- Izvoz v Upravitelja oglasov za Facebook je omejen na segmente.
- Ustvarite ali posodobite samo občinstva po meri v storitvi Facebook vrste *seznam strank*.
- Izvoz segmentov s skupno 10 milijonov profilov strank lahko traja do 90 minut.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Nastavitev povezave z Upraviteljem oglasov za Facebook

Preden lahko uporabniki ustvarijo izvoz, mora skrbnik konfigurirati povezavo s storitvijo in dovoliti udeležencem, da uporabljajo povezavo.

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajanje povezave** in izberite **Upravitelj oglasov za Facebook** za konfiguracijo povezave.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Preverjanje pristnosti z oglasi za Facebook: 

   1. Izberite možnost **Nadaljujte s storitvijo Facebook** za prijavo v svoj oglaševalski račun Facebook.

   1. Omogočite dovoljenje **ads_management** po preverjanju pristnosti s storitvijo Facebook.

   1. Izberite **račun za oglaševanje v storitvi Facebook**, s katerim želite delati.

   1. Na spustnem seznamu izberite možnost **Trenutno občinstvo po meri** ali ustvarite **Novo občinstvo po meri**. Za več informacij glejte [**Občinstvo v Upravitelju oglasov za Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > S tem izvozom lahko ustvarite ali posodobite samo občinstva po meri v storitvi Facebook vrste *seznam strank*. V nekaterih primerih spustni seznam vsebuje občinstva po meri različnih vrst. Če izberete drugo vrsto kot *seznam strank*, izvoz ne bo uspel. 

1. Preglejte **Zasebnost podatkov in skladnost** in izberite **Strinjam se**.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Za ustvarjanje novega izvoza izberite **Dodaj cilj**. 

1. V možnosti **Povezava za izvoz** izberite povezavo v razdelku **Upravitelj oglasov za Facebook**. Če se vam poimenovanje tega odseka ne prikaže, to pomeni, da vam ni na voljo nobena tovrstna povezava.

1. V polju **Izberi polje identifikatorja ključa** izberite **E-poštni naslov**, **Ime in naslov** ali **Telefon** , da pošljete podatke Upravitelju oglasov za Facebook. 

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.

1. Preslikajte pripadajoče atribute iz poenotene entitete stranke za izbrani identifikator ključa.
   > [!TIP]
   > Največ možnosti za ujemanje boste dosegli, če za identifikator ključa izberete možnost **E-poštni naslov**. Dodajanje dodatnih identifikatorjev lahko izboljša ujemanje.

1. Izberite **Dodajanje atributa** za preslikavo več atributov za pošiljanje v Upravitelja oglasov za Facebook. Atributi upravitelja oglasov za Facebook se preslikajo v naslednja uporabnikom prijazna imena: **IM** = **Ime**, **PR** = **Priimek**, **ZI** = **Začetnica imena**, **TELEFON** = **Telefon**, **SP** = **Spol**, **DR** = **Datum rojstva**, **DRŽ** = **Država**, **MST** = **Mesto**, **PŠ** = **Poštna številka**, **DRŽAVA** = **Država/regija**

1. Izberite segmente, ki jih želite izvoziti.

1. Izberite **Shrani**.

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab). 

Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Upravitelja oglasov za Facebook, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Upravitelj oglasov za Facebook izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.


[!INCLUDE [footer-include](includes/footer-banner.md)]
