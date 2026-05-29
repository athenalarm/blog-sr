---
title: "Evaluacija magistralne topologije i IP multipleksne arhitekture u fabričkim bezbednosnim sistemima: Tehnički vodič za distributere komercijalnih alarma i integratore sistema"
date: 2026-05-20T09:00:00+08:00
draft: false
type: "posts"
description: "Sveobuhvatni tehnički inženjerski vodič koji evaluira rešenja kao što je RS-485 magistrala u poređenju sa sistemima gde je primenjena IP multipleksna arhitektura u velikim proizvodnim pogonima. Naučite kako da ublažite elektromagnetne smetnje, prevaziđete ograničenja udaljenosti, eliminišete pad napona i izvršite integraciju sa platformama kao što su SCADA sistem i sistem upravljanja zgradom."
keywords: [Factory Security Systems, Bus-Topology Alarm, IP-Multiplexing Architecture, Commercial Alarm Distributors, System Integrators, Industrial Intrusion Alarm, RS-485 Alarm Bus, SIA DC-09, Factory Alarm System Design]
---

Izbor opreme za proizvodni kompleks od 40.000 m² značajno se razlikuje od izbora za lanac maloprodajnih objekata. Fabrička okruženja nameću specifična električna, topološka i operativna ograničenja. Ova ograničenja izlažu svaku slabost u osnovnoj arhitekturi alarmnog sistema. Te slabosti direktno postaju vaša garantna odgovornost, uzrokuju nenaplative izlaske tehničkih ekipa na teren i donose rizik od gubitka ugovora o održavanju.

