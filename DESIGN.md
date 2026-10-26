# FairHome – technický návrh (DESIGN)

## 1. Základný koncept

FairHome bude mobilná aplikácia pre Android, ktorá pomôže dvom ľuďom v jednej domácnosti plánovať a spravodlivo rozdeľovať domáce práce. Bude fungovať offline na jednom zariadení, bez účtov a synchronizácie. Tento dokument opisuje spôsob realizácie požiadaviek.

## 2. Použité technológie

| Technológia | Využitie |
| --- | --- |
| Android Studio | Vývoj a testovanie aplikácie |
| Kotlin | Programovací jazyk |
| Jetpack Compose | Tvorba obrazoviek a formulárov |
| Room Database | Lokálne ukladanie úloh, profilov a histórie |
| ViewModel (MVVM) | Oddelenie používateľského rozhrania od logiky |
| Android Notifications + WorkManager | Približné pripomienky nesplnených úloh |
| Git a GitHub | Verzionovanie projektu |

Internetové pripojenie, GPS, fotoaparát ani ďalšie senzory nebudú potrebné.

## 3. Architektúra aplikácie

Použije sa jednoduchá architektúra **MVVM**:

- **View (Jetpack Compose):** Zobrazuje zoznam úloh, formuláre a prehľady; prijíma vstupy používateľa.
- **ViewModel:** Spracúva akcie používateľa a zabezpečuje logiku plánovania a prideľovania úloh.
- **Model (Room Database):** Uchováva profily, úlohy a informácie o ich dokončení.

Obrazovky budú získavať údaje cez ViewModel, nie priamo z databázy.

## 4. Ukladané údaje

Aplikácia bude ukladať tri základné druhy údajov:

1. **Používateľ:** identifikátor a meno jedného z dvoch členov domácnosti.
2. **Úloha:** názov, bodová náročnosť (1–5), prvý termín a opakovanie (denne, týždenne alebo mesačne).
3. **Naplánované vykonanie úlohy:** konkrétny termín, pridelený používateľ, stav splnenia a prípadný čas dokončenia.

Oddelenie úlohy od jej jednotlivých vykonaní umožní evidovať históriu a zároveň plánovať ďalšie termíny. Údaje zostanú uložené aj po zatvorení aplikácie. Pri úprave alebo odstránení opakujúcej sa úlohy sa zachovajú už dokončené záznamy.

## 5. Obrazovky aplikácie

- **Úvodné nastavenie:** zadanie mien dvoch používateľov pri prvom spustení.
- **Hlavná obrazovka:** zoznam najbližších a omeškaných úloh, termíny, pridelené osoby, označenie splnenia a filtrovanie podľa osoby.
- **Správa úloh:** vytvorenie, úprava a odstránenie úlohy vrátane nastavenia bodov a opakovania.
- **Prehľad:** súčet pridelených bodov pre oboch používateľov v aktuálnom týždni a história splnených úloh.
- **Nastavenia:** zmena mien a zapnutie alebo vypnutie pripomienok.

## 6. Plánovanie a spravodlivé rozdeľovanie

Každá domáca práca bude mať náročnosť od **1 do 5 bodov**. Pri vytvorení konkrétneho termínu aplikácia spočíta body už pridelených úloh v danom kalendárnom týždni (pondelok až nedeľa):

1. Novú úlohu pridelí osobe, ktorá má zatiaľ menej pridelených bodov.
2. Ak majú obe osoby rovnaký počet bodov, bude ich pri takýchto prípadoch striedať.
3. Už pridelené úlohy sa pri pridaní ďalšej úlohy automaticky nepresúvajú.


Pri dennom, týždennom alebo mesačnom opakovaní bude aplikácia vytvárať ďalšie termíny. Ak zostane predchádzajúci termín nesplnený, zobrazí sa ako omeškaný a ďalšie opakovanie vznikne nezávisle od neho. Ak pri mesačnom opakovaní neexistuje rovnaký deň, použije sa posledný deň daného mesiaca.

## 7. Notifikácie

Aplikácia bude môcť cez systém Android zobrazovať **lokálne pripomienky** nesplnených úloh v deň ich termínu. Presný čas doručenia nebude garantovaný. Ak používateľ notifikácie nepovolí, ostatné funkcie aplikácie budú fungovať ďalej.

## 8. Rozsah prvej verzie

Prvá verzia bude podporovať iba **dva profily na jednom Android zariadení**. Nebude obsahovať prihlasovanie, cloud, synchronizáciu medzi telefónmi, pokročilé grafy ani systém odmien. Tieto funkcie nie sú potrebné na overenie hlavného cieľa: plánovania a férového rozdeľovania domácich povinností.
