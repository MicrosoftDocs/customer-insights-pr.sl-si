---
title: Izvozite podatke Customer Insights v Upravitelja oglasov za Facebook
description: Naučite se, kako konfigurirati povezavo in izvažati v Upravitelja oglasov za Facebook.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ca32906a98bc734639fb369d6f5a92e8888fd850
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906830"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Izvoz seznamov segmentov v Upravitelja oglasov za Facebook (predogledna različica)

Izvozite segmente poenotenih profilov strank v Upravitelja oglasov za Facebook za ustvarjanje oglaševalskih akcij v storitvama Facebook in Instagram.

## <a name="prerequisites-for-connection"></a>Predpogoji za povezavo

- Potrebujete [**račun za oglase Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), ki vključuje [**poslovni račun Facebook**](https://business.facebook.com/).
- Biti morate skrbnik [**računa za oglaševanje v storitvi Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Znane omejitve

- Do 10 milijonov profilov strank na posamezen izvoz v Upravitelja oglasov za Facebook.
- Izvoz v Upravitelja oglasov za Facebook je omejen na segmente.
- Ustvarite ali posodobite samo občinstva po meri v storitvi Facebook vrste *seznam strank*.
- Izvoz segmentov s skupno 10 milijoni profilov lahko traja do 90 minut.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Nastavitev povezave z Upraviteljem oglasov za Facebook

Preden lahko uporabniki ustvarijo izvoz, mora skrbnik konfigurirati povezavo s storitvijo in dovoliti udeležencem, da uporabljajo povezavo.

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajanje povezave** in izberite **Upravitelj oglasov za Facebook** za konfiguracijo povezave.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, je privzeto **Skrbniki**. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Preverjanje pristnosti z oglasi za Facebook: 

   1. Izberite **Nadaljujte z računom Facebook**, da se prijavite v račun za oglaševanje v storitvi Facebook.

   1. Omogočite dovoljenje **ads_management** po preverjanju pristnosti s storitvijo Facebook.

   1. Izberite **račun za oglaševanje v storitvi Facebook**, s katerim želite delati.

   1. Izberite **Obstoječe občinstvo po meri** s spustnega seznama ali ustvarite **Novo občinstvo po meri**. Za več informacij glejte [**Občinstvo v Upravitelju oglasov za Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > S tem izvozom lahko ustvarite ali posodobite samo občinstva po meri v storitvi Facebook vrste *seznam strank*. V nekaterih primerih v spustnem seznamu vidite občinstva po meri drugih vrst. Če izberete drugo vrsto kot *seznam strank*, izvoz ne bo uspel. 

1. Preglejte **Zasebnost podatkov in skladnost** in izberite **Strinjam se**.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Za ustvarjanje novega izvoza izberite **Dodaj cilj**. 

1. V možnosti **Povezava za izvoz** izberite povezavo v razdelku **Upravitelj oglasov za Facebook**. Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.

1. V polju **Izberi polje identifikatorja ključa** izberite **E-poštni naslov**, **Ime in naslov** ali **Telefon** , da pošljete podatke Upravitelju oglasov za Facebook. 

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.

1. Preslikajte pripadajoče atribute iz poenotene entitete stranke za izbrani identifikator ključa.
   > [TIP] Če izberete **E-poštni naslov** kot identifikator ključa, imate največ možnosti za ujemanje. Dodajanje dodatnih identifikatorjev lahko izboljša ujemanje.

1. Izberite **Dodajanje atributa** za preslikavo več atributov za pošiljanje v Upravitelja oglasov za Facebook. Atributi Upravitelja oglasov za Facebook se preslikajo na naslednja uporabnikom prijazna imena: **FN** = **Ime**, **LN** = **Priimek**, **FI** = **Prva začetnica**, **TELEFON** = **Telefon**, **GEN** = **Spol**, **DOB** = **Datum rojstva**, **ST** = **Zvezna država**, **CT** = **Mesto**, **ZIP** = **Poštna številka**, **DRŽAVA** = **Država/regija**

1. Izberite segmente, ki jih želite izvoziti.

1. Izberite **Shrani**.

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab). Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Upravitelja oglasov za Facebook, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Upravitelj oglasov za Facebook izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
