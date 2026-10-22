# FairHome – správa domácich povinností

## 1. Aký problém riešim?

Nerovnomerné rozdelenie a nedostatočný prehľad o pravidelných domácich povinnostiach medzi dvoma ľuďmi žijúcimi v spoločnej domácnosti.

## 2. Kto sú moji používatelia?

Aplikácia je určená pre dvojice zdieľajúce jednu domácnosť, ktorí chcú mať prehľad o upratovaní a spravodlivo si rozdeliť povinnosti. Obaja používatelia budú mať vlastný profil v aplikácii na jednom zariadení.

## 3. Ako chcem problém vyriešiť? (MVP)

Vytvorím Android aplikáciu, ktorá umožní plánovať a evidovať domáce práce a automaticky ich rozdeľovať medzi dvoch používateľov.

Základné funkcie MVP:

- Vytvorenie dvoch lokálnych používateľských profilov.
- Pridávanie, úprava a mazanie domácich úloh (napr. vysávanie, upratovanie kuchyne alebo kúpeľne, varenie, vynášanie smetí, umývanie okien, atď.).
- Nastavenie opakovania úloh (denne, týždenne alebo mesačne).
- Priradenie náročnosti úlohe pomocou bodov.
- Automatické rozdelenie úloh medzi používateľov s cieľom približne vyrovnať súčet bodov za pridelené úlohy.
- Zobrazenie aktuálnych úloh, termínov a osoby zodpovednej za ich vykonanie.
- Označenie úlohy ako splnenej a evidencia jej dokončenia.
- Lokálne notifikácie pripomínajúce naplánované úlohy.

Aplikácia bude fungovať na jednom Android zariadení bez potreby internetu.

## 4. Čo nebude súčasťou MVP (non-goals) a prečo?

- **Registrácia a prihlasovanie:** Aplikácia bude mať iba dva lokálne profily, preto používateľské účty nie sú potrebné.
- **Synchronizácia medzi telefónmi a cloudový backend:** Projekt bude určený na používanie na jednom zariadení.
- **Podpora viac ako dvoch používateľov:** Prvá verzia bude zameraná na dvojčlenné domácnosti, aby bolo rozdeľovanie úloh jednoduchšie.
- **Pokročilé štatistiky a grafy:** Základný prehľad úloh bude pre prvú verziu postačujúci.
- **Nákupné zoznamy a evidencia výdavkov:** Tieto funkcie nesúvisia s hlavným cieľom aplikácie.

## 5. Aké technológie potrebujem?

- **Android Studio:** Vývojové prostredie na tvorbu a testovanie aplikácie.
- **Kotlin:** Programovací jazyk pre Android.
- **Jetpack Compose:** Tvorba používateľského rozhrania.
- **Room Database:** Lokálne ukladanie profilov, úloh a ich histórie.
- **ViewModel (MVVM):** Oddelenie logiky aplikácie od používateľského rozhrania.
- **Android Notifications:** Lokálne upozornenia na naplánované úlohy.
- **Git a GitHub:** Verzionovanie a uchovávanie zdrojového kódu.


