---
title: Uporaba lastne shrambe ključev Azure (predogledna različica)
description: Naučite se konfigurirati Customer Insights za uporabo lastnega trezorja ključev Azure za upravljanje skrivnosti.
ms.date: 08/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 229fb5698a02d1d73c30442f61c7b1b5fce918bf
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246175"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Uporaba lastne shrambe ključev Azure (predogledna različica)

Povezovanje namenskega [Shramba ključev Azure](/azure/key-vault/general/basic-concepts) v okolje Customer Insights pomaga organizacijam pri izpolnjevanju zahtev glede skladnosti.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Povežite trezor ključev z okoljem Customer Insights

Nastavite namenski trezor ključev za uprizarjanje in uporabo skrivnosti v meji skladnosti organizacije.

### <a name="prerequisites"></a>Zahteve

- Aktivna naročnina na Azure.

- An [Administrator](permissions.md#admin) vlogo [dodeljena](permissions.md#add-users) v Customer Insights.

- [sodelavec](/azure/role-based-access-control/built-in-roles#contributor) in [Administrator uporabniškega dostopa](/azure/role-based-access-control/built-in-roles#user-access-administrator) vloge v trezorju ključev ali skupini virov, ki ji pripada trezor ključev. Za več informacij obiščite [Dodajanje ali odstranitev dodelitve vlog Azure s portalom Azure](/azure/role-based-access-control/role-assignments-portal). Če nimate vloge skrbnika uporabniškega dostopa v trezorju ključev, nastavite dovoljenja za nadzor dostopa na podlagi vloge za glavnega servisa Azure za Dynamics 365 Customer Insights ločeno. Upoštevajte postopke, da [uporabite glavno ime storitve Azure](connect-service-principal.md) za shrambo ključev, ki jo je treba povezati.

- Shramba ključev mora imeti požarni zid Key Vault **onemogočeno**.

- Trezor ključev je v istem [Azurna lokacija](https://azure.microsoft.com/global-infrastructure/geographies/#overview) kot okolje Customer Insights. V Customer Insights pojdite na **skrbnik** > **Sistem** in **O tem** zavihek za ogled regije okolja.

### <a name="recommendations"></a>Priporočila

- [Uporabite ločen ali namenski trezor ključev](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults) ki vsebuje samo skrivnosti, potrebne za Customer Insights.

- Upoštevajte [najboljše postopke za uporabo storitve Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) za možnosti nadzora dostopa, varnostnega kopiranja, spremljanja sprememb in obnovitve.

### <a name="link-a-key-vault-to-the-environment"></a>Povezava shrambe ključev z okoljem

1. Pojdi do **skrbnik** > **Varnost** in nato izberite **Shramba ključev** zavihek.
1. V ploščici **Key Vault** izberite **Nastavitev**.
1. Izberite **Naročnina**.
1. Izberite shrambo ključev v spustnem seznamu **Key Vault**. Če je na voljo preveč trezorjev ključev, izberite skupino virov, da omejite rezultate iskanja.
1. Preglejte [Zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **Strinjam se**.
1. Izberite **Shrani**.

The **Shramba ključev** ploščica prikazuje ime povezanega trezorja ključev, naročnino in skupino virov. Pripravljena je za uporabo v nastavitvah povezave.
Za podrobnosti o tem, katera dovoljenja za trezor ključev so dodeljena Customer Insights, pojdite na [Dovoljenja, odobrena za trezor ključev](#permissions-granted-on-the-key-vault).

## <a name="use-the-key-vault-in-the-connection-setup"></a>Uporaba shrambe ključev v nastavitvah povezave

Kdaj [vzpostavljanje povezav](connections.md) do [podprte tretje osebe](#supported-connection-types) sisteme, uporabite skrivnosti iz povezanega trezorja ključev za konfiguracijo povezav.

1. Odprite razdelek **Skrbnik** > **Povezave**.
1. Izberite **Dodaj povezavo**.
1. Za podprte vrste povezav je na voljo preklop **Uporabi storitev Key Vault**, če ste povezali shrambo ključev.
1. Namesto ročnega vnosa skrivnosti izberite ime skrivnosti, ki kaže na vrednost skrivnosti v trezorju ključev.

   :::image type="content" source="media/use-key-vault-secret.png" alt-text="Podokno za povezavo s povezavo SFTP, ki uporablja skrivnost storitve Key Vault.":::

1. Izberite **Shrani** da ustvarite povezavo.

## <a name="supported-connection-types"></a>Podprte vrste povezav

Podprte so naslednje povezave za [izvoz](export-destinations.md):

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>Dovoljenja, odobrena za trezor ključev

Naslednja dovoljenja so dodeljena aplikaciji Customer Insights v povezanem trezorju ključev [Politika dostopa do trezorja ključev](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) oz [Nadzor dostopa Azure na podlagi vlog](/azure/key-vault/general/rbac-guide?tabs=azure-cli) je omogočeno.

### <a name="key-vault-access-policy"></a>Pravilnik o dostopu za storitev Key Vault

| Vnesi        | Dovoljenja          |
| ----------- | -------------------- |
| Tipka         | [Pridobite ključe](/rest/api/keyvault/keys/get-keys/get-keys), [Pridobite ključ](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Skrivnost      | [Pridobite skrivnosti](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Pridobite skrivnost](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Potrdilo | [Pridobite potrdila](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Pridobite potrdilo](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Prejšnje vrednosti so minimalne za navedbo in branje med izvajanjem.

### <a name="azure-role-based-access-control"></a>Nadzor dostopa Azure, ki temelji na vlogi

The [Key Vault Uporabnik z dovoljenjem za branje in uporabniške vloge Secret Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli) bo dodan za Customer Insights.

## <a name="frequently-asked-questions"></a>Pogosto zastavljena vprašanja

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Ali lahko Customer Insights zapiše skrivnosti ali prepiše skrivnosti v shrambo ključev?

Ne. Samo dovoljenja za branje in seznam, opisana v [podeljena dovoljenja](#permissions-granted-on-the-key-vault) so dodeljeni Customer Insights. Sistem ne more dodati, izbrisati ali prepisati skrivnosti v shrambo ključev. To je tudi razlog, zakaj ne morete vnesti poverilnic, ko povezava uporablja storitev Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Ali lahko spremenim povezavo iz skrivnosti Key Vault v privzeto preverjanje pristnosti?

Ne. Ko jo konfigurirate z uporabo skrivnosti iz povezane shrambe ključev, se ne morete vrniti na privzeto povezavo. Ustvarite ločeno povezavo in odstranite staro, če je ne potrebujete več.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Kako lahko prekličem dostop do trezorja ključev za Customer Insights?

Če je [Politika dostopa do trezorja ključev](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) oz [Nadzor dostopa Azure na podlagi vlog](/azure/key-vault/general/rbac-guide?tabs=azure-cli) je omogočeno, odstranite dovoljenja za glavnega servisa`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` z imenom `Dynamics 365 AI for Customer Insights`. Vse povezave, ki uporabljajo shrambo ključev, bodo prenehale delovati.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Skrivnost, ki se uporablja v povezavi, je bila odstranjena iz shrambe ključev. Kaj lahko storim?

Ko konfigurirana skrivnost iz trezorja ključev ni več dostopna, se v Customer Insights prikaže obvestilo. Omogočite [začasno brisanje](/azure/key-vault/general/soft-delete-overview) v shrambi ključev za obnovitev skrivnosti, če so bile odstranjene po pomoti.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Povezava ne deluje, vendar je moja skrivnost v shrambi ključev. Kaj je lahko vzrok?

Ko ne more dostopati do trezorja ključev, se v Customer Insights prikaže obvestilo. Vzrok je lahko:

- Dovoljenja za principala storitve Customer Insights so bila odstranjena. Obnoviti jih je treba ročno.

- Požarni zid v shrambi ključev je omogočen. Požarni zid mora biti onemogočen, da bo shramba ključev ponovno dostopna za Customer Insights.
