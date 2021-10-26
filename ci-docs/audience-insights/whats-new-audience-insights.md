---
title: Nove in prihajajoče funkcije
description: Informacije o novih funkcijah, izboljšavah in popravkih napak.
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 5262ad20019e90e73ab121a5ab90e602c1a32b7e
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606134"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Kaj je novega pri zmogljivosti vpogledov v občinstvo Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Navdušeno sporočamo, da so najnovejše posodobitve pripravljene! V tem članku so povzete funkcije predogledne različice za javnost, splošne izboljšave razpoložljivosti in posodobitve funkcij. Če si želite ogledati dolgoročne načrte za funkcije, glejte [Načrti za izdajo storitev Dynamics 365 in Power Platform](/dynamics365/release-plans/).

Posodobitve izdajamo po posameznih regijah. Tako lahko nekatere regije vidijo funkcije pred drugimi. Če ni določeno drugače, vam ni treba ničesar storiti in aplikacijo bomo samodejno posodobili brez izpadov.

> [!TIP]
> Če želite predložiti zahteve glede funkcij in predloge za izdelke ter glasovati o njih, pojdite na [portal zamisli za aplikacijo Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="september-2021-updates"></a>Posodobitve v septembru 2021

Posodobitve v septembru 2021 vključujejo nove funkcije, nadgradnje zmogljivosti in popravke napak.

### <a name="activities"></a>dejavnosti

- **Izboljšave časovnice dejavnosti** Filtre za časovnico dejavnosti smo razširili na profile strank. Poleg tega lahko z novim podoknom za filtriranje filtrirate po vrsti dejavnosti in datumu. Datume je mogoče filtrirati z različnimi pogoji. Za več informacij glejte [Ogled časovnice dejavnosti v profilih strank](activities.md#view-activity-timelines-on-customer-profiles).

### <a name="relationships"></a>Odnosi

- **Podpora za odnos z več skoki** Pri konfiguriranju dejavnosti in določanju odnosov med entitetami uporabite odnose z več skoki. Odnosi z več skoki uporabljajo vmesno entiteto za povezavo dveh entitet. Ko konfigurirate dejavnost, lahko z odnosom z več skoki povežete entiteto dejavnosti z vmesno entiteto in nato z entiteto stranke. Odnose z več skoki lahko združite z odnosi z več potmi. Za več informacij glejte [Odnos z več skoki](relationships.md#multi-hop-relationship).

- **Podpora za odnos z več potmi** Pri konfiguriranju dejavnosti in določanju odnosov med entitetami uporabite odnose z več potmi. Odnosi z več potmi povezujejo izvorno entiteto z več entitetami. Ko konfigurirate dejavnost, lahko z odnosom z več potmi povežete entiteto dejavnosti z več entitetami strank. Odnose z več potmi lahko združite z odnosi z več skoki. Za več informacij glejte [Odnos z več potmi](relationships.md#multi-path-relationship).

## <a name="august-2021-updates"></a>Posodobitve v avgustu 2021

Posodobitve v juliju in avgustu 2021 vključujejo novo funkcijo, nadgradnjo zmogljivosti in popravke napak.

### <a name="extensibility"></a>Razširljivost

- **Izvozite segmente v storitev Klaviyo** Razširili smo svoje [cilje za izvoz in vključili storitev Klaviyo](export-klaviyo.md). S storitvijo Klaviyo zdaj lahko izvažate segmente, da ustvarite akcije, izvedete e-poštno trženje in uporabite določene skupine strank. 


## <a name="june-2021-updates"></a>Posodobitve za junij 2021

Posodobitve v juniju 2021 vključujejo številne funkcije, nadgradnje zmogljivosti in popravke napak.

### <a name="data-ingestion"></a>Uvoz podatkov

- **Izboljšane posodobitve napredka pri poenotenju podatkov** Zdaj si lahko ogledate preglednejše in izboljšane dinamične posodobitve stanja korakov za [postopek poenotenja podatkov](data-unification.md). Ta funkcija vam omogoča, da spremljate podroben napredek, razumete potek postopka in po potrebi ukrepate pri posameznem koraku.

### <a name="extensibility"></a>Razširljivost

- **Izvozite segmente in druge podatke v Salesforce Marketing Cloud** Cilje za izvoz smo razširili tudi na [Salesforce Marketing Cloud](export-salesforce.md). Sedaj lahko izvažate segmente in druge vrste podatkov v Salesforce Marketing Cloud z izvozom blagovne znamke SFTP. V Salesforceu lahko uvoz podatkov popolnoma avtomatizirate in uporabite za ustvarjanje učinkovitejših trženjskih akcij.  
 
- **Izvozite segmente v ActiveCampaign** Cilje za izvoz smo razširili tudi na [Active Campaign](export-active-campaign.md). S storitvijo ActiveCampaign zdaj lahko izvažate segmente, da ustvarite akcije, izvedete e-poštno trženje in sodelujete z določenimi skupinami strank.
 
- **Izvozite segmente v Sendinblue** Cilje za izvoz smo razširili tudi na [Sendinblue](export-sendinblue.md). S storitvijo Sendinblue zdaj lahko izvažate segmente, da ustvarite akcije, izvedete e-poštno trženje in sodelujete z določenimi skupinami strank.
 
### <a name="ux-updates"></a>Posodobitve uporabniških izkušenj 

- **Nova in izboljšana stran »Stranke« in stran s podrobnostmi o profilu** Za boljšo uporabniško izkušnjo in izboljšano učinkovitost smo prenovili stran »Stranke« in stran s podrobnostmi o profilu. Te spremembe vam omogočajo ogled, razvrščanje, iskanje in filtriranje strank. Filtri so zdaj predstavljeni v URL-ju za nemoteno skupno rabo rezultatov iskanja z drugimi uporabniki. Rezultate iskanja lahko shranite tudi kot segment.    
  Stran s podrobnostmi za profile strank zdaj združuje podatke v različnih podrazdelkih, kot so demografski podatki, ID-ji in drugi atributi profila za boljšo berljivost. Drugi razdelki na strani s podrobnostmi o profilu so zdaj bolj interaktivni. Na primer razdelek dejavnosti zdaj omogoča filtriranje in razvrščanje.


## <a name="may-2021-updates"></a>Posodobitve za maj 2021

Posodobitve maja 2021 vključujejo številne funkcije, nadgradnje zmogljivosti in popravke napak.

### <a name="data-ingestion"></a>Uvoz podatkov

- **Ogled ali sprememba metapodatkov ali definicije entitete, ko pripenjate podatke iz Azure Data Lake Storage** Zdaj si lahko ogledujete in urejate metapodatke ali definicijo entitete v vpogledih za občinstvo, ko pripenjate podatke iz mape Common Data Model v vaši storitvi Azure Data Lake Storage. Ta zmogljivost zagotavlja povratne informacije v realnem času, preverjanje modelov in preverjanje napak. Omogoča vam nemoteno urejanje model.json in manifest.json.

### <a name="extensibility"></a>Razširljivost

- **Izboljšan izvoz segmentov, razpored po meri in podvajanje** Zdaj si lahko [ogledate vse izvoze za določen segment](export-destinations.md#view-exports-and-export-details) na seznamu. Ta novi pogled pomaga pri upravljanju uporabe določenega segmenta in prilagajanju obstoječih ali ustvarjanju novih izvozov.    
  [Določite lahko urnike osveževanja po meri](export-destinations.md#schedule-and-run-exports) za posamezen izvoz ali več izvozov hkrati. Do zdaj so se izvozi izvajali ob vsakem osveževanju sistema.    
  Namesto da bi ustvarili nov izvoz brez predloge, lahko začnete na podlagi obstoječega in s tem prihranite nekaj časa.

- **Izvoz segmentov v Microsoft Advertising** Ciljne lokacije za izvoz smo razširili, da vključujejo tudi Microsoft Advertising. V storitvi Microsoft Advertising lahko s poenotenimi podatki o profilih strank ustvarite ciljne skupine storitve Customer Match in jih uporabite za svoje oglaševalske akcije. Če želite več informacij, glejte [Izvoz segmentov v Microsoft Advertising](export-microsoft-advertising.md).

- **Izvoz segmentov v LinkedIn Ads** Izvozne cilje smo razširili, tako da vključujejo oglase LinkedIn Ads in vam omogočili, da prek LinkedIna odklenete ciljanje stikov in ciljanje podjetij z izvozom vaših poenotenih podatkov o profilih strank. Če želite več informacij, glejte [Izvoz segmentov v LinkedIn Ads](export-linkedin-ads.md).


- **Izvoz segmentov v Omnisend** Ciljne lokacije za izvoz smo razširili, da vključujejo tudi Omnisend. S segmenti, ustvarjenimi v vpogledih občinstva, ustvarite akcije, zagotovite e-poštno trženje in uporabite določene skupine strank s storitvijo Omnisend. Če želite več informacij, glejte [Izvoz segmentov v Omnisend](export-omnisend.md)

### <a name="predictions"></a>Predvidevanja

- **Poročilo o uporabnosti vhodnih podatkov** Poročilo o uporabnosti vhodnih podatkov ponuja strnjen prikaz napak in opozoril, ki jih lahko ustvarijo vaše vnaprej pripravljene napovedi. Prav tako daje priporočila, kako izboljšati zmogljivost modela.    
  Poročilo je na voljo, ko model zaključi s postopkom kvalificiranja. Ustvarjeno je za vsak model posebej, ne glede na to, ali je bilo uspešno zaključeno ali ne.
  Trenutno je ta funkcija na voljo samo za model izgube transakcije. Za več informacij glejte [Poročilo o uporabnosti vhodnih podatkov](manage-predictions.md#input-data-usability-report).

### <a name="relationships"></a>Odnosi

- **Vizualizator odnosov** Pogled vizualizatorja odnosov vam omogoča, da vidite vse obstoječe odnose med entitetami in njihovo kardinalnostjo. Odnosi so zdaj organizirani v skupine: ustvaril uporabnik, sistem in podedovani odnosi. Pogled lahko izvozite tudi kot sliko. Več informacij najdete v razdelku [Ogled odnosov](relationships.md#view-relationships). 

## <a name="april-2021-updates"></a>Posodobitve iz aprila 2021

Posodobitve aprila 2021 vključujejo številne funkcije, nadgradnje zmogljivosti in popravke napak.

### <a name="data-unification"></a>Poenotenje podatkov
 
- **Izboljšana izkušnja spajanja za poenotenje podatkov**    
  
   Zdaj imamo izboljšano uporabniško izkušnjo pri konfiguraciji spajanja za postopek poenotenja podatkov. Spremembe vključujejo intuitivno urejanje spojenih polj in podrobne statistične podatke o združenih in enojnih poljih.

- **Preurejanje entitete in konfiguriranje vseh izvornih zapisov v entiteto stranke**  
      
   Zdaj lahko v postopku poenotenja podatkov preuredite in odstranite entitete iz obstoječega načrta združitve. To omogoča prilagoditev preurejanja entitet v postopku ujemanja glede na poslovne potrebe. Poleg tega omogočamo vključitev vseh neujemajočih se zapisov v končno entiteto *stranke*, kar omogoča opredelitev določitve nabora podatkov o profilih strank.

### <a name="enrichments"></a>Obogatitve

 - **Nova obogatitev: obogateni naslovi**    
  
   Z veseljem predstavljamo novo obogatitev za izboljšanje naslovov v podatkih o strankah. Naslovi v vaših podatkih so lahko nestrukturirani, nepopolni ali napačni. Ta funkcija uporablja Microsoftove modele za normalizacijo in obogatitev naslovov v obliko Common Data Model za boljšo natančnost in vpoglede.
 
   Če želite več informacij, glejte razdelek [Obogatitev profilov strank z izboljšanimi naslovi](enrichment-enhanced-addresses.md).

- **Izkušnja vodene konfiguracije za obogatitve**    
  
   Vrnili smo se k izkušnji konfiguracije za obogatitve s preprosto vodeno izkušnjo. Zdaj imate jasen postopek po korakih za ustvarjanje in urejanje obogatitev.
 
   Poleg tega smo ločili konfiguracijo povezav za obogatitve drugih proizvajalcev, da omogočimo uporabo iste povezave za več obogatitev. Nove povezave lahko konfigurirajo samo skrbniki, vendar so ustvarjene povezave na voljo tako skrbnikom kot sodelavcem.    

   Če želite več informacij, glejte razdelek [Pregled povezav](connections.md).

- **Več obogatitev iste vrste**    
  
   Zdaj uporabnikom omogočamo ustvarjanje in upravljanje več obogatitev iste vrste obogatitve. Zdaj lahko na primer ustvarite dve ločeni obogatitvi naslova, da obogatite dva različna segmenta strank. Omejitve veljajo za število obogatitev iste vrste, ki jih lahko ustvarite, in se lahko razlikujejo glede na vrsto obogatitve.
  
   Za več informacij glejte [Obogatitev za profile strank](enrichment-hub.md).

## <a name="march-2021-updates"></a>Posodobitve marca 2021

Posodobitve marca 2021 vključujejo številne funkcije, nadgradnje zmogljivosti in popravke napak.

### <a name="activities"></a>dejavnosti

- **Čarovnik za dejavnosti in semantične vrste**

   Izboljšali in posodobili smo izkušnjo preslikave dejavnosti, da bi vodili in poenostavili ustvarjanje preslikave dejavnosti. V tej novi izkušnji uporabniki dobijo vodeno izkušnjo, ki jim pomaga dokončati posamezni korak postopka. V koraku za preslikavo dejavnosti lahko uporabnik poleg izbire med številnimi vrstami dejavnosti izbere tudi semantično preslikavo podatkov za atribut *Naročnina* in/ali *SalesOrderLine* v industrijske standardne sheme, ki se lahko uporabljajo za nadaljnjo porabo.   

   Za več informacij glejte [Dejavnosti stranke](activities.md).

### <a name="data-ingestion"></a>Uvoz podatkov

- **Povezava s podatkovnimi viri na mestu uporabe prek podatkovnih tokov in prehodov Power Platform** Z veseljem objavljamo predogled podatkovnih tokov Power Platform in povezljivosti na mestu uporabe z uporabo prehodov v storitvi Customer Insights s povezanim okoljem Power Platform ali Dataverse. Vsi novi viri podatkov, ustvarjeni v okolju Customer Insights s povezanim okoljem Dataverse bodo privzeto nastavljeni na podatkovne tokove Power Platform, ki zagotavljajo podatkovno povezljivost na mestu uporabe in bogat nabor povezovalnikov in zmogljivosti preoblikovanja.

### <a name="extensibility"></a>Razširljivost

- **Izvozi, združeni v povezave in izvoze** Spremenili smo ime strani **Izvozne destinacije** na **Povezave** in dodali ločeno stran **Izvozi**. Kot del te posodobitve bomo obstoječe izvoze preoblikovali v pare iz povezave in izvoza, ki uporablja to povezavo. Skrbnikom imajo tako jasnejši pregled nad odhodnimi podatki na strani **Povezave**. Vse uporabniške vloge imajo dostop do strani **Izvozi**, vendar lahko samo skrbniki dovolijo, da sodelavci urejajo določene izvoze s povezavami v skupni rabi.     
  Za več informacij glejte [Pregled povezav](connections.md) in [Pregled izvozov](export-destinations.md).

- **Izvoz segmentov v Campaign Monitor** Ciljne lokacije za izvoz smo razširili, da vključujejo tudi Campaign Monitor. Zdaj lahko izvozite segmente iz Customer Insights na sezname Campaign Monitor in jih uporabite kot izhodišče za svoje tržne kampanje.    
   Če želite več informacij, glejte [Izvoz v Campaign Monitor](export-campaign-monitor.md).

- **Izvoz segmentov v Constant Contact** Ciljne lokacije za izvoz smo razširili, da vključujejo tudi Constant Contact. Zdaj lahko izvozite segmente iz Customer Insights na sezname Constant Contact in jih uporabite kot izhodišče za svoje tržne kampanje.   
   Če želite več informacij, glejte [Izvoz v Constant Contact](export-constant-contact.md).

- **Izvoz segmentov v RollWorks** Ciljne lokacije za izvoz smo razširili, da vključujejo tudi RollWorks. Zdaj lahko izvozite segmente iz Customer Insights v občinstva RollWorks in jih uporabite kot izhodišče za svoje oglaševanje v okviru prodaje podjetjem.    
   Če želite več informacij, glejte [Izvoz v RollWorks](export-rollworks.md).

- **Izvoz segmentov v Snapchat** Ciljne lokacije za izvoz smo razširili, da vključujejo tudi Snapchat. Zdaj lahko izvozite segmente iz Customer Insights v občinstva Snapchat in jih uporabite kot izhodišče za oglaševanje.     
   Če želite več informacij, glejte [Izvoz v Snapchat](export-snapchat.md).

### <a name="predictions"></a>Predvidevanja

- **Uporaba filtrov za izdelke v napovednih priporočilih izdelkov** V naš model priporočil izdelkov smo dodali možnost uporabe filtrov za izdelke. Zdaj lahko ustvarite predvidevanje, ki uporablja samo podmnožico vaših izdelkov.    
   Za več informacij glejte [Konfiguriranje filtrov izdelkov](predict-product-recommendation.md#configure-product-filters).

- **Ustvarjanje segmentov iz modelov predvidevanja** Dodali smo hiter način za ustvarjanje segmentov z rezultati modela predvidevanja. Na strani z rezultati modela lahko enostavno ustvarite nov segment, tako da izberete novo možnost **Ustvari segment**.    
  Za več informacij glejte [Ustvarjanje segmenta na podlagi modela predvidevanja](prediction-based-segment.md).

- **Pojasnila za priporočila izdelkov** Dodali smo informacije, ki pojasnjujejo ključne dejavnike, ki se jih je model umetne inteligence naučil za oblikovanje priporočil izdelkov, in stopnjo, s katero ti dejavniki prispevajo k priporočilom izdelkov. Te informacije se dodajo na zaslon z rezultati modela.    
   Za več informacij glejte [Pregled stanja in rezultatov predvidevanja](predict-product-recommendation.md#review-a-prediction-status-and-results).

## <a name="february-2021-updates"></a>Posodobitve februarja 2021

Posodobitve v februarju 2021 vključujejo več funkcij, nadgradnje zmogljivosti in popravke napak.

#### <a name="extensibility"></a>Razširljivost

- **Izvoz segmentov v AdRoll**

  Cilje za izvoz smo razširili na storitev AdRoll. Zdaj lahko izvozite segmente iz Customer Insights v občinstva AdRoll in jih uporabite kot osnovni model za oglaševanje. Če želite več informacij, glejte razdelek [Povezovalnik za AdRoll](export-adroll.md).

#### <a name="segments"></a>Segmenti
 
- **Podvajanje segmenta**
  
  Če želite na podlagi obstoječega segmenta ustvariti novega, lahko segment podvojite segment in ga uredite, da ga še izboljšate. 

- **Dodajanje dodatnih atributov segmentu**

  Zdaj lahko v izhod segmenta vključite atribute, tudi če ti atributi niso del profila stranke. Vključite na primer ID-je naročnin v segment, čeprav je del naročniške entitete, ki ima razmerje M:1 z entiteto stranke. Dokler atribut pripada entiteti, povezani z entiteto stranke, lahko te atribute vključite.  

#### <a name="predictions"></a>Predvidevanja

- **Ustvarjanje predvidenih priporočil izdelkov**

  Eden prvih korakov za izboljšanje poslovnega prihodka in povečanje zvestobe strank s prilagajanjem in sodelovanjem je razumeti, za nakup česa se zanimajo stranke. Podajanje priporočil za izdelke, ki niso usklajeni z interesi vaše stranke, lahko ustvari občutek nepovezanosti med stranko in vašim podjetjem ter na koncu omeji skupni potencialni prihodek in izkušnjo stranke. 

  Z lastnimi podatki lahko zdaj ustvarite predvidevanja za izdelke, ki jih bodo vaše stranke verjetno kupile v prihodnosti. Za več informacij glejte [Predvidevanje priporočil izdelkov](predict-product-recommendation.md).

#### <a name="system-administration"></a>Skrbništvo sistema

- **Okolje za kopiranje podpira več vrst virov podatkov**

  Skrbniki lahko kopirajo konfiguracije okolja v novo okolje v isti organizaciji. Ta funkcija razširja funkcionalnost kopiranja okolja v primerih, ko so v uporabi viri podatkov na podlagi podatkovnega jezera, ki ga upravlja Microsoft Dataverse, ali mape Common Data Model.

## <a name="january-2021-updates"></a>Posodobitve v januarju 2021

Posodobitve v januarju 2021 vključujejo številne funkcije, nadgradnje učinkovitosti delovanja in popravke napak.

#### <a name="extensibility"></a>Razširljivost

- **Razširjena funkcionalnost in izboljšana učinkovitost delovanja za izvoz SFTP** Zdaj lahko izvozite vse izhodne entitete rešitve Customer Insights v gostitelja SFTP. Izvoz je bil predhodno omejen na segmentne entitete. Poleg tega učinkovitost delovanja izvoza SFTP omogoča večjo količino podatkov v krajšem času, odvisno od učinkovitosti delovanja vašega gostitelja SFTP.    
  Za več informacij glejte [Povezovalnik za SFTP (predogled)](export-sftp.md).  

#### <a name="segments"></a>Segmenti

- **Predlagani segmenti za izboljšanje meritev, ki jih omogoča strojno učenje** Obstaja nov način odkrivanja in ustvarjanja segmentov. Sistem uporablja model umetne inteligence za predlaganje segmentov, ki lahko pomagajo izboljšati KPI (mera), kateremu že sledite. Prikazujemo obseg vpliva atributov, ki jih izberete na eno mero ali drug primarni atribut. Ti podatki pomagajo najti morebitne segmente, ki predstavljajo priložnosti.    
  Za več informacij glejte [Predlagani segmenti (predogled)](suggested-segments.md).

#### <a name="data-unification"></a>Poenotenje podatkov

- **Izboljšana izkušnja povezovanja** Izkušnja povezovanja je bila posodobljena v območju poenotenja podatkov. Omogoča vam konfiguriranje in ogled pravil za povezovanje, vključno s podrobnimi statističnimi podatki, ki dodatno pojasnijo, kako deluje povezovanje. Obstajajo možnosti, da onemogočite pravilo za povezovanje, tako da ni več aktivno, hkrati pa ohranite konfiguracijo, pravila za povezovanje »povleci in spusti« in še več.
  Za več informacij glejte [Povezovanje entitet](match-entities.md).

- **Rezultat odstranjevanja podvojenih elementov iz postopka ujemanja je na voljo kot entiteta** Rezultat odstranjevanja podvojenih elementov iz postopka ujemanja je za nadaljnjo analizo zapisan v ločeno entiteto. Ta entiteta je sestavljena iz polj, uporabljenih v postopku odstranjevanja podvojenih elementov, in zapisa zmagovalca ter ustreznih nadomestnih zapisov, ki se spojijo z zapisom zmagovalca.
  Za več informacij glejte [Rezultat odstranjevanja podvojenih elementov kot entiteta](match-entities.md#deduplication-output-as-an-entity).

#### <a name="system-administration"></a>Skrbništvo sistema

- **Brezhibno deljenje podatkov s storitvijo Microsoft Dataverse** Zdaj lahko rezultate storitve Customer Insights delite z aplikacijami Microsoft Dataverse z uporabo shrambe Data Lake, ki jo upravlja rešitev Microsoft Dataverse. Ko okolje Dataverse povežete s storitvijo Customer Insights, lahko omogočite skupno rabo podatkov.
  Za več informacij glejte [Upravljanje okolij](manage-environments.md).




[!INCLUDE[footer-include](../includes/footer-banner.md)]