---
title: Uporaba lastne shrambe ključev Azure za upravljanje skrivnosti
description: Preberite, kako konfigurirati storitev Customer Insights za uporabo lastne shrambe ključev Azure.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: d4f2d5ebc828053c40e22065f4915c4d0f84153f
ms.sourcegitcommit: 6ec4626a185892dfb781d3c7af4384f9c13f3723
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/17/2022
ms.locfileid: "8763599"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Uporaba lastne shrambe ključev Azure (predogledna različica)

Povezovanje namenskega [Azurni trezor ključev](/azure/key-vault/general/basic-concepts) v okolje Customer Insights pomaga organizacijam izpolnjevati zahteve skladnosti.
Dodeljena shramba ključev se lahko uporablja za pripravo in uporabo skrivnosti na meji zagotavljanja skladnosti organizacije. Customer Insights lahko uporabi skrivnosti v Azure Key Vault za [vzpostaviti povezave](connections.md) na sisteme tretjih oseb.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Povežite trezor ključev z okoljem Customer Insights

### <a name="prerequisites"></a>Zahteve

Če želite konfigurirati trezor ključev v Customer Insights, morajo biti izpolnjeni naslednji predpogoji:

- Imate aktivno naročnino na Azure.

- Imate [skrbnik](permissions.md#admin) vlogo v storitvi Customer Insights. Več o tem [uporabniška dovoljenja v Customer Insights](permissions.md#assign-roles-and-permissions).

- Imate vlogo [Sodelavec](/azure/role-based-access-control/built-in-roles#contributor) in [Skrbniški dostop uporabnika](/azure/role-based-access-control/built-in-roles#user-access-administrator) v shrambi ključev ali skupini virov, ki ji pripada shramba ključev. Za več informacij obiščite [Dodajanje ali odstranitev dodelitve vlog Azure s portalom Azure](/azure/role-based-access-control/role-assignments-portal). Če nimate vloge Skrbniški dostop uporabnika v shrambi ključev, morate za glavno ime storitve Azure ločeno nastaviti dovoljenja za nadzor dostopa, ki temeljijo na vlogi, za storitev Dynamics 365 Customer Insights. Upoštevajte postopke, da [uporabite glavno ime storitve Azure](connect-service-principal.md) za shrambo ključev, ki jo je treba povezati.

- Shramba ključev mora imeti **onemogočen** požarni zid za storitev Key Vault.

- V istem je trezor za ključe [Azurna lokacija](https://azure.microsoft.com/global-infrastructure/geographies/#overview) kot okolje Customer Insights. Regija okolja v Customer Insights je navedena pod **Admin** > **sistem** > **O** > **Regija**.

### <a name="link-a-key-vault-to-the-environment"></a>Povezava shrambe ključev z okoljem

1. Pojdi do **Admin** > **Varnost**, nato pa izberite **Trezor ključev** zavihek.
1. V ploščici **Key Vault** izberite **Nastavitev**.
1. Izberite **Naročnina**.
1. Izberite shrambo ključev v spustnem seznamu **Key Vault**. Če se prikaže preveč shramb ključev, izberite skupino virov, da omejite rezultate iskanja.
1. Sprejmite izjavo **Zasebnost podatkov in skladnost**.
1. Izberite **Shrani**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Koraki za nastavitev povezanega trezorja ključev v Customer Insights.":::

Ploščica **Key Vault** zdaj prikazuje povezano ime shrambe ključev, skupino virov in naročnino. Pripravljena je za uporabo v nastavitvah povezave.
Za podrobnosti o tem, katera dovoljenja za trezor ključev so dodeljena Customer Insights, pojdite na [Dovoljenja, odobrena za trezor ključev](#permissions-granted-on-the-key-vault), kasneje v tem članku.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Uporaba shrambe ključev v nastavitvah povezave

Ko [vzpostavite povezave](connections.md) za sisteme drugih ponudnikov, lahko za konfiguracijo povezav uporabite skrivnosti iz povezane storitve Key Vault.

1. Odprite razdelek **Skrbnik** > **Povezave**.
1. Izberite **Dodaj povezavo**.
1. Za podprte vrste povezav je na voljo preklop **Uporabi storitev Key Vault**, če ste povezali shrambo ključev.
1. Namesto da ročno vnesete skrivnost, lahko izberete ime skrivnosti, ki kaže na skrivno vrednost v shrambi ključev.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Podokno za povezavo s povezavo SFTP, ki uporablja skrivnost storitve Key Vault.":::

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

Naslednja dovoljenja so dodeljena Customer Insights na povezanem trezorju ključev, če obstaja [Politika dostopa do Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) oz [Nadzor dostopa, ki temelji na vlogah Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) je omogočeno.

### <a name="key-vault-access-policy"></a>Pravilnik o dostopu za storitev Key Vault

| Vnesi        | Dovoljenja          |
| ----------- | -------------------- |
| Tipka         | [Pridobite ključe](/rest/api/keyvault/keys/get-keys/get-keys), [Pridobite ključ](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Skrivnost      | [Pridobite skrivnosti](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Pridobite skrivnost](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Potrdilo | [Pridobite potrdila](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Pridobite potrdilo](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Prejšnje vrednosti so minimalne za navedbo in branje med izvajanjem.

### <a name="azure-role-based-access-control"></a>Nadzor dostopa Azure, ki temelji na vlogi

Uporabniški vlogi Key Vault Uporabnik z dovoljenjem za branje in Key Vault Secrets bosta dodani za Customer Insights. Za podrobnosti o teh vlogah obiščite [Vdelane vloge Azure za postopke podatkovne ravnine Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Priporočila

- Uporabite ločen ali namenski trezor ključev, ki vsebuje samo skrivnosti, potrebne za Customer Insights. Preberite več o tem, zakaj [priporočamo ločene shrambe ključev](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Upoštevajte [najboljše postopke za uporabo storitve Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) za možnosti nadzora dostopa, varnostnega kopiranja, spremljanja sprememb in obnovitve.

## <a name="frequently-asked-questions"></a>Pogosto zastavljena vprašanja

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Ali lahko Customer Insights zapiše skrivnosti ali prepiše skrivnosti v trezor ključev?

Ne. Samo dovoljenja za branje in seznam, opisana v [podeljena dovoljenja](#permissions-granted-on-the-key-vault) razdelku prej v tem članku so dodeljeni Customer Insights. Sistem ne more dodati, izbrisati ali prepisati skrivnosti v shrambo ključev. To je tudi razlog, zakaj ne morete vnesti poverilnic, ko povezava uporablja storitev Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Ali lahko spremenim povezavo iz skrivnosti Key Vault v privzeto preverjanje pristnosti?

Ne. Ko jo konfigurirate z uporabo skrivnosti iz povezane shrambe ključev, se ne morete vrniti na privzeto povezavo. Ustvarite ločeno povezavo in odstranite staro, če je ne potrebujete več.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Kako lahko prekličem dostop do trezorja ključev za Customer Insights?

Odvisno od tega, ali je omogočen [pravilnik o dostopu za storitev Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ali [nadzor dostopa Azure, ki temelji na vlogi](/azure/key-vault/general/rbac-guide?tabs=azure-cli), morate odstraniti dovoljenja za glavno ime storitve `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` z imenom `Dynamics 365 AI for Customer Insights`. Vse povezave, ki uporabljajo shrambo ključev, bodo prenehale delovati.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Skrivnost, ki se uporablja v povezavi, je bila odstranjena iz shrambe ključev. Kaj lahko storim?

Obvestilo se prikaže v Customer Insights, ko konfigurirana skrivnost iz trezorja ključev ni več dostopna. Omogočite [začasno brisanje](/azure/key-vault/general/soft-delete-overview) v shrambi ključev za obnovitev skrivnosti, če so bile odstranjene po pomoti.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Povezava ne deluje, vendar je moja skrivnost v shrambi ključev. Kaj je lahko vzrok?

Ko ne more dostopati do trezorja ključev, se v storitvi Customer Insights prikaže obvestilo. Vzrok je lahko:

- Dovoljenja za principal storitve Customer Insights so bila odstranjena. Obnoviti jih je treba ročno.

- Požarni zid v shrambi ključev je omogočen. Požarni zid mora biti onemogočen, da bo trezor ključev ponovno dostopen za Customer Insights.
