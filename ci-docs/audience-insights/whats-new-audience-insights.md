---
title: Nove in prihajajoče funkcije
description: Informacije o novih funkcijah, izboljšavah in popravkih napak.
ms.date: 11/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 07b4bee0445f9cd7d53a37cd405af839feb07ae3
ms.sourcegitcommit: 4004eadac7a65e50e0a409cb925958523c2b6348
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/30/2020
ms.locfileid: "4650024"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Kaj je novega pri zmogljivosti vpogledov v občinstvo Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Navdušeno sporočamo, da so najnovejše posodobitve pripravljene! V tem članku so povzete funkcije predogledne različice za javnost, splošne izboljšave razpoložljivosti in posodobitve funkcij. Če si želite ogledati dolgoročne načrte za funkcije, glejte [Načrti za izdajo storitev Dynamics 365 in Power Platform](https://docs.microsoft.com/dynamics365/release-plans/).

Če želite izvedeti več o zmogljivostih, načrtovanih v zadnjih šestih mesecih, si lahko ogledate tudi naslednji videoposnetek.

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

Posodobitve izdajamo po posameznih regijah. Tako lahko nekatere regije vidijo funkcije pred drugimi. Če ni določeno drugače, vam ni treba ničesar storiti in aplikacijo bomo samodejno posodobili brez izpadov.

> [!TIP]
> Če želite predložiti zahteve glede funkcij in predloge za izdelke ter glasovati o njih, pojdite na [portal zamisli za aplikacijo Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="november-2020-updates"></a>Posodobitve v novembru 2020

Posodobitve v novembru 2020 vključujejo več funkcij, nadgradnje zmogljivosti in popravke napak.

### <a name="new-and-updated-features-in-november-2020"></a>Nove in posodobljene funkcije v novembru 2020

#### <a name="data-enrichment"></a>Obogatitev podatkov

- **Prek uvoza po meri s protokolom za varen prenos datotek (SFTP) pridobite lastne podatke za obogatitev**
  
  Uvoz po meri SFTP vam omogoča uvoz podatkov za obogatitev, ki jim ni treba iti skozi postopek poenotenja podatkov. Preberite več o uvozu po meri SFTP.

  Za več informacij glejte [Obogatite profile strank s podatki po meri (predogled)](enrichment-SFTP-custom-import.md).
 
- **Obogatite podatke o strankah s podatki o lokaciji družbe HERE Technologies**

  S storitvami za obogatitev podatkov podjetja HERE Technologies lahko z normalizacijo naslova, ekstrakcijo zemljepisne širine in dolžine in še več zagotovite natančnejše razumevanje lokacije svojih strank. Več informacij o obogatitvi v sodelovanju z družbo HERE Technologies.

  Za več informacij glejte [Obogatitev profilov strank v sodelovanju z družbo HERE Technologies](enrichment-here.md).

#### <a name="data-unification"></a>Poenotenje podatkov

- **Prilagodljivost za omogočanje profiliranja podatkov pri izbranih entitetah in poljih iz vašega računa za shranjevanje**

  Navedete lahko, pri katerih podatkovnih entitetah in poljih iz mape Common Data Model v vašem računu za shrambo Azure Data Lake želite omogočiti profiliranje podatkov kot del postopka vnosa podatkov.

  Za več informacij glejte [Vzpostavitev povezave z mapo Common Data Model](connect-common-data-model.md#connect-to-a-common-data-model-folder).

#### <a name="extensibility"></a>Razširljivost

- **Aktivirajte svoje segmente prek storitve Google Ads**

  Izvozite segmente s seznama občinstva storitve Google Ads in uporabite te sezname za oglaševanje v Googlovem iskalniku ter storitvah Google Display Network, YouTube in Gmail. Preberite več o aktiviranju segmentov prek storitve Google Ads.

  Če želite več informacij, glejte razdelek [Povezovalnik za Google Ads](export-google-ads.md).

- **Aktivirajte svoje segmente prek storitve Marketo**

  Izvozite segmente v občinstva Marketo in občinstva uporabite za avtomatizacijo trženja. Preberite več o aktiviranju segmentov prek storitve Marketo. 

  Če želite več informacij, glejte razdelek [Povezovalnik za Marketo](export-marketo.md).

- **Aktivirajte svoje segmente prek storitve DotDigital**

  Izvozite segmente v DotDigital in jih uporabite za tržne namene. Preberite več o aktiviranju segmentov prek storitve DotDigital. 

  Če želite več informacij, glejte razdelek [Povezovalnik za DotDigital](export-dotdigital.md).

#### <a name="predictions"></a>Predvidevanja

- **Predvidevanje izgub glede transakcij**

  Funkcija predvidevanja izgube glede transakcij vam omogoča, da brez pomoči podatkovnega znanstvenika predvidevate verjetnost, da bo stranka prenehala nakupovati izdelke ali storitve.  Z uporabo ocene predvidevanja lahko kombinirate druge informacije o svojih strankah, na primer vrednost strank, da ustvarite segmente strank z visokim tveganjem izgube ali strank z visoko vrednostjo. Ta segment uporabite za neposredno ciljanje strank prek tržnih dejavnosti, podpore strankam in drugih scenarijev, da zmanjšate tveganje izgube.
 
  Konfigurirajte definicijo izgube kot časovnega okna, specifičnega za vaše podjetje, in določite, kdaj se stranke štejejo za izgubljene. Na primer, trgovina z živili bo morda želela stranko šteti za izgubljeno, če slednja v zadnjih 30 dneh ni ničesar kupila.
 
  Ko nadaljujete z ustvarjanjem predvidevanja, vam bomo pojasnili, kateri podatki so potrebni, in vam omogočili preslikavo podatkov o vašem podjetju v polja, potrebna za napovedovanje izgube za vaše stranke. Prav tako lahko nastavite razpored za vnovično usposabljanje modela na podlagi novih informacij v vašem sistemu, da se prilagodi spreminjajočim se poslovnim okoliščinam.
 
  Za več informacij glejte [Predvidevanje izgub glede transakcij (predogled)](predict-transactional-churn.md).

#### <a name="system-administration"></a>Skrbništvo sistema

- **Ponastavitev okolja**

  Ponastavite vse v okolju izbranega primerka, da začnete znova.

  Za več informacij glejte [Ponastavitev obstoječega okolja](manage-environments.md#reset-an-existing-environment).


- **Povežite se s svojim računom za shrambo Azure Data Lake prek glavnega imena storitve**

  Zapišite izhodne podatke v račun za shranjevanje in odčitajte podatke iz njega prek glavnega imena storitve Azure. Obstoječe povezave računa za shranjevanje lahko še naprej uporabljajo ključ računa. Ponujajo tudi možnost nadgradnje za uporabo glavnega imena storitve v nadaljnjih postopkih. Nove povezave bodo temeljile na načinu preverjanja pristnosti glavnega imena storitve za vaš račun za shranjevanje.

  Za več informacij glejte [Povezovanje računa Azure Data Lake Storage Gen2 z glavnim imenom storitve Azure za vpoglede v občinstvo](connect-service-principal.md).

## <a name="october-2020-updates"></a>Posodobitve v oktobru 2020

Posodobitve v oktobru 2020 vključujejo več funkcij, nadgradnje zmogljivosti in popravke napak.

### <a name="new-and-updated-features-in-october-2020"></a>Nove in posodobljene funkcije v oktobru 2020

#### <a name="extensibility"></a>Razširljivost

- **Izvoz v Mailchimp**

Izvozite segmente na obstoječe sezname občinstva v storitvi Mailchimp, da svojim strankam zagotovite prilagojeno e-poštno izkušnjo.

Če želite več informacij, glejte razdelek [Povezovalnik za Mailchimp](export-mailchimp.md).

#### <a name="data-enrichment"></a>Obogatitev podatkov

- **Odstranite podvajanje izvornih zapisov v entiteti Match**

Navedite pravila za odstranjevanje podvajanja za entitete, ki se uporabljajo v postopku ujemanja za prepoznavanje podvojenih zapisov. Združite jih v en zapis in povežite vse izvorne zapise s tem združenim zapisom. Ta zapis, pri katerem je bilo odstranjeno podvajanje, bo nato uporabljen v postopku ujemanja med entitetami.

Za več informacij glejte [Opredelitev odstranjevanja podvajanj za entiteto ujemanja](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="system-administration"></a>Skrbništvo sistema

- **Organizacija: nova možnost osveževanja pri možnosti spajanja**

Do danes, ko zaženete postopek spajanja, je sistem zagnal vse nadaljnje procese, ki so odvisni od spajanja in nadaljnjih procesov. Zdaj lahko potrdite izhodne podatke procesa spajanja (poenotena entiteta stranke), preden ga uporabite pri nadaljnji obdelavi, kot so segmenti ali mere.
Na strani za spajanje lahko zdaj izberete, da zaženete samo korak spajanja in zaženete samo ta postopek. Če želite osvežiti vse nadaljnje procese, lahko izberete zagon postopkov spajanja in nadaljnjih procesov. 

## <a name="september-2020-updates"></a>Posodobitve v septembru 2020

Posodobitve v septembru 2020 vključujejo več funkcij, nadgradnje zmogljivosti in popravke napak.

### <a name="new-and-updated-features-in-september-2020"></a>Nove in posodobljene funkcije v septembru 2020

#### <a name="activities"></a>dejavnosti

- **Inteligentno predvidevanje semantike atributov**

Ta nova funkcija predvideva vrste semantike za vhodne atribute, ki se prenesejo v postopek poenotenja podatkov. Uporablja modele strojnega učenja, ki izboljšajo natančnost in prihranijo čas.

#### <a name="enrichments"></a>Obogatitve

- **Obogatitev z demografskimi podatki družbe Experian**

Obogatitev z demografskimi podatki iz družbe Experian je zdaj na voljo v predogledu. Družba Experian je vodilna v svetu pri kreditnem poročanju o potrošniških in podjetjih ter tržnih storitvah. S [storitvami za obogatitev podatkov družbe Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage) lahko globlje razumete svoje stranke tako, da svoje profile strank obogatite z demografskimi podatki, kot so velikost gospodinjstva, dohodek in drugo.

Če želite uporabljati to funkcijo, morate imeti aktivno naročnino na Experian.

Za več informacij glejte [Obogatitev profilov strank z demografskimi podatki podjetja Experian](enrichment-experian.md)


#### <a name="system-administration"></a>Skrbništvo sistema

- **Podokno s podrobnostmi opravila**

Podokno s podrobnostmi opravila vam omogoča ogled podrobnosti o opravilih, ki jih sistem izvaja. To je priročen način za prepoznavanje težav s konfiguracijo in iskanje rešitev.
Preglejte sporočila o napakah in preverite, kako lahko odpravite morebitne težave.
 
- **Obdelava informacij dodana na dodatne strani**

Ta izboljšava dodaja informacije o stanju vaših entitet na strani **Entitete** in **Stranke**.
 
Poleg tega lahko na obeh straneh najdete podrobnosti o poteku procesov, skupaj s podrobnostmi opravila.

- **Izboljšave na strani stanje sistema**

Izboljšali smo strukturo tabele s podrobnostmi o stanju na **Sistem** > **Stanje** pri pregledu izvozov podatkov.
 
Poleg tega so napake v stolpcu **Podrobnosti** zdaj podrobnejše in izvedljivejše. 
 
- **Preklic vrnitve opravila v prejšnje stanje**

Ko opravilo prekinete, na primer v postopku ujemanja, se vrne v svoje zadnje stanje. Če se je na primer postopek ujemanja včeraj dokončal in ga danes prekličete, se bo vrnil v včerajšnje uspešno stanje.


## <a name="august-2020-updates"></a>Posodobitve v avgustu 2020

Posodobitve v avgustu 2020 vključujejo več funkcij, nadgradnje zmogljivosti in popravke napak.

### <a name="new-and-updated-features-in-august-2020"></a>Nove in posodobljene funkcije v avgustu 2020

#### <a name="data-unification"></a>Poenotenje podatkov

- **Izboljšana izkušnja za stopnjo zemljevida med poenotenjem podatkov**

  Izkušnja s stopnjo zemljevida v postopku poenotenja podatkov vam omogoča, da enostavneje izberete entitete, atribute in definirate semantiko.

  Te spremembe vključujejo:
  
  - manj interakcij, potrebnih za dodajanje entitet in polj
  - Izboljšane možnosti iskanja na strani zemljevida
  - vizualno in enostavno identifikacijo predlagane vrste polja

#### <a name="enrichment"></a>Obogatitev

- **Obogatitev s priljubljenimi interesi na voljo na dodatnih trgih**

  Razpoložljivost obogatitve s priljubljenimi interesi širimo zunaj ZDA na pet dodatnih trgov: Kanada, Avstralija, Združeno kraljestvo, Francija in Nemčija. S to razširitvijo lahko svoje podatke o strankah obogatite z dodatnimi interesi, ki veljajo za te trge. Obogatili bomo tudi profile strank, ki se nahajajo na teh trgih, z uporabo lokalnih lastniških podatkov iz storitve Microsoft Graph.
  Za več informacij glejte [Obogatitev profilov strank s priljubljenimi blagovnimi znamkami in zanimanji](enrichment-microsoft-graph.md)


## <a name="july-2020-updates"></a>Posodobitve za julij 2020

Posodobitve v juliju 2020 vključujejo številne funkcije, nadgradnje zmogljivosti in popravke napak.

### <a name="new-and-updated-features-in-july-2020"></a>Nove in posodobljene funkcije za julij 2020

#### <a name="extensibility"></a>Razširljivost

- **Sprožilec za storitev Power Automate za popoln postopek poenotenja**

  Sprožilce za Power Automate smo podaljšali in vam omogočili, da ustvarite obvestilo ali dejanje, ko je osvežitev postopka poenotenja (preslikava, ujemanje, spajanje) dokončana.    
  Za več informacij glejte [Povezovalnik za Power Automate](export-power-automate.md)

#### <a name="enrichment"></a>Obogatitev

- **Obogatitev priljubljenih blagovnih znamk je na voljo na dodatnih trgih**

  Obogatitev priljubljenih blagovnih znamk širimo na pet dodatnih trgov (poleg ameriškega): kanadski, avstralski, britanski, francoski, nemški in trg Združenega kraljestva. S to razširitvijo lahko obogatite podatke o strankah z lokalnimi blagovnimi znamkami na teh trgih. Obogatili bomo tudi profile strank, ki se nahajajo na teh trgih, z uporabo lokalnih lastniških podatkov iz storitve Microsoft Graph.
  Za več informacij glejte [Obogatitev profilov strank s priljubljenimi blagovnimi znamkami in zanimanji](enrichment-microsoft-graph.md)

## <a name="june-2020-updates"></a>Posodobitve za junij 2020

Posodobitve v juniju 2020 vključujejo številne funkcije, nadgradnje zmogljivosti in popravke napak.

### <a name="new-and-updated-features-in-june-2020"></a>Nove in posodobljene funkcije za julij 2020

#### <a name="enrichment"></a>Obogatitev

- **Obogatitev s podatki podjetja, ki jih zagotavlja družba Leadspace**
  
  Določite polja v poenotenih profilih strank, ki se uporabljajo za iskanje povezanih podatkov podjetja, ki jih zagotavlja družba Leadspace. Po izvedbi postopka obogatitve so profili za prodajo podjetjem obogateni z dodatnimi atributi, vključno z velikostjo podjetja, lokacijo, industrijo in drugo.    
  To sodelovanje vam omogoča, da izboljšate kakovost svojih podatkov s podatki, ki jih zagotavljajo storitve neodvisnih ponudnikov. Za uporabo te obogatitve potrebujete licenco družbe Leadspace, da lahko dostopate do njihovih podatkov podjetja o prodaji podjetjem. Sistem bo to licenco uporabljal za stalno obogatitev vaših podatkov.    
  Za več informacij glejte [Obogatitev profilov podjetij z družbo Leadspace](enrichment-leadspace.md).

- **Stran zvezdišča za obogatitev**

  Vsa razpoložljiva obogatitev podatkov pri ponudnikih za obogatitev, ki jih ponuja prvi in tretji, se konfigurira na istem mestu. Konfiguriranje obogatitve podatkov je brezhibna izkušnja, ki jo lahko upravljate kjer koli.    
  Za več informacij glejte [Obogatitev za profile strank](enrichment-hub.md).

- **Ločena obogatitev priljubljenih blagovnih znamk in zanimanj**

  Priljubljene blagovne znamke in zanimanja sta zdaj na voljo kot dve neodvisni obogatitvi. Ločene obogatitve vam omogočajo, da jih individualno konfigurirate in upravljate, odvisno od poslovnih zahtev ali potreb.    
  Za več informacij glejte [Obogatitev profilov strank s priljubljenimi blagovnimi znamkami in zanimanji](enrichment-microsoft-graph.md).

#### <a name="extensibility"></a>Razširljivost

- **URL-ji, ki jih je mogoče klikniti, za poenotene dejavnosti v dodatku za kartico stranke v Dynamics 365**

  Poenotene dejavnosti v dodatku za kartico stranke zdaj prikazujejo URL-je, ki jih je mogoče klikniti, če so bili ti URL-ji definirani med konfiguracijo dejavnosti.    
  Za več informacij glejte [Dodatek za kartico stranke](customer-card-add-in.md).

- **Priljubljene blagovne znamke in zanimanja, ki so na voljo v dodatku za kartico stranke v Dynamics 365**

  Nov kontrolnik v dodatku za kartice strank v Dynamics 365 vam omogoča, da stikom v aplikacijah za sodelovanje s strankami v Dynamics 365 prikažete obogatitve blagovnih znamk in zanimanj.    
  Za več informacij glejte [Dodatek za kartico stranke](customer-card-add-in.md).

- **Dodatni sprožilci storitve Power Automate**

  Sprožilce za Power Automate smo podaljšali in dodali naslednje sprožilce:
  - Prejem obvestila ali izvedba dejanja, ko se dokonča samodejna polna osvežitev (viri podatkov, poenotenje, segmenti, mere, izvozi)
  - Določite prag za poslovno mero. Na primer: lahko ustvarite obvestilo, ki se pošlje, ko se preseže določen prag. Poleg tega sprožilec zagotovi informacije, ki vam omogočajo, da zgradite bolj zapletene poteke dela v storitvi Power Automate.    
  Za več informacij glejte [Povezovalnik za Power Automate](export-power-automate.md)

- **Izvoz v upravitelja oglasov storitve Facebook**
  
  Ta zmogljivost vam omogoča izvoz segmentov v Upravitelja oglasov za Facebook. Segmenti se izvozijo kot ciljne skupine po meri za uporabo poenotenih profilov strank pri trženjskih akcijah in oglasih Facebook. Ciljne skupine po meri se lahko uporabijo za ustvarjanje oglaševalskih akcij v storitvi Instagram prek upravitelja oglasov storitve Facebook.    
  Za več informacij glejte [Povezovalnik za upravitelja oglasov storitve Facebook](export-facebook.md).

#### <a name="predictions"></a>Predvidevanja

- **Predvidevanje odpovedi naročnin**

  Če sledite vodeni izkušnji, boste lahko ustvarili predvidevanja odpovedi naročnin na območjih naročnin, kot so storitve v oblaku, članstvo strank in ostali sektorji. 

  Funkcija predvidevanja odpovedi naročnin vam omogoča, da predvidite verjetnost, da bo stranka prenehala uporabljati naročniške izdelke ali storitve, ne da bi pri tem sodelovali s podatkovnim analitikom. Z oceno predvidevanja lahko združite druge podatke o svojih strankah, da ustvarite segmente z visokim tveganjem odpovedi. S pomočjo tega segmenta lahko neposredno usmerite stranke pri trženju, podpori strankam in drugih scenarijih, da zmanjšate tveganje izgube za določene stranke ter izboljšate prihodke in zmanjšate stroške.

  Znotraj izkušnje lahko konfigurirate definicijo odpovedi kot časovno okno, ki je značilno za vaše podjetje. Na primer: podjetje, ki se ukvarja s pretakanjem video vsebin, z mesečno naročnino želi vedeti, ali bo stranka naročnino odpovedala po 15 dneh po poteku naročnine.

  Vodili vas bomo skozi predvidevanje in vam povedali, katere podatke potrebujete, omogočili da podatke o podjetju preslikate v polja, zahtevana za predvidevanje odpovedi za vaše stranke. Medtem ko se poslovne informacije spreminjajo, lahko nastavite razpored za prekvalificiranje novih informacij v sistemu, da se prilagodijo spreminjajočim se poslovnim razmeram.    
  Za več informacij glejte [Predvidevanje odpovedi naročnin (predogledna različica)](predict-subscription-churn.md).

#### <a name="segments"></a>Segmenti

- **Poišči podobne stranke**
  
  Poiščite podobne stranke v vaši bazi strank z umetno inteligenco. Model strojnega učenja dvojiške razvrstitve dodeli oceno podobnosti strankam v razširjenem segmentu. Rezultat temelji na podobnosti s strankami v izvornem segmentu. Profili strank se glede na oceno podobnosti dodajo na novo ustvarjen segment.

  Digitalni marketing uporablja model umetne inteligence za modeliranje podobnih ciljnih skupin tako, da z njim poišče stranke, ki so podobne drugemu segmentu vaših strank, in faktorizira dodatne atribute. Izbirate lahko atribute in določite največje število dovoljenih strank v novem segmentu. Model umetne inteligence bo nato izračunal ocene podobnosti za vsako stranko na podlagi izbranih atributov in poiskal stranke, ki imajo višjo povprečno oceno podobnosti. Izbrani segment bo vključeval stranke, ki so podobne strankam v izvirnem segmentu.    
  Če želite več informacij, glejte [Podobne stranke](find-similar-customer-segments.md).

- **Prekrivanje segmentov in diferenciatorji**

  Prekrivanje segmentov vam omogoča, da vidite, koliko strank je skupnih dvema segmentoma (ali več segmentov) in katere stranke so to. Vidite lahko na primer, kako se segment strank, ki veliko porabijo, prekriva s segmentom strank z visokim zadovoljstvom ali kako se segment strank, ki odpovejo naročnino, prekriva s segmentom strank z nizkim zadovoljstvom. Poleg tega lahko analizirate, kako se prekrivanje spreminja na podlagi dodatnega atributa po vaši izbiri.

  Diferenciatorji segmentov razkrivajo, kaj razlikuje en segment od ostalih strank ali drugega segmenta. Vse, kar morate storiti, je določiti segment in sistem bo določil atribute profila in mere za razlikovanje segmenta v obliki razvrščenega seznama diferenciatorjev – od najmočnejšega diferenciatorja do najšibkejšega.    
  Za več informacij glejte [Vpogledi v segmente (predogledna različica)](segment-insights.md).

- **Življenjska doba segmenta**
  
  Določite razpored za aktivacijo ali deaktivacijo segmenta.    
  Za več informacij glejte [Upravljanje obstoječih segmentov](segments.md#manage-existing-segments).

## <a name="may-2020-updates"></a>Posodobitve za maj 2020

Posodobitve v maju 2020 vključujejo številne funkcije, nadgradnje delovanja in popravke napak.

### <a name="new-and-updated-features-in-may-2020"></a>Nove in posodobljene funkcije za maj 2020

#### <a name="data-ingestion"></a>Uvoz podatkov

- **Sprotni uvoz podatkov: pogledi zgodovine**

  Ko uporabljate naš API za uvoz sprotnih posodobitev, si lahko ogledate do 30 dni zbrane zgodovine za te posodobitve. Imate dostop do zbirk vseh uspešnih ali neuspelih klicev API, vključno z njihovimi izidi, izvornim sistemom in drugimi koristnimi metapodatki.    
  Za več informacij glejte [Uvoz podatkov v realnem času](real-time-data-ingestion.md).

- **Sprotni uvoz podatkov: posodobitve profila**

  Ta razširitev sprotnega uvoza podatkov vam omogoča, da v nekaj sekundah opazite spremembe v določenih poljih uporabniškega profila.    
  Poleg funkcionalnosti za dejavnosti v realnem času sistem podpira posodobitve polj profila z manjšo zakasnitvijo. Sprotne posodobitve za polja profilov imajo čas poteka in zato niso primerno nadomestilo za načrtovana osveževanja.    
  Za več informacij glejte [Uvoz podatkov v realnem času](real-time-data-ingestion.md).

#### <a name="extensibility"></a>Razširljivost

- **Posodobljena časovnica in oštevilčevanje strani v dodatku za kartico stranke**

  Časovnica rešitve za dodatek za kartico stranke se ujema s časovnico dejavnosti. Izboljšalo se je oštevilčevanje strani časovnice, zdaj prikazuje do 50 dejavnosti hkrati. Omogoča tudi nalaganje dodatnih dejavnosti na časovnici.    
  Za več informacij glejte [Dodatek za kartico stranke](customer-card-add-in.md).

- **Sprožilec Power Automate za spremembe segmenta**

  Sprožilci za Power Automate določijo, iz česa lahko ustvarite tok. Novo dodani sprožilec vam omogoča, da določite prag za segment. Na primer: lahko ustvarite obvestilo, ki se pošlje, ko se preseže določen prag.    
  Za več informacij glejte [Povezovalnik za Power Automate](export-power-automate.md).

- **Podpora za več strank pri modelih po meri**

  Konfigurirajte delovne tokove za modele po meri s spletno storitvijo drugega najemnika za strojno učenje Azure. Ko ustvarite nov potek dela za modele po meri, se lahko vpišete v najemnika za strojno učenje Azure. Ta sposobnost je dodatek k obstoječi zmožnosti integracije z lastno spletno storitvijo strojnega učenja Azure.    
  Za več informacij glejte [Modeli strojnega učenja po meri](custom-models.md).

#### <a name="segments"></a>Segmenti

- **Avtomatizacija poti entitete**

  Pri ustvarjanju segmenta morajo uporabniki določiti pot entitete. Ta zmožnost predstavlja prvi korak k avtomatizaciji definicije poti entitete, tako da se lahko osredotočite na merila segmentacije, ki jih imate v mislih.    
  Če je entiteta, s katero želite segmentirati svoje stranke, neposredno povezana s poenoteno entiteto stranke, vam ne bo treba več določiti poti entitete. Če pa obstaja več možnih poti entitete, jo morate še vedno določiti ročno.

- **Dejanja na več segmentih**
  
  Uporabniki lahko z enim klikom izberejo več segmentov in izvedejo več dejanj, kot je osvežitev segmentov.    

- **Osveževanje segmentov**

  Uporabniki lahko osvežijo en segment ali izberejo samo segmente, ki jih želijo osvežiti.    

  
- **Izboljšave sestavljenih segmentov**

  Uporabniki lahko ustvarjajo, urejajo in brišejo segmente, ki temeljijo na drugih segmentih. Na primer segment, zgrajen na drugem segmentu, ki je bil zgrajen na tretjem segmentu.    

- **Stran »Seznam segmentov«**

  Nova zasnova strani s segmenti uporablja obliko seznama, ki vam omogoča, da vidite več segmentov hkrati. Za hitro iskanje segmentov je dodano iskalno polje. Uporabniki lahko zdaj izvajajo dejanja, kot so nalaganje ali brisanje več segmentov hkrati. Uvedena je nova izkušnja trenda za hitro prepoznavanje pomembnih sprememb v segmentih.    
  Za več informacij glejte [Ustvarjanje in upravljanje segmentov](segments.md).

#### <a name="system-administration"></a>Skrbništvo sistema

- **Aplikacija Customer Insights na voljo v Microsoft Dynamics 365 Online Government**

  Z več in več kanali za interakcije se podatki o državljanih razpršijo po nešteto sistemih, kar vodi do podatkov v silosih in razdrobljenega pogleda informacij o interakcijah državljanov. Brez popolnega pogleda interakcij vsakega državljana po kanalih se javne uprave ne morejo učinkovito posodobiti. Microsoft je zavezan podpiranju tehnoloških potreb javne uprave, da bi izpolnil pričakovanja državljanov glede doslednih in odzivnih izkušenj.    
  S 1. fazo izdaje za leto 2020 bo Dynamics 365 Customer Insights na voljo za Government Community Cloud (GCC), okolje, ki je zgrajeno za zadovoljevanje večjih potreb vladnih agencij ZDA glede skladnosti. Agencije pridobijo enoten pogled na državljane in uporabljajo predhodno vgrajeno UI za pridobivanje vpogledov, ki izboljšujejo interakcije, pooblaščajo zaposlene in preoblikujejo skupnosti, hkrati pa zmanjšujejo kompleksnost IT in izpolnjujejo standarde ZDA glede skladnosti in varnosti. Dynamics 365 Government izpolnjuje zahtevne pogoje programa FedRAMP (Federal Risk and Authorization Management Program) ZDA, kar zveznim agencijam Združenih držav Amerike omogoča, da izkoristijo prihranke stroškov in strogo varnost rešitve Microsoft Cloud.

## <a name="april-2020-updates"></a>Posodobitve iz aprila 2020

Posodobitve v aprilu 2020 vključujejo številne funkcije, nadgradnje delovanja in popravke napak.

### <a name="new-and-updated-features-in-april-2020"></a>Nove in posodobljene funkcije za april 2020

#### <a name="activities"></a>Dejavnosti

- **Preslikava entitete dejavnosti na običajno vrsto dejavnosti**
  
  Konfiguracija dejavnosti in shranjevanje trenutno temeljita na statični zasnovi, da si jih ogledate v časovnici. Semantični pomen dejavnosti, ki ima potencial za več primerov uporabe v modelih umetne inteligence, trenutno ni v celoti izkoriščen. Načrtujemo, da bo časovnica dejavnosti bolj dinamična, na podlagi vrste dejavnosti in boljšega semantičnega razumevanja dejavnosti. Cilj te funkcije je prepoznati vrsto dejavnosti, kot je opredeljeno v modelu Common Data Model, za katero koli uvoženo dejavnost.
  Za več informacij glejte [Dejavnosti stranke](activities.md).

#### <a name="data-ingestion"></a>Uvoz podatkov

- **Sprotni uvoz podatkov: dejavnosti**
  
  Vnos podatkov v realnem času zagotavlja podatke takoj za porabo, dokler naslednje načrtovano osveževanje ne izvleče teh podatkov iz vira podatkov.    
  Za več informacij glejte [Uvoz podatkov v realnem času](real-time-data-ingestion.md).

- **Izboljšave pri pripravi podatkov**
  
  Preberite več o podatkih, uvoženih v entiteto. S povzetkom podatkov lahko razumete značilnosti kakovosti podatkov, ki vam lahko pomagajo pri ustreznih ukrepih.    
  Če želite več informacij, glejte [Raziskovanje podatkov entitete](entities.md#exploring-a-specific-entitys-data).

- **Uvozite analitične podatke iz storitve Dynamics 365 s storitvijo Common Data Service**
  
  Common Data Service je na voljo kot način za ustvarjanje virov podatkov. Obstoječe stranke Dynamics 365 lahko uvozijo analitične entitete iz storitve Common Data Service v aplikacijo Customer Insights. Posamezen vir podatkov lahko istočasno uporablja isto jezero, upravljano s storitvijo Common Data Service, v okolju Customer Insights.    
  Za več informacij glejte [Povezovanje s podatki v upravljanem jezeru podatkov Common Data Service](connect-common-data-service-lake.md).

#### <a name="extensibility"></a>Razširljivost

- **Izvozi v LiveRamp**

  Aktivirajte svoje podatke v rešitvi LiveRamp®, da povežete več kot 500 platform po digitalnih, družabnih in televizijskih ekosistemih. Uporabite svoje podatke v rešitvi LiveRamp za ciljanje, prekinjanje in prilagajanje oglaševalskih akcij.    
  Za več informacij glejte [Povezovalnik za LiveRamp&reg;](export-liveramp.md).

- **Dodatek za ekipe aplikacije Customer Insights**
  
  Bot ponuja možnosti iskanja za poenotene profile strank. Prikazala se bo kartica z do 15 polji iz pridobljenega profila stranke. Več ujemanj vrne seznam rezultatov, kjer lahko izberete profil.    
  Za več informacij glejte [Bot Teams za aplikacijo Customer Insights](export-teams-bot.md).

#### <a name="measures"></a>Mere

- **Stran »Seznam ukrepov«**
  
  Izboljšave strani z ukrepi vključujejo podporo za dejanja v zvezi s posameznim ukrepom in z več ukrepi hkrati. Poleg tega boste našli polje za iskanje, s katerim boste hitro našli in spremljali ukrepe.    
  Za več informacij glejte [Ustvarjanje in upravljanje segmentov](segments.md).

- **Izboljšave sestavljenih ukrepov**
  
  Uporabniki lahko ustvarjajo, urejajo in brišejo ukrepe, ki temeljijo na drugih ukrepih. Na primer ukrep, zgrajen na drugem ukrepu, ki je bil zgrajen na tretjem ukrepu.

#### <a name="segments"></a>Segmenti

- **Dodaten operator**
  
  Operator v naboru omogoča segmentacijo za stranke glede na več možnih vrednosti nizov. Preden je bil dodan ta operator, ste morali sestaviti take segmente z več pogoji ALI. Operator v naboru omogoča, da to uredite z enim pogojem.    
  Za več informacij glejte [Ustvarjanje in upravljanje segmentov](segments.md).

#### <a name="system-administration"></a>Skrbništvo sistema

- **Kopirajte konfiguracijske nastavitve v novo okolje**
  
  Kopirajte konfiguracijo iz enega okolja v drugo. Med ustvarjanjem novega okolja lahko izberete obstoječe okolje, iz katerega želite kopirati konfiguracijo. Trenutno podpiramo vire podatkov, poenotenje podatkov, odnose, ukrepe in segmente, ki jih je treba kopirati. Poverilnice vira podatkov in dejanski podatki niso kopirani.    
  Za več informacij glejte [Upravljanje okolij](manage-environments.md).