Ovaj vodič pruža detaljnu inženjersku analizu za distributere komercijalnih alarma, integratore bezbednosnih sistema i menadžere nabavke koji projektuju ili nabavljaju protivprovalnu infrastrukturu za velike industrijske objekte. Tekst analizira realne kompromise između tradicionalnog analognog ožičenja, [topologije adresabilne RS-485 magistrale](https://athenalarm.com/athenalarm-technical-documents/burglar-alarm-knowledge/matters-485-wiring/) i modernih rešenja koja koristi [IP multipleksna arhitektura](https://athenalarm.com/network-alarm-system/network-alarm-monitoring-system-application/). Izbor hardverske strukture direktno određuje ukupne troškove instalacije, kompatibilnost sa centrima za nadgledanje i dugoročne profitne margine održavanja.

Inženjerska praksa pokazuje da u svakoj fabrici većoj od 3.000 m² sa više proizvodnih zona čista analogna topologija ne može zadovoljiti operativne zahteve. Ključni zadatak inženjera nije izbor između magistrale i IP rešenja, već njihovo pravilno slojevito kombinovanje u jedinstven sistem.

---

## Mehanizmi otkaza usled elektromagnetnih smetnji u fabričkim mrežama alarmnih magistrala

Proizvodne hale predstavljaju električno neprijateljska okruženja za prenos osetljivih signala. Uređaji kao što je frekventni regulator, koji pokreću motore transportera i CNC vretena, generišu širokopojasni konduktivni šum u opsegu od 10 kHz do 30 MHz. Ovaj šum se direktno indukuje u neoklopljene signalne kablove koji se pružaju paralelno sa energetskim vodovima. Teška industrijska rasklopna postrojenja stvaraju snažne induktivne tranzijente tokom preklapanja. To može indukovati visoke naponske pikove od 50 do 200 V na susednim niskonaponskim kontrolnim kablovima. Veliki blokovi fluorescentne rasvete takođe stvaraju stalno kapacitivno sprezanje na harmonicima frekvencije od 50/60 Hz.

U realnim uslovima, konduktivne elektromagnetne smetnje koje generiše frekventni regulator uzrokuju fantomske alarmne događaje i korumpirane okvire na magistrali. Tradicionalna analogna zona nema ugrađenu otpornost na šum. Svaki indukovani napon iznad praga detekcije centrale registruje se kao alarmni događaj. Instalateri se redovno suočavaju sa fantomskim alarmima na proizvodnim podovima koji potiču od pokretanja obližnjih mašina, a ne od stvarnog upada. To dovodi do situacije gde tehničari troše sate na rešavanje problema bez rezultata, što narušava odnose sa klijentima i uništava profitne margine.

Diferencijalna signalizacija koju koristi RS-485 magistrala delimično rešava ovaj specifični inženjerski izazov. Prijemnik reaguje isključivo na razliku napona između dva provodnika, pa se zajednički šum indukovan na obe žice poništava. Ovo obezbeđuje 20 do 40 dB potiskivanja šuma, što je sasvim dovoljno za laka industrijska okruženja. Međutim, RS-485 magistrala nije kompletno rešenje za tešku proizvodnju. Visokofrekventni šum i dalje može korumpirati podatke ako je usmeravanje kablova loše izvedeno ili ako dužine linija prilaze električnim limitima protokola.

![Athenalarm AS-9000 dijagram instalacije i ožičenja adresabilne alarmne centrale](https://athenalarm.com/wp-content/uploads/2023/03/Athenalarm-burglar-alarm-manufacturer-scaled.jpg)

Optička mrežna infrastruktura, koja služi kao primarni transportni sloj za sisteme gde je primenjena IP multipleksna arhitektura, potpuno eliminiše konduktivne elektromagnetne smetnje. Optički kablovi nemaju metalne provodnike koji bi delovali kao antene za indukovani šum. Zbog toga su u zonama zavarivanja, visokonaponskih postrojenja i hemijske prerade IP ekspanzioni moduli sa optičkom podlogom jedino pouzdano rešenje koje radi bez lažnih alarma.

---

## Inženjering pada napona za RS-485 instalacije na velikim udaljenostima

Nedovoljno procenjen problem u velikim fabrikama jeste pad napona na alarmnim magistralama. Ovaj problem se najčešće manifestuje u najgorem trenutku, kada svi detektori istovremeno povuku maksimalnu struju u stanju punog alarma.

Inženjerski proračun se oslanja na formulu:

$$V_{\text{drop}} = 2 \times I \times R \times L$$

U ovoj formuli parametri označavaju sledeće vrednosti:
* $I$ = ukupna struja svih čvorova na petlji u stanju mirovanja ili alarma (u amperima)
* $R$ = otpor provodnika po metru dužine ($\Omega/\text{m}$), određen poprečnim presekom žice
* $L$ = fizička udaljenost do najudaljenijeg čvora (u metrima)
* Koeficijent 2 uzima u obzir odlazni i povratni vod provodnika

Za standardni pleteni kabl od 22 AWG otpor iznosi približno $0.054\ \Omega/\text{m}$. Za deblji kabl od 18 AWG ovaj otpor opada na $0.021\ \Omega/\text{m}$.

Primer proračuna obuhvata fabričku magistralu sa 48 adresabilnih čvorova. Svaki čvor troši 12 mA u stanju alarma, a najudaljeniji modul se nalazi na 650 m udaljenosti od centrale.
* Ukupna struja alarma iznosi: $48 \text{ čvorova} \times 0.012\text{ A} = 0.576\text{ A}$
* Upotrebom kabla od 22 AWG dobija se sledeći rezultat: $V_{\text{drop}} = 2 \times 0.576 \times 0.054 \times 650 = 40.435\text{ V}$

Ovaj proračun jasno pokazuje problem jer sistem sa nominalnim naponom od 12 V DC ne može izdržati pad napona od $40.435\text{ V}$. Na terenu se javlja podnapon na udaljenim čvorovima tokom punog strujnog opterećenja u stanju alarma. Čvorovi potpuno gube komunikaciju kada lokalni napon padne ispod 10.5 V DC, što je minimum za transivere koje koristi RS-485 magistrala. Pri naponu od 13.8 V DC na centrali, dozvoljena margina pada iznosi samo 3.3 V pre pojave prvih otkaza uređaja.

Pravilno inženjersko rešenje zahteva sledeće korake:
1. Prelazak na kablove od 18 AWG ili 16 AWG za sve trase duže od 200 metara radi smanjenja pada napona za 60 do 70 procenata.
2. Distribucija tačaka za ubrizgavanje napajanja instalacijom pomoćnih izvora napajanja na sredini ili na krajevima dugačkih petlji.
3. Segmentacija gustih zona u kraće pod-petlje umesto razvlačenja jedne dugačke petlje kroz čitavu fabriku.

---

## Hibridna RS-485 i IP multipleksna arhitektura za fabrike sa više objekata

Arhitektura koja pruža najviše performansi u velikim fabrikama kombinuje lokalne petlje gde se koristi RS-485 magistrala unutar svakog objekta i njihovu agregaciju na IP modulima. Prenos podataka do centralne komandne table obavlja se preko fabričke LAN mreže ili optičke okosnice.

Ovaj pristup uspešno rešava ključne izazove udaljenosti. Svaki lokalni segment gde se primenjuje RS-485 magistrala ostaje unutar granica od 200 do 400 metara, obezbeđujući stabilan rad hardvera. IP sloj omogućava pouzdan prenos podataka na neograničene udaljenosti između udaljenih zgrada. Takođe se drastično proširuje ukupni kapacitet zona jer jedna [adresabilna alarmna centrala](https://athenalarm.com/burglar-alarm/intrusion-alarm-panel/alarm-control-panel/) može primiti stotine zona raspoređenih po čitavom kampusu. Distributeri moraju uzeti u obzir rizik gde pojedinačni prekid kabla potpuno izoluje nizvodne segmente koje koristi RS-485 magistrala u kaskadnim instalacijama. Hibridna konfiguracija rešava ovaj rizik izolacijom kvarova na nivou pojedinačnih objekata.

Prekid kabla ili kratak spoj u objektu C neće ugroziti zone u objektima A, B ili D. IP veza sa ekspanderom svakog objekta ostaje potpuno nezavisna i operativna. Centralni monitoring se integriše preko protokola [SIA DC-09](https://athenalarm.com/) preko IP mreže, pružajući identičan niz podataka bez obzira na udaljenost senzora.

Integratori moraju unapred proveriti mrežne politike fabrike. Sukobi u konfiguraciji zaštitnih zidova mogu blokirati saobraćaj ako IT odeljenje kontroliše deljenu mrežu. Preporučuje se ugovaranje namenskog bezbednosnog VLAN-a ili postavljanje odvojene fizičke mreže kako bi se izbegle promene u IT konfiguracijama.

![Athenalarm mrežni sistem za monitoring alarma](https://athenalarm.com/wp-content/uploads/2022/05/Athenalarm-network-alarm-monitoring-system-1-1024.jpg)

---

## Integracija industrijskih alarma sa SCADA, BMS i VMS platformama

Veliki proizvodni pogoni zahtevaju povezivanje [sisteme protivprovalnih alarma](https://athenalarm.com/burglar-alarm/) sa postojećom operativnom tehnologijom. To uključuje [SCADA sistem](https://athenalarm.com/) za nadzor procesa, [sistem upravljanja zgradom](https://athenalarm.com/) (BMS) za automatizaciju ambijenta i VMS sisteme za upravljanje video nadzorom.

Alarmne centrale koje poseduju [Modbus-TCP](https://athenalarm.com/) interfejs omogućavaju da SCADA sistem čita stanja zona i zdravlje hardvera kao vrednosti registara. SCADA sistem proziva centralu u intervalima od 1 do 5 sekundi. Na osnovu tih podataka mogu se automatski zaustaviti transportne trake ili aktivirati panik rasveta u opasnim zonama tokom incidenta.

Povezivanje sa kamerama se izvodi preko standarda [ONVIF Profile S](https://athenalarm.com/). Kada se aktivira spoljni linijski detektor, alarmni sistem šalje komande kameri da se okrene ka predefinisanoj poziciji i pokrene snimanje visoke rezolucije. Proizvođači poput platforme [Athenalarm](https://athenalarm.com/) nude i izvorni SDK ili REST API za napredne komandne sisteme.

Glavna prepreka na terenu su konflikti u pravilima zaštitnog zida koji blokiraju portove za ONVIF Profile S, Modbus-TCP ili SIA DC-09 komunikaciju. Integratori moraju uračunati dodatno vreme za konfiguraciju mrežnih barijera u saradnji sa fabričkim IT timom.

![Dijagram mrežnog sistema za nadgledanje alarma preko interneta](https://athenalarm.com/wp-content/uploads/2022/05/Network-alarm-monitoring-system-diagram-01-1024.jpg)

---

## Strategija dvostruke redundantnosti za pouzdano fabričko nadgledanje

Korišćenje samo jednog komunikacionog puta u industrijskim sistemima predstavlja kritičnu tačku otkaza celog sistema. Standard za kritične objekte zahteva da se ugradi [dvosmerni komunikacioni modul](https://athenalarm.com/) sa automatskim prebacivanjem na rezervnu vezu.

Primarna putanja koristi fabrički LAN ili WAN za prenos protokola SIA DC-09 do prijemnog centra. Sekundarna putanja se oslanja na 4G LTE mobilnu mrežu preko privatnog APN-a. Sistem šalje kontrolne signale (heartbeat) na obe putanje u intervalima od 30 do 90 sekundi. Ako primarna veza nestane, prijemnik registruje prekid i nastavlja da prima događaje preko LTE mreže.

U praksi, prekid korporativne WAN mreže može poremetiti primarnu putanju nadgledanja tokom perioda kada u fabrici nema osoblja. To se često dešava tokom vikenda ili noćnih održavanja IT opreme. Ćelijski modul tada služi kao neprekidna polisa osiguranja objekta. Zdue gašenja starih 2G i 3G mreža širom sveta, novi projekti moraju koristiti isključivo 4G LTE tehnologiju kako bi izbegli dugoročni gubitak komunikacije.

![Dijagram mrežnog sistema za nadgledanje alarma preko 4G mreže](https://athenalarm.com/wp-content/uploads/2022/05/Network-alarm-monitoring-system-diagram-06-1024.jpg)

---

## Dijagnostička procedura za udaljene RS-485 čvorove koji nisu na mreži

Kada se pojavi otkaz udaljenog uređaja, inženjeri moraju primeniti strukturirani dijagnostički okvir za lociranje uzroka. Procedura počinje merenjem DC napona na terminalima problematičnog čvora pomoću digitalnog multimetra.

* **Korak 1: Izmerite DC napon na terminalu čvora**
  * Zavisno od izmerene vrednosti napona, proces se deli na tri dijagnostičke grane:

* **Grana A: Izmereni napon je ispod 10.5 V DC (Kritičan podnapon)**
  * Napon je ispod minimuma za stabilan rad transivera magistrale usled prevelikog pada napona. Primenite sledeće mere sanacije:
    * Proverite poprečni presek žice i zamenite kablove podstandardnog kvaliteta debljim provodnicima (18/16 AWG).
    * Izmerite ukupnu struju potrošnje svih uređaja na petlji da ne prelazi nominalnu snagu napajanja.
    * Instalirajte [linijski repetitor](https://athenalarm.com/) radi regeneracije digitalnog signala i resetovanja električne udaljenosti.
    * Pregledajte sistem na prisustvo lutajućih struja uzrokovanih nepravilnim uzemljenjem na više mesta.
    * Postavite dodatne module za pomoćno ubrizgavanje napajanja na sredini trase kako biste podigli radni napon.

* **Grana B: Izmereni napon je između 10.5 V i 11.5 V DC (Marginalna zona)**
  * Uređaj radi u nestabilnoj sivoj zoni gde komunikacija može prekidati tokom vršnih opterećenja. Sprovedite slevodeće preventivne korake:
    * Izvršite testiranje pod punim opterećenjem simulacijom stanja alarma kada svi releji i indikatori troše maksimum struje.
    * Zakažite zamenu kablova i prelazak na veći poprečni presek tokom prvog planiranog zastoja proizvodnje.
    * Označite lokaciju za ugradnju modula za spoljno napajanje u narednom planskom ciklusu.

* **Grana C: Izmereni napon je iznad 11.5 V DC (Napon je adekvatan / Problem sa signalom)**
  * Električno napajanje je ispravno, pa je uzrok isključenja korupcija signala ili konflikt podataka. Izvršite duboku dijagnostiku:
    * Izmerite talasnost AC napona osciloskopom da uočite visokofrekventne elektromagnetne smetnje koje indukuje frekventni regulator.
    * Proverite prisustvo i vrednost završnog otpornika od $120\ \Omega$ na krajnjim tačkama gde se završava RS-485 magistrala.
    * Proverite hardverske DIP prekidače da eliminišete konflikte uzrokovane dupliranim adresama uređaja na istoj petlji.
    * Proverite kontinuitet oklopa kabla i osigurajte da je povezan na uzemljenje samo na strani alarmne centrale kako biste sprečili petlje uzemljenja.

---

## Planiranje particija i strategija izolacije magistrale u industrijskim bezbednosnim sistemima

Fabrika se ne može posmatrati kao jedna celina, već kao skup zona sa različitim profilima rizika. Rešenje je raspoređivanje u nezavisne celine gde se primenjuje [particija zona](https://athenalarm.com/) unutar jedne centrale.

Proizvodne hale sa visokim nivoom EMI šuma, skladišta sa noćnom logistikom i administrativne kancelarije rade po različitim rasporedima. Svakom delu se dodeljuje sopstvena particija zona sa posebnim profilom reagovanja i šiframa za naoružavanje. Inženjerska disciplina zahteva izradu mape particija pre polaganja kablova kako bi se izbeglo skupo reprogramiranje sistema nakon instalacije.

Pravilno ožičenje zahteva striktna pravila oklapanja i zaštite. Kabl tipa [oklopljeni upleteni par](https://athenalarm.com/) mora biti uzemljen isključivo na strani centrale. Dvostrano uzemljenje stvara petlje uzemljenja koje propuštaju mrežni šum od 50/60 Hz u signalnu liniju. Takođe, alarmni kablovi moraju biti fizički odvojeni od energetskih vodova najmanje 150 mm.

Ugradnja uređaja kao što je [modul za izolaciju magistrale](https://athenalarm.com/) ključna je za očuvanje integriteta mreže. Kada nastane kratak spoj na spoljnoj liniji ili usled nagnječenja kabla, modul za izolaciju magistrale isključuje oštećeni segment u roku od nekoliko milisekundi. Ostatak sistema nastavlja da komunicira nesmetano, sprečavajući da lokalni kvar paralizuje kompletan bezbednosni sistem fabrike.

---

### Tehnička matrica podataka: Poređenje komunikacionih arhitektura

| Tehnički parametar | Tradicionalne analogne zone | Industrijska RS-485 magistrala | IP multipleksna arhitektura |
| :--- | :--- | :--- | :--- |
| **Maksimalna topološka udaljenost** | ~300 m (limit otpora petlje) | Do 1.200 m po segmentu bez repetitora | Neograničeno preko LAN/optičke okosnice |
| **Maksimalni kapacitet čvorova / zona** | 1 zona po ožičenoj liniji | 128–256 čvorova po petlji (zavisi od centrale) | Na hiljade zona preko IP agregatora |
| **Otpornost na šum (EMI/RFI)** | Loša — podložna indukovanom naponu | Visoka — diferencijalna signalizacija potiskuje šum | Veoma visoka — izolovana Ethernet ili optička veza |
| **Redundantnost u slučaju kvara** | Nema — prekid provodnika gasi zonu | Moduli za izolaciju magistrale izoluju kratak spoj | Dvostruka putanja / Spanning Tree Protocol (STP) |
| **Dijagnostičke mogućnosti** | Binarno: samo otvoreno ili kratak spoj | Prozivanje čvorova: adresa, status, tamper, napajanje | Telemetrija paketa, IP ping u realnom vremenu, heartbeat |
| **Vreme puštanja u rad (fabrika sa 200 zona)** | Visoko — pojedinačno terminisanje i označavanje | Umereno — adresiranje magistrale i verifikacija signala | Nisko do umereno — IP konfiguracija smanjuje servisiranje |
| **Ranjivost na lažne alarme usled EMI** | Veoma visoka | Umerena (zahteva disciplinu oklapanja i uzemljenja) | Niska (optički segmenti su imuni na smetnje) |
| **Ukupni troškovi vlasništva (TCO) za 10 godina** | Visoki — zamena opreme pri svakom proširenju | Srednji — modularno proširenje u okviru magistrale | Niski — softversko adresiranje bez novih kablova |

---

### Tehnički FAQ za menadžere nabavke industrijskih alarma

#### Q1: Zašto se hibridna RS-485 i IP arhitektura preferira u velikim fabrikama?
Hibridna arhitektura eliminiše ograničenja udaljenosti i izoluje kvarove među zgradama. To se postiže jer lokalna RS-485 magistrala održava determinističku komunikaciju na terenu, dok IP agregacija uklanja dugačke linije kablova. Time se osigurava da prekid kabla u jednom objektu ne ugrozi ostatak sistema, omogućavajući skalabilnost na celom fabričkom kampusu.

#### Q2: Kako industrijske elektromagnetne smetnje utiču na pouzdanost alarmnog sistema?
Elektromagnetne smetnje (EMI) uzrokuju lažne alarme i korupciju podataka destabilizacijom analognih petlji i magistrala. Industrijski izvori poput uređaja kao što je frekventni regulator indukuju naponske pikove i šum na neoklopljenim kablovima. Pravilno uzemljenje, oklopljeni upleteni par i segmentacija su kritični za neutralizaciju ovih smetnji i sprečavanje lažnih okidanja zona.

#### Q3: Šta uzrokuje da RS-485 čvorovi odu van mreže u velikim fabričkim instalacijama?
Prekomerni pad napona je primarni uzrok prestanka rada udaljenih čvorova na terenu. Dugačke kablovske trase u kombinaciji sa nedovoljnim poprečnim presekom provodnika i visokom ukupnom strujom detektora tokom punog opterećenja u stanju alarma smanjuju napon ispod kritičnih 10.5 V DC. Ovo onemogućava rad primopredajnika na magistrali.

#### Q4: Zašto je SIA DC-09 protokol preferiran u odnosu na Contact ID u industrijskom nadzoru?
Protokol SIA DC-09 omogućava šifrovani IP prenos visoke propusne moći i brzu dostavu paketa bez zagušenja svojstvenih za stariji Contact ID. Podržava prenos tekstualnih opisa zona, potvrdu o prijemu na nivou protokola i naprednu dvostruku redundantnost (IP/LTE). To je od ključnog značaja za upravljanje stotinama istovremenih događaja u industrijskim objektima.

---

### Inženjerska referenca: Brzi pregled entiteta i protokola

| Termin | Kategorija | Definicija |
| :--- | :--- | :--- |
| **RS-485** | Fizički standard magistrale | Diferencijalni serijski protokol sa dve žice, maks. 1.200 m na 100 kbps, koristi se kao primarna terenska magistrala |
| **SIA DC-09** | Protokol za dojavu alarma | IP-nativni protokol za prenos alarma sa AES-256 šifrovanjem i potvrdom dostave; menja stariji DTMF Contact ID |
| **Contact ID** | Nasleđeni alarmni protokol | DTMF-bazirana dojava alarma preko PSTN telefonskih linija; široko podržan ali propusno ograničen i nešifrovan |
| **Modul za izolaciju magistrale** | Zaštitni hardver | In-line RS-485 uređaj koji elektronski isključuje neispravne segmente magistrale radi izolacije kratkog spoja |
| **Linijski repetitor** | Regeneracija signala | Uređaj koji pojačava i sinhronizuje RS-485 signale radi produženja magistralnih linija preko električnog limita od 1.200 m |
| **EOLR** | Nadzor zone | Krajnji otpornik linije (End-of-Line Resistor); postavlja se na kraj petlje zone radi neprekidnog nadzora kontinuiteta |
| **ONVIF Profile S** | Standard za integraciju kamera | Otvoreni standard koji omogućava alarmnim centralama da kontrolišu PTZ kamere i pokreću snimanje preko TCP/IP komandi |
| **Modbus-TCP** | Industrijski protokol integracije | Ekstenzija Modbus protokola bazirana na Ethernetu; omogućava čitanje podataka o zonama od strane SCADA i BMS platformi |
| **Dvosmerni komunikacioni modul** | Hardver za redundantnost | Komunikacioni modul sa istovremenom primarnom IP i sekundarnom celularnom dojavom, uz automatsko prebacivanje staze |
| **VFD** | Izvor EMI šuma | Frekventni regulator (Variable Frequency Drive); kontroler brzine motora koji generiše širokopojasni elektro šum |
| **TCO** | Poslovna metrika | Ukupni troškovi vlasništva (Total Cost of Ownership); 10-godišnja analiza troškova kapitala, instalacije, servisa i zamene |
| **Privatni APN** | Mobilna konfiguracija | Privatno ime pristupne tačke (Access Point Name); namensko rutiranje mobilnih podataka koje izoluje alarmni saobraćaj |

---

[Athenalarm](https://athenalarm.com/) je profesionalni proizvođač protivprovalnih alarma i dobavljač komercijalnih bezbednosnih sistema. Kompanija obezbeđuje adresabilne alarmne centrale, infrastrukturu za mrežni monitoring alarma i OEM/ODM razvojne usluge za globalne distributere alarma, integratore sistema i operatore centara za nadgledanje. Tehničke specifikacije i uputstva za instalaciju dostupni su preko [Athenalarm portal tehničke podrške](https://athenalarm.com/athenalarm-technical-documents/technical-support/).
