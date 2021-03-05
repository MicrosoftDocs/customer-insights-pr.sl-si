---
title: Izvozite podatke Customer Insights v Upravitelja oglasov za Facebook
description: Preberite, kako konfigurirati povezavo z Upraviteljem oglasov za Facebook.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269994"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Povezovalnik za Upravitelja oglasov za Facebook (predogled)

Izvozite segmente poenotenih profilov strank v Upravitelja oglasov za Facebook za ustvarjanje oglaševalskih akcij v storitvama Facebook in Instagram.

## <a name="prerequisites"></a>Zahteve

- Imeti morate [**račun za oglaševanje v storitvi Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), ki vključuje [**poslovni račun Facebook**](https://business.facebook.com/).
- Biti morate skrbnik [**računa za oglaševanje v storitvi Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="connect-to-facebook-ads-manager"></a>Poveži z Upraviteljem oglasov za Facebook

1. Izberite **Skrbnik** > **Cilji za izvoz**.

1. V razdelku **Upravitelj oglasov za Facebook** izberite **Nastavi**.

1. Dajte svojemu cilju izvoza prepoznavno ime v polju **Prikazno ime**.

1. Izberite **Nadaljujte z računom Facebook**, da se prijavite v račun za oglaševanje v storitvi Facebook.

1. Omogočite dovoljenje **ads_management** po preverjanju pristnosti s storitvijo Facebook.

1. Izberite **račun za oglaševanje v storitvi Facebook**, s katerim želite delati.

1. Izberite **Obstoječe občinstvo po meri** s spustnega seznama ali ustvarite **Novo občinstvo po meri**. Za več informacij glejte [**Občinstvo v Upravitelju oglasov za Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.

1. Izberite **Naslednji** za nastavitev izvoza.

## <a name="configure-the-connector"></a>Konfiguracija povezovalnika

1. V polju **Izberi polje identifikatorja ključa** izberite **E-poštni naslov**, **Ime in naslov** ali **Telefon** , da pošljete podatke Upravitelju oglasov za Facebook.

1. Preslikajte pripadajoče atribute iz poenotene entitete stranke za izbrani identifikator ključa.
   > [TIP] Če izberete **E-poštni naslov** kot identifikator ključa, imate največ možnosti za ujemanje. Dodajanje dodatnih identifikatorjev lahko izboljša ujemanje.

1. Izberite **Dodaj atribut** za preslikavo dodatnih atributov, ki jih želite poslati Upravitelju oglasov za Facebook. Atributi Upravitelja oglasov za Facebook se preslikajo na naslednja uporabnikom prijazna imena: **FN** = **Ime**, **LN** = **Priimek**, **FI** = **Prva začetnica**, **TELEFON** = **Telefon**, **GEN** = **Spol**, **DOB** = **Datum rojstva**, **ST** = **Zvezna država**, **CT** = **Mesto**, **ZIP** = **Poštna številka**, **DRŽAVA** = **Država/regija**

1. Izberite segmente, ki jih želite izvoziti.

1. Izberite **Shrani**.

## <a name="export-the-data"></a>Izvoz podatkov

Lahko [izvozite podatke na zahtevo](export-destinations.md). Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).

## <a name="known-limitations"></a>Znane omejitve

- Do 10 milijonov profilov strank na posamezen izvoz v upravitelja oglasov za Facebook 
- Izvoz v upravitelja oglasov za Facebook je omejen na segmente
- Izvoz segmentov s skupno 10 milijonom profilov lahko traja do 90 minut

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Upravitelja oglasov za Facebook, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Upravitelj oglasov za Facebook izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.


[!INCLUDE[footer-include](../includes/footer-banner.md)]