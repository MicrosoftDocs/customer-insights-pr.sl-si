---
title: Povezave z drugimi storitvami iz rešitve Customer Insights.
description: Delite podatke z drugimi storitvami.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 17e04b243e9b3d4375c86f5a890a18be35956835
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304992"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="5dae1-103">Pregled povezav (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="5dae1-103">Connections (preview) overview</span></span>

<span data-ttu-id="5dae1-104">Povezave so ključnega pomena za omogočanje skupne rabe podatkov iz rešitve Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5dae1-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="5dae1-105">Vsaka povezava vzpostavi skupno rabo podatkov z določeno storitvijo.</span><span class="sxs-lookup"><span data-stu-id="5dae1-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="5dae1-106">Povezave so temelj za [konfiguriranje obogatitev neodvisnih proizvajalcev](enrichment-hub.md) in [konfiguriranje izvozov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="5dae1-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="5dae1-107">Isto povezavo je mogoče uporabiti večkrat.</span><span class="sxs-lookup"><span data-stu-id="5dae1-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="5dae1-108">Ena povezava s storitvijo Dynamics 365 Marketing na primer deluje za več izvozov, eno povezavo za Leadspace pa lahko uporabite za več obogatitev.</span><span class="sxs-lookup"><span data-stu-id="5dae1-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="5dae1-109">Odprite razdelek **Skrbnik** > **Povezave**, da ustvarite povezave in si jih ogledate.</span><span class="sxs-lookup"><span data-stu-id="5dae1-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="5dae1-110">V zavihku **Povezave** so prikazane vse dejavne povezave.</span><span class="sxs-lookup"><span data-stu-id="5dae1-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="5dae1-111">Na seznamu je prikazana vrstica za vsako posamezno povezavo.</span><span class="sxs-lookup"><span data-stu-id="5dae1-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="5dae1-112">Na zavihku **Odkrivanje** pridobite hiter pregled in opis ter ugotovite, kaj lahko storite s posamezno možnostjo razširljivosti.</span><span class="sxs-lookup"><span data-stu-id="5dae1-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="5dae1-113">Izvozi</span><span class="sxs-lookup"><span data-stu-id="5dae1-113">Exports</span></span>

<span data-ttu-id="5dae1-114">Nove povezave lahko konfigurirajo samo skrbniki, lahko pa sodelavcem dodelijo dostop do uporabe obstoječih povezav.</span><span class="sxs-lookup"><span data-stu-id="5dae1-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="5dae1-115">Skrbniki nadzorujejo, kam so lahko poslani podatki, sodelavci pa določajo koristno vsebino in pogostost, ki ustreza njihovim potrebam.</span><span class="sxs-lookup"><span data-stu-id="5dae1-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="5dae1-116">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="5dae1-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="5dae1-117">Obogatitve</span><span class="sxs-lookup"><span data-stu-id="5dae1-117">Enrichments</span></span>

<span data-ttu-id="5dae1-118">Nove povezave lahko konfigurirajo samo skrbniki, vendar so ustvarjene povezave vedno na voljo tako skrbnikom kot sodelavcem.</span><span class="sxs-lookup"><span data-stu-id="5dae1-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="5dae1-119">Skrbniki upravljajo poverilnice in podelijo soglasje za prenose podatkov.</span><span class="sxs-lookup"><span data-stu-id="5dae1-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="5dae1-120">Povezave lahko nato za obogatitve uporabijo tako skrbniki kot sodelavci.</span><span class="sxs-lookup"><span data-stu-id="5dae1-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="5dae1-121">Dodajanje nove povezave</span><span class="sxs-lookup"><span data-stu-id="5dae1-121">Add a new connection</span></span>

