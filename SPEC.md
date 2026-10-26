# FairHome – špecifikácia požiadaviek

## 1. Problém

Dvojice žijúce v spoločnej domácnosti často nemajú prehľad o pravidelných domácich prácach a o tom, či sú medzi nimi rozdelené spravodlivo.

## 2. Používatelia a roly

Aplikácia je určená dvom partnerom alebo spolubývajúcim, ktorí používajú jedno spoločné Android zariadenie - tablet. Obaja majú rovnaké oprávnenia: môžu upravovať úlohy a označovať ich za splnené. Neexistuje administrátor ani prihlasovanie.

## 3. Funkčné požiadavky MVP

### 3.1 Profily
- **F1.** Pri prvom spustení používateľ zadá mená dvoch členov domácnosti.
- **F2.** Používateľ môže neskôr zmeniť zobrazené mená; história splnených úloh ostane priradená k pôvodným profilom.

### 3.2 Správa úloh
- **F3.** Používateľ môže vytvoriť úlohu s názvom, náročnosťou **1 až 5 bodov**, dátumom prvého vykonania a opakovaním **denne, týždenne alebo mesačne**.
- **F4.** Používateľ môže upraviť alebo odstrániť úlohu. Zmena sa uplatní na budúce výskyty úlohy.
- **F5.** Aplikácia zobrazuje jednotlivé plánované výskyty úloh, ich termíny, priradeného člena domácnosti a stav **čaká / splnená**.

### 3.3 Rozdelenie povinností
- **F6.** Aplikácia automaticky priradí každý nový výskyt úlohy jednému z dvoch členov domácnosti.
- **F7.** Pri prideľovaní sa usiluje o približne rovnaký **súčet bodov plánovaných úloh v danom kalendárnom týždni**. Úlohu dostane osoba s nižším aktuálne prideleným súčtom. Pri rovnosti sa osoby striedajú. Úlohy sa nemusia rozdeliť presne 50 : 50, keďže majú rôznu náročnosť.

### 3.4 Plnenie a prehľad
- **F8.** Používateľ môže označiť naplánovaný výskyt úlohy za splnený; aplikácia uloží dátum a čas dokončenia.
- **F9.** Používateľ môže zrušiť omylom označené splnenie.
- **F10.** Domovská obrazovka zobrazuje úlohy na najbližších sedem dní vrátane nesplnených úloh po termíne a umožňuje filtrovať podľa osoby.

### 3.5 Pripomienky a ukladanie
- **F11.** Aplikácia môže používateľa upozorniť lokálnou notifikáciou na nesplnenú úlohu v deň termínu.
- **F12.** Profily, šablóny úloh, ich výskyty a dokončenia sa uchovávajú lokálne aj po reštarte aplikácie. Aplikácia funguje bez internetového pripojenia.

## 4. Obmedzenia

- Platforma: Android, aplikácia v slovenskom jazyku.
- Presne dva profily na jednom zariadení; bez účtu a synchronizácie.
- Úloha má vždy jedného prideleného vykonávateľa.
- Opakovanie je iba denné, týždenné alebo mesačné.
- Notifikácie závisia od povolení a obmedzení operačného systému.

## 5. Mimo rozsahu prvej verzie (non-goals)

- Synchronizácia medzi telefónmi, cloud a účty
- Viac ako dvaja členovia domácnosti
- Manuálne výmeny a schvaľovanie úloh
- Pokročilé grafy, odmeny a rebríčky
- Nákupné zoznamy, platby, fotografie a GPS


## 6. Otvorené otázky a prijaté rozhodnutia

Tieto rozhodnutia platia pre prvú verziu a možno ich po dohode s vyučujúcim upraviť:

1. **Čo znamená spravodlivo?** Približne vyrovnať body pridelených úloh v rámci kalendárneho týždňa; nejde o meranie skutočne odpracovaného času.
2. **Čo ak úloha nie je hotová v termíne?** Ostane označená ako nesplnená a po termíne; nové opakovanie vznikne podľa harmonogramu nezávisle od nej.
3. **Kedy sa prideľuje opakovaná úloha?** Pri vytvorení konkrétneho plánovaného výskytu, nie pri označení predchádzajúceho výskytu za splnený.
4. **Majú profily heslá?** Nie; predpokladá sa dôvera medzi dvojicou používajúcou spoločné zariadenie.
