---
title: Ustvarjanje povezave med vpogledi občinstva in vpogledi v interakcije
description: Ustvarjanje aktivne povezave med vpogledi občinstva in vpogledi v interakcije za omogočanje dvosmerne izmenjave podatkov.
ms.date: 09/08/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 56adc206d83bc6e34a55f11383393b5ac66da531
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229892"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Ustvarjanje povezave med vpogledi občinstva in vpogledi v interakcije

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Integracija med vpogledi v interakcije in vpogledi občinstva povezuje okolja iz obeh zmogljivosti in omogoča dvosmerno izmenjavo podatkov.

Uporabite poenotene profile in segmente iz vpogledov občinstva za več možnosti analize pri vpogledih v interakcije. Iz vpogledov v interakcije izvozite dogodke, ki imajo visoko poslovno vrednost. S temi dogodki dodajte podatke v poenotene profile v vpogledih občinstva.

## <a name="prerequisites"></a>Zahteve

- Občinstvo profili vpogledov morajo biti shranjeni v Azure Data Lake Storage račun, ki ga imate, ali v a [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro)&ndash; upravljano podatkovno jezero. 
- Vaše okolje vpogledov v občinstvo mora imeti povezano okolje storitve Dataverse. Če to okolje prav tako uporablja storitev Dataverse za shranjevanje podatkov, preverite, da ste izbrali možnost **Omogočite skupno rabo podatkov** v vpogledih v občinstvo. Za več informacij glejte razdelek [Ustvarjanje in konfiguriranje okolja v vpogledih v občinstvo](../audience-insights/create-environment.md).
- Potrebujete skrbniška dovoljenja za okolja vpogledov v interakcije in vpogledov občinstva.
- Povezana okolja morajo biti v isti geografski regiji.

> [!NOTE]
> - Če je vaša naročnina na vpoglede v občinstvo preskusna različica in uporablja interno upravljano jezero podatkov v vpogledih v občinstvo, se obrnite na [pirequest@microsoft.com](mailto:pirequest@microsoft.com) za pomoč. 
> - Če vaše okolje vpogledov občinstva uporablja vašo storitev Azure Data Lake Storage za shranjevanje podatkov, morate v račun za shranjevanje dodati glavno ime storitve Azure za vpoglede v interakcije. Za podrobnosti pojdite na [Povezava z računom Azure Data Lake Storage z glavnim imenom storitve Azure za vpoglede občinstva](../audience-insights/connect-service-principal.md). 


## <a name="create-an-environment-link"></a>Ustvarjanje povezave okolja

Povezavo okolja lahko ustvarite tako, da posodobite nastavitve v razdelku **Skrbnik** > **Okolje** pri vpogledih v interakcije.

**Vzpostavitev aktivne povezave med vpogledi občinstva in vpogledi v interakcije**

1. Na strani **Skrbnik okolja** izberite zavihek **Povezovanje okolij**.

    :::image type="content" source="media/integrate1.png" alt-text="Nastavite okolje.":::

1. Izberite **Nastavitev okolij** v zgornjem levem kotu ali na dnu zaslona.

     :::image type="content" source="media/integrate2.png" alt-text="Izbiranje okolja za vpoglede občinstva.":::

1. Izberite okolje vpogledov občinstva in nato izberite ***Naprej**, da končate. Zdaj lahko izberete izbirne funkcije za povezana okolja.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Omogočite atribute in segmente poenotenih profilov vpogledov občinstva

Ko povežete okolja, lahko izberete izbirne funkcije za povezana okolja. Te funkcije omogočajo poenotene atribute profila in segmente iz vpogledov občinstva za interaktivno analizo podatkov o strankah.

> [!IMPORTANT]
> Če želite, da se segmenti vpogledov občinstva prikažejo v vpogledih v interakcije, morate najprej [zagnati združevanje in postopke iz strežnika](../audience-insights/merge-entities.md). Postopki iz strežnika so pomembni, ker ustvarjajo edinstveno tabelo, ki pripravlja segmente vpogledov občinstva za skupno rabo z vpogledi v interakcije. (Če je načrtovana osvežitev sistema, se bodo samodejno vključili postopki iz strežnika.)

**Za analizo spletnih podatkov v vpogledih v interakcije**

1. Na strani **Skrbnik okolja** vklopite preklop **Deli podatke iz vpogledov občinstva z vpogledi v interakcije** in nato izberite **Naprej**.

    :::image type="content" source="media/integrate4.png" alt-text="Izberite funkcije.":::

1. Izberite atribute poenotenih profilov, ki bodo postali dimenzije v vpogledih v interakcije. (Vsi atributi niso uporabne dimenzije. Na primer, verjetno ne boste potrebovali **Ime** ali **Priimek** kot atribut za analizo dogodkov na vašem spletnem mestu.)

    :::image type="content" source="media/integrate5.png" alt-text="Obravnava dimenzij.":::

   >[!NOTE]
   > Vsi atributi profila vpogledov občinstva, ki predstavljajo identifikatorje (npr. **ID** in **nadomestni ID**), so filtrirani iz atributov, ki so na voljo, in postanejo dimenzije v vpogledih v interakcije.

1. Ko končate z izbiro atributov, izberite **Naprej**.
1. Dodajte uporabnike, ki si lahko ogledajo dimenzije in segmente profila vpogledov občinstva v vpogledih v interakcije.

    :::image type="content" source="media/integrate6.png" alt-text="Upravljanje dostopa do podatkov o strankah.":::

   > [!IMPORTANT]
   > Če v tem koraku izrecno ne dodate uporabnikov, bodo podatki pri vpogledih v interakcije skriti pred uporabniki.
   > Če želite, da se segmenti vpogledov občinstva prikažejo v vpogledih v interakcije, morate najprej [zagnati združevanje in postopke iz strežnika](../audience-insights/merge-entities.md). Postopki iz strežnika so pomembni, ker ustvarjajo edinstveno tabelo, ki pripravlja segmente vpogledov občinstva za skupno rabo z vpogledi v interakcije. (Če je načrtovana osvežitev sistema, se bodo samodejno vključili postopki iz strežnika.)

1. Preglejte svojo izbiro in nato izberite **Končaj**.

    :::image type="content" source="media/integrate7.png" alt-text="Preglejte nastavitve podatkov o strankah.":::

## <a name="export-refined-events-to-audience-insights"></a>Izvozite dogodke, ki so natančneje določeni, v vpoglede občinstva

Ko ustvarite povezavo med okolji, lahko dogodke, ki so natančneje določeni, iz vpogledov v interakcije izvozite v vpoglede občinstva in jih uvozite kot nov vir podatkov. 

Za več informacij pojdite na [Integracija spletnih podatkov iz vpogledov v interakcije z vpogledi občinstva](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