<span data-ttu-id="5dae1-122">Za dodajanje povezav morate imeti [skrbniška dovoljenja](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="5dae1-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="5dae1-123">Če vzpostavite povezavo z drugimi Microsoftovimi storitvami, predvidevamo, da sta obe storitvi del iste organizacije.</span><span class="sxs-lookup"><span data-stu-id="5dae1-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="5dae1-124">Odprite razdelek **Skrbnik** > **Povezave (predogled)**.</span><span class="sxs-lookup"><span data-stu-id="5dae1-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="5dae1-125">Pojdite na zavihek **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="5dae1-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="5dae1-126">Izberite možnost **Dodaj povezavo**, da ustvarite novo povezavo.</span><span class="sxs-lookup"><span data-stu-id="5dae1-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="5dae1-127">V spustnem meniju izberite vrsto povezave, ki jo želite ustvariti.</span><span class="sxs-lookup"><span data-stu-id="5dae1-127">Choose from the dropdown menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="5dae1-128">V podoknu **Vzpostavitev povezave** vnesite zahtevane podrobnosti.</span><span class="sxs-lookup"><span data-stu-id="5dae1-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="5dae1-129">**Prikazno ime** in vrsta povezave opisujeta povezavo.</span><span class="sxs-lookup"><span data-stu-id="5dae1-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="5dae1-130">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="5dae1-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="5dae1-131">Dejanska polja so odvisna od storitve, s katero vzpostavljate povezavo.</span><span class="sxs-lookup"><span data-stu-id="5dae1-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="5dae1-132">Podrobnosti o določeni vrsti povezave lahko izveste v ustreznem članku o ciljni storitvi.</span><span class="sxs-lookup"><span data-stu-id="5dae1-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="5dae1-133">Izberite možnost **Shrani**, da ustvarite povezavo.</span><span class="sxs-lookup"><span data-stu-id="5dae1-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="5dae1-134">Izberete lahko tudi **Nastavitev** na ploščici na zavihku **Odkrivanje**.</span><span class="sxs-lookup"><span data-stu-id="5dae1-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="5dae1-135">Omogočanje uporabe povezav za izvoze podatkov za sodelavce</span><span class="sxs-lookup"><span data-stu-id="5dae1-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="5dae1-136">Ko nastavljate povezavo za izvoz podatkov ali jo urejate, izberete uporabnike, ki lahko uporabijo to povezavo za določanje [izvozov podatkov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="5dae1-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="5dae1-137">Privzeto je povezava na voljo uporabnikom z vlogo skrbnika.</span><span class="sxs-lookup"><span data-stu-id="5dae1-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="5dae1-138">To nastavitev lahko spremenite v razdelku **Izberite, kdo lahko uporablja to povezavo** in dovolite uporabo te povezave uporabnikom z vlogo sodelavca.</span><span class="sxs-lookup"><span data-stu-id="5dae1-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="5dae1-139">Sodelavci ne bodo mogli videti povezave ali je urejati.</span><span class="sxs-lookup"><span data-stu-id="5dae1-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="5dae1-140">Pri ustvarjanju izvoza bodo videli le prikazno ime in vrsto povezave.</span><span class="sxs-lookup"><span data-stu-id="5dae1-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="5dae1-141">Če date povezavo v skupno rabo, sodelavcem dovolite uporabo povezave.</span><span class="sxs-lookup"><span data-stu-id="5dae1-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="5dae1-142">Sodelavci bodo videli skupne povezave, ko nastavijo izvoze.</span><span class="sxs-lookup"><span data-stu-id="5dae1-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="5dae1-143">Upravljajo lahko vse izvoze, v katerih je uporabljena ta specifična povezava.</span><span class="sxs-lookup"><span data-stu-id="5dae1-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="5dae1-144">To nastavitev lahko spremenite, hkrati pa ohranite izvoze, ki so jih že določili sodelavci.</span><span class="sxs-lookup"><span data-stu-id="5dae1-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="5dae1-145">Urejanje povezave</span><span class="sxs-lookup"><span data-stu-id="5dae1-145">Edit a connection</span></span>

1. <span data-ttu-id="5dae1-146">Odprite razdelek **Skrbnik** > **Povezave (predogled)**.</span><span class="sxs-lookup"><span data-stu-id="5dae1-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="5dae1-147">Pojdite na zavihek **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="5dae1-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="5dae1-148">Izberite navpične tri pike zraven povezave, ki jo želite urediti.</span><span class="sxs-lookup"><span data-stu-id="5dae1-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="5dae1-149">Izberite **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="5dae1-149">Select **Edit**.</span></span>

1. <span data-ttu-id="5dae1-150">Spremenite vrednosti, ki jih želite posodobiti, in izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="5dae1-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="5dae1-151">Odstranjevanje povezave</span><span class="sxs-lookup"><span data-stu-id="5dae1-151">Remove a connection</span></span>

<span data-ttu-id="5dae1-152">Če je povezava, ki jo želite odstraniti, uporabljena v obogatitvah ali izvozih, jo morate najprej odstraniti oziroma z njo prekiniti povezavo.</span><span class="sxs-lookup"><span data-stu-id="5dae1-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="5dae1-153">Pogovorno okno za odstranitev vas bo vodilo do ustreznih obogatitev oziroma izvozov.</span><span class="sxs-lookup"><span data-stu-id="5dae1-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> 

<span data-ttu-id="5dae1-154">Odstranjene obogatitve in izvozi bodo postali nedejavni.</span><span class="sxs-lookup"><span data-stu-id="5dae1-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="5dae1-155">Ponovno jih aktivirate tako, da jim na strani [Obogatitve](enrichment-hub.md) ali [Izvozi](export-destinations.md) dodate drugo povezavo.</span><span class="sxs-lookup"><span data-stu-id="5dae1-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="5dae1-156">Odprite razdelek **Skrbnik** > **Povezave (predogled)**.</span><span class="sxs-lookup"><span data-stu-id="5dae1-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="5dae1-157">Pojdite na zavihek **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="5dae1-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="5dae1-158">Izberite navpične tri pike zraven povezave, ki jo želite odstraniti.</span><span class="sxs-lookup"><span data-stu-id="5dae1-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="5dae1-159">Na spustnem seznamu izberite **Odstrani**.</span><span class="sxs-lookup"><span data-stu-id="5dae1-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="5dae1-160">Prikaže se potrditveno pogovorno okno.</span><span class="sxs-lookup"><span data-stu-id="5dae1-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="5dae1-161">Če je povezava uporabljena v obogatitvah ali izvozih, izberite gumb, da preverite, kateri elementi uporabljajo povezavo.</span><span class="sxs-lookup"><span data-stu-id="5dae1-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="5dae1-162">**Izvozi:** če želite odstraniti povezavo, lahko izberete možnost odstranjevanja ali prekinjanja povezave z izvozi.</span><span class="sxs-lookup"><span data-stu-id="5dae1-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="5dae1-163">Za prekinitev povezave z izvozom lahko skrbniki uporabijo dejanje **Prekini povezavo**.</span><span class="sxs-lookup"><span data-stu-id="5dae1-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="5dae1-164">To dejanje je na voljo za posamezen izbrani izvoz ali več njih.</span><span class="sxs-lookup"><span data-stu-id="5dae1-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="5dae1-165">Če prekinete povezavo, se konfiguracija izvoza ohrani, vendar se ne bo zagnala, dokler ji ni dodana druga povezava.</span><span class="sxs-lookup"><span data-stu-id="5dae1-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="5dae1-166">**Obogatitve:** če želite odstraniti povezavo, lahko izberete možnost deaktiviranja ali odstranjevanja obogatitev.</span><span class="sxs-lookup"><span data-stu-id="5dae1-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="5dae1-167">Ko za povezavo ni več odvisnosti, se vrnite v razdelek **Skrbnik** > **Povezave** in poskusite znova odstraniti povezavo.</span><span class="sxs-lookup"><span data-stu-id="5dae1-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="5dae1-168">Za potrditev izbrisa izberite možnost **Odstrani**.</span><span class="sxs-lookup"><span data-stu-id="5dae1-168">To confirm the deletion, select **Remove**.</span></span>

