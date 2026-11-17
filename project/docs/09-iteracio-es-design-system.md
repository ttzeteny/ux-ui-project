# Iteráció, ellenőrzés, mini design system és átadás – 9. fejezet

**Figma fájl:** https://www.figma.com/design/FuNI5vQfABJU65oCM8jcZR

| Oldal | Tartalom |
|---|---|
| **Finomított prototípus (8. házi)** | Az iterált prototípus (2. iteráció is), új **07 Beállítások** képernyő |
| **Design system (9. házi)** | Variánsos komponensek, használati szabályok, előfordulásszámok |
| **Átadás – 02 Session-összefoglaló** | 5 állapot, annotációk (Dev Mode + számozott), változó- és komponenslista |
| **UI-irányelv** | 8. házi irányelv; a fókusz változó frissült (D7) |

**Prototípus-link (fő út):** https://www.figma.com/proto/FuNI5vQfABJU65oCM8jcZR?node-id=27-1108&starting-point-node-id=27%3A1108

---

## 1. Döntési napló

Bizonyítékcímkék: **[kutatás]** tesztmegfigyelés, **[elv]** szakmai/akadálymentességi elv, **[korlát]**, **[feltételezés]**.

### D1 – A javaslat fő gombjának felirata · 1. iteráció (8. házi) · ellenőrizve
- **Bizonyíték (L1, súlyosság 3) [kutatás]:** 2/3 résztvevő megállt a „Kipróbálom a következő sessionben” gomb előtt („Ez most átír valamit a setupban?”). R3 csak moderátori kérdés után kattintott.
- **Hipotézis:** Ha a gomb felirata a valódi következményt nevezi meg, és alatta kimondjuk, hogy az iRacingben semmi nem változik, akkor a résztvevők habozás és segítség nélkül eljutnak a sikerállapotig, mert a félelem a setup módosulásából fakadt.
- **Módosítás:** a felirat „Fókuszba teszem a következő sessionre” lett, alatta segédszöveg: „Csak az appban jelöljük meg: nem módosít semmit az iRacingben vagy a setupodban.”
- **Elvetett alternatívák:**
  - Megerősítő ablak („Biztosan…?”): riasztási vakságot okoz (7.1 lecke), és plusz lépés.
  - A gomb elhagyása, csak a javaslat szövege: ekkor nincs „mit próbálok ki legközelebb” döntés, és a Fejlődés funkció nem kap bemenetet.
- **Kompromisszum:** hosszabb felirat, a gomb szélesebb lett (a 960 px-es nézetben két sorba törhet).
- **Várt hatás:** 3/3 résztvevő segítség nélkül eljut a 06-os sikerállapotig.
- **Nyitott kérdés:** érti-e a felhasználó, hogy a „fókusz” a következő session után visszajelzést ad (a Fejlődés oldal még nincs prototipizálva)?

### D2 – Ami ingyen megmarad, az a paywallon törzsszövegben szerepel · 1. iteráció · ellenőrizve
- **Bizonyíték (L2, 3) [kutatás]:** R2: „És ha nem fizetek, a kanyarlista is eltűnik?” A megnyugtató információ 12 px-es, halvány segédszöveg volt. [elv] Megtévesztő minták kerülése (3. házi, L2).
- **Hipotézis:** Ha az ingyen megmaradó funkciókat a döntés helyén, törzsszövegben és elsődleges színnel soroljuk fel, akkor a résztvevők helyesen mondják el, mit veszítenek fizetés nélkül, mert eddig nem vették észre az információt.
- **Módosítás:** „Ingyen is megmarad: a kanyarlista, az időveszteség és a fő ok.” Törzs stílus, `szöveg/elsődleges` szín.
- **Elvetett alternatíva:** külön „Ingyenes vs. Prémium” összehasonlító táblázat a paywallon. Ez túl hosszú a döntési ponton; a Fiók és előfizetés oldalra való.
- **Kompromisszum:** a paywall kártya magasabb lett, a próba gomb lejjebb került.
- **Várt hatás:** F3-ban 3/3 helyesen mondja meg, mi marad ingyen.
- **Nyitott kérdés:** csökkenti-e a konverziót, hogy kimondjuk, mi ingyenes? (Csak élesben mérhető.)

### D3 – Az első terhelés napja kiírva · 1. iteráció · ellenőrizve
- **Bizonyíték (L3, 2) [kutatás]:** R3: „akkor most levonja a 2 500-at?”
- **Hipotézis:** Ha a szöveg konkrét napot mond („az első terhelés a 8. napon”), akkor a résztvevők nem hiszik, hogy a próba indításakor fizetnek, mert a „7 napig ingyenes, utána…” mondat értelmezést igényelt.
- **Módosítás:** „7 napig ingyenes, utána 2 500 Ft/hó; az első terhelés a 8. napon. 2 nappal a próba vége előtt e-mailben emlékeztetünk. Bármikor lemondhatod…”
- **Elvetett alternatíva:** a dátum kiírása („december 3-án”). Pontosabb lenne, de a prototípusban nincs valós dátum; élesben ez lesz a cél (lásd a nyitott kérdést).
- **Várt hatás:** F3-ban 3/3 helyesen nevezi meg az első terhelés idejét.
- **Nyitott kérdés:** konkrét dátum vagy relatív nap: melyik érthetőbb? Élesben dátummal.

### D4 – Setup-címke a sessionlistában · 1. és 2. iteráció · részben ellenőrizve
- **Bizonyíték (L4, 2) [kutatás]:** 2/3 nem a listában találta meg a setupot. A 2. körben 1/3-nál (R6) még mindig így volt („azt hittem, ez a fájlnév”).
- **1. iteráció:** „Setup:” előtag, Címke kiemelt stílus (8. házi).
- **2. iteráció, hipotézis:** Ha a lista fölé oszlopfejléc kerül („Pálya és idő · Autó · Legjobb kör · Setup · Eltérés a referenciához”), akkor a setup oszlop szerepe a sor elolvasása nélkül is érthető, mert a fejléc a megszokott táblázatminta (Jakob-törvény).
- **Módosítás:** oszlopfejléc a „Session lista” tetején (01, 01b).
- **Elvetett alternatívák:**
  - Ikon a setup-címke előtt: kétértelmű ikon, felirat nélkül nem segít.
  - Külön „Setup” szűrő: a kérdés nem szűrés, hanem leolvasás.
- **Kompromisszum:** a fejléc egy sorral csökkenti a látható sessionök számát.
- **Várt hatás:** F1-ben 3/3 a listából olvassa ki a setupot, 15 mp alatt.
- **Nyitott kérdés:** **még nincs újratesztelve.** A soron belüli oszlopszélességek még nem fix rácsok, ezért az igazítás hosszú pályanévnél elcsúszhat (fejlesztési feladat: fix oszlopszélesség).

### D5 – A pályatérkép kanyarszámai kattinthatók · 1. iteráció · ellenőrizve
- **Bizonyíték (L5, 2) [kutatás]:** R2: „A térképen szoktam kiválasztani a kanyart, a MoTeC-ben is így megy.” A kattintás zsákutcába vezetett. [elv] A jelzőnek egyeznie kell a viselkedéssel (7.1 lecke).
- **Hipotézis:** Ha a térkép kanyarszámai ugyanoda visznek, mint a lista sorai, akkor a térképpel kezdők sem jutnak zsákutcába, mert a haladók megszokott belépési pontja működik.
- **Módosítás:** térkép → Kanyar részletei; a felirat: „Kattints egy kanyarszámra a részletekhez.”
- **Elvetett alternatíva:** a térkép kereteinek és feliratának levétele (hogy ne látsszon kattinthatónak). Ez a haladók munkamódját nem szolgálná ki.
- **Kompromisszum:** két út vezet ugyanoda; a billentyűzetes elsődleges út a lista marad (átadási annotáció).
- **Várt hatás:** a 2. körben 0 zsákutca az F2 alatt.
- **Nyitott kérdés:** a térkép vagy a lista a gyorsabb belépési pont a haladóknak? (Csak valós térképpel vizsgálható.)

### D6 – Mire vonatkozik az időveszteség? · 2. iteráció · nincs újratesztelve
- **Bizonyíték (2. kör, K1, 2) [kutatás]:** R4: „A −0,31 az most egy körre vonatkozik, vagy az egész sessionre összesen?” Megállt, és bizonytalanul válaszolt; a kanyar és az ok megnevezése sikerült.
- **Hipotézis:** Ha a kanyarlista címe kimondja a viszonyítás alapját („a legjobb köröd a referenciához mérve”), akkor a résztvevők helyesen értelmezik a számot, mert most a mértékegység nem egyértelmű.
- **Módosítás:** a lista címe „Kanyarok időveszteség szerint · a legjobb köröd a referenciához mérve” (02, 04, világos mód, átadás).
- **Elvetett alternatívák:**
  - Minden sorban „/kör” utótag: zajos, és ötször ismétlődik.
  - Átlag a sessionre: más fogalom, nem ugyanazt méri (az átlagot a Fejlődés oldal mutatná).
- **Várt hatás:** a 3. körben 3/3 helyesen mondja meg, mire vonatkozik a szám.
- **Nyitott kérdés:** kell-e választható nézet (legjobb kör vs. átlag)?

### D7 – Semleges fókuszkeret · design system · elv alapján ellenőrizve
- **Bizonyíték [elv]:** a `fókusz` változó (kék/300) és az elsődleges gomb (kék/400) között 1,53:1 volt a kontraszt, így a fókusz nem különül el a gomb színétől. WCAG 2.4.7 (látható fókusz), 2.4.13 (fókusz megjelenése).
- **Hipotézis:** Ha a fókuszkeret semleges, a háttérrel maximálisan kontrasztos szín (sötét módban szürke/50, világosban szürke/900), akkor minden komponensen jól látható lesz.
- **Módosítás:** a `fókusz` változó aliasa változott; a Gomb, a Beviteli mező, a Legördülő szűrő és a Jelölőnégyzet Fókusz variánsa 2 px-es, kívül futó keretet kapott.
- **Elvetett alternatíva:** kék keret 2 px-es hézaggal (offset). Figmában és a natív UI-keretrendszerekben nehezebb következetesen megvalósítani.
- **Ellenőrzés (számolva):** a keret és a háttér között 16,61:1 mindkét módban. A keret és az elsődleges gomb között 2,63:1 (sötét) és 3,24:1 (világos).
- **Nyitott kérdés:** a sötét módban 2,63:1 a gombon a 2.4.13 (AAA) ajánlás alatt van. Billentyűzetes teszttel kell megnézni, hogy zavar-e.

---

## 2. Ellenőrzés: 2. tesztkör (szimulált)

- **Mit ellenőriztem:** D1, D2, D3 és D5 (az 1. iteráció), a 8. házi feladataival (F1–F3) és sikerkritériumaival.
- **Résztvevők:** 3 új, szimulált fő, ugyanazzal a szűrővel. Új résztvevők, hogy ne legyen tanulási hatás.
  - R4: 2 400 iRating, GT3;
  - R5: 3 100 iRating, LMP2, MoTeC-felhasználó;
  - R6: 1 700 iRating, GT4.
- **Környezet:** mint a 8. háziban, a „Finomított prototípus” oldal 1. iterációs állapotával.

### Rövid jegyzetek (M = megfigyelés, I = idézet, É = értelmezés)
- **R4**
  - M: F2 55 mp alatt kész; a gombra habozás nélkül kattintott.
  - I: „Jó, hogy leírja, hogy a játékhoz nem nyúl.”
  - M: a számra rákérdezett.
  - I: „A −0,31 az most egy körre vonatkozik…?”
  - É: a D1 működik; új bizonytalanság a mértékegységről → D6.
- **R5**
  - M: a térképen a „1”-es számra kattintott, és a Les Combes részleteire jutott (nincs zsákutca).
  - M: később a „2”-esre is kattintott, és a „Nem érhető el a prototípusban” képernyőt kapta. Ez a prototípus korlátja (csak Les Combes kidolgozott), nem lelet.
  - M: F3-ban elmondta: „7 nap ingyen, a 8. napon von le, és a kanyarlista ingyen is marad.”
  - É: a D5, a D2 és a D3 működik.
- **R6**
  - M: F1-ben a listában nem a setup-címkét olvasta, megnyitotta az összefoglalót.
  - I: „Azt hittem, a dobozban a fájlneve van.”
  - É: a D4 1. iterációja nem elég → 2. iteráció (oszlopfejléc).
  - M: F2 1:20, F3 helyes.

### Előtte–utána (sikerkritériumonként)
| Sikerkritérium | 1. kör (8. házi) | 2. kör | Változás | Bizonyíték ereje |
|---|---|---|---|---|
| F2: a kanyar és az ok megnevezése 2 percen belül, segítség nélkül | 3 / 3 (1:05, 1:30, 1:40) | 3 / 3 (0:55, 1:10, 1:20) | változatlan (teljesült); az idő csak tájékoztató | gyenge–közepes |
| F2: a sikerállapot elérése segítség nélkül (D1) | 2 / 3 | 3 / 3 | javult | közepes (2 résztvevőnél volt elakadás) |
| F2: zsákutca a fő úton (D5) | 1 alkalom / 3 fő | 0 / 3 | javult | gyenge (1 fő használta a térképet) |
| F3: a díj, az első terhelés és az ingyenes rész helyes elmondása (D2, D3) | 1 / 3 teljesen helyes | 3 / 3 | javult | közepes |
| F1: a setup kiolvasása a listából (D4) | 1 / 3 | 2 / 3 | részben javult, **nyitott** | gyenge |
| A szám értelmezése (új, D6) | – (nem kérdeztük) | 1 / 3 bizonytalan | új lelet | gyenge |

A „3 / 3” megfigyelésszám, nem százalék.

**Következtetés:** a vizsgált (szimulált) 3 résztvevőnél a fő feladat sikerkritériuma teljesült, és a paywall megértése javult. A setup-címke és a szám értelmezése még nyitott; mindkettőhöz van 2. iterációs módosítás, de még nincs újratesztelve.

### Korlátok
- **Szimulált résztvevők** (AI-generált); a valós viselkedés eltérhet.
- **Kis minta** (3 + 3 fő, eltérő emberek): erős jelzés lehet, de nem bizonyíték.
- **Prototípus:** egyetlen kitalált Spa-session, nincs valós .ibt-elemzés, csak Les Combes kidolgozott.
- **Csak asztali, 1280 px, sötét mód;** a világos mód és a 960 px-es nézet nincs tesztelve.
- **Billentyűzetes és képernyőolvasós használat nincs tesztelve** (a D7 csak számolt kontrasztra épül).
- **A 2. iteráció módosításai (D4, D6) nincsenek újratesztelve.**

---

## 3. Mini design system (Figma: „Design system (9. házi)” oldal)

Csak a képernyőkön ténylegesen előforduló elemek. Az előfordulások száma a „Finomított prototípus” oldalon lévő példányok száma.

| Komponens | Tulajdonságok és variánsok | Előfordulás | Hol |
|---|---|---|---|
| **Gomb** | Típus: Elsődleges / Másodlagos / Szöveges link × Állapot: Alap / Rámutatás / Fókusz / Letiltott / Betöltés (a linknél Betöltés nincs) · Felirat (szöveg) | 25 | minden képernyő |
| **Beviteli mező** | Állapot: Alap / Fókusz / Kitöltött / Hiba / Letiltott · Címke, Érték, Hibaüzenet | 1 | 07 Beállítások (telemetria mappa) |
| **Legördülő szűrő** | Állapot: Alap / Rámutatás / Fókusz / Nyitott · Felirat | 6 | 01, 01b szűrők |
| **Jelölőnégyzet** | Állapot: Ki / Be / Fókusz / Letiltott · Felirat | 3 | 01, 01b („Csak elemezhető sessionök”), 07 (értesítés) |
| **Stat kártya** | Címke, Érték | 9 | 02, 04, 02 világos |
| **Session sor** | Állapot: Alap / Rámutatás / Nem elemezhető · 6 szöveges tulajdonság | 9 | 01, 01b |
| **Kanyar sor** | Állapot: Alap / Rámutatás / Kiválasztott · Helyezés, Kanyar, Ok, Veszteség | 15 | 02, 04, 02 világos |
| **Állapotsáv** | Típus: Info / Siker / Figyelmeztetés / Hiba · Cím, Szöveg | 3 (+4 az átadási oldalon) | 01b, 06, 07, átadás |
| **Oldalsó menü** | – | 9 | minden képernyő |
| **Grafikon helyőrző** | Csatorna | 9 | 03, 05, 06 |

- **Elnevezés:** magyar, szerep szerinti nevek; a tulajdonságok mindenhol *Típus* és *Állapot*.
- **Stílusok:** minden komponens a „Téma” színváltozóit, a „Térköz” változókat és a 8 szövegstílust használja.
- **Használati szabályok:** 1–3 mondat minden komponens mellett a Figmában. Ezek a 8. házi leleteire is hivatkoznak (L1, L4, L5).
- **Új a 9. háziban:**
  - Beviteli mező, Legördülő szűrő, Jelölőnégyzet és Stat kártya. A kézzel rajzolt szűrőket és mutatókat példányokra cseréltem; a prototípus-kapcsolatok megmaradtak.
  - Új 07 Beállítások képernyő: itt használt a beviteli mező hibaállapota, valós edge case-ként (a telemetria mappa nem érhető el).
- **Próba (9.5, 9. lépés):** a Gomb összes variánsának lekerekítését 6-ról 8 px-re állítottam. Mind a 25 példány követte, a felülírt feliratok megmaradtak.
- **Tapasztalat:** a meglévő komponensek variánskészletbe vonása (combine as variants) megtartotta a példányokat és a szövegértékeket. Ezért ezeket nem építettem újra, hanem a meglévőket bővítettem.

---

## 4. Átadás (Figma: „Átadás – 02 Session-összefoglaló” oldal)

- **Állapotok:**
  - Normál;
  - Betöltés (előrehaladás és becsült idő, váz sorok, a gomb Betöltés állapotban);
  - Üres (nincs teljes kör);
  - Hiba (az .ibt nem olvasható, automatikus újrapróbálás);
  - Eltérő setup (figyelmeztetés a lista fölött).
- **Annotációk (5 db):** Dev Mode-annotációként a rétegeken, és számozott jelölőkkel a „Normál” állapoton. Tartalmuk: viselkedés, rangsorszabály (legfeljebb 5 kanyar, > 0,03 mp), hosszú név, fókuszsorrend, szerepek és címkék, 200%-os nagyítás.
- **Elfogadási kritérium:** Given–When–Then formában.
- **Lista a változók nevével** (17 változó, automatikusan összegyűjtve a képernyő kötéseiből), a komponensek és a szövegstílusok listájával.

---

## 5. Javasolt következő lépés

**Legnagyobb bizonytalanság:** az, hogy a „fő ok” és a kanyarrangsor **valós .ibt-adatokon** helyes-e, és a versenyzők elfogadják-e. Az eddigi tesztek mind egyetlen kitalált sessionre épültek, ezért ezt nem mutatták meg.

**Lépés: Wizard of Oz-teszt 5 valódi simracerrel, a saját adataikkal.**
1. A résztvevő elküldi egy friss edzés .ibt fájlját.
2. Kézzel (MoTeC / Garage 61) elkészítjük a rangsort és a „fő okot” az app szabályai szerint, és betöltjük a prototípusba.
3. Megkérdezzük: egyezik-e a saját érzésével vagy a saját elemzésével, és mit tenne a javaslattal?

- **Sikerkritérium:** legalább 4/5 résztvevő szerint a rangsor első kanyarja valóban a fő gyengesége, és legalább 3/5 a „fő okot” is helyesnek tartja.
- **Miért ez a sorrend:** nagy a hatása (ha a fő ok rossz, a termék alapígérete dől meg), nagy a bizonytalanság, és olcsó (nem kell hozzá algoritmust fejleszteni). Közben a D4 és a D6 is újratesztelhető.

**Éles validáció a bevezetés után (előre kijelölt mérőszámok):**
- a sessionök hány százalékában nyitják meg a kanyar részleteit;
- a fókuszba tett kanyar ideje javul-e a következő azonos pályás sessionben;
- a 7 napos próbán belüli lemondások aránya, és hogy a lemondók közül hányan használják tovább az ingyenes csomagot (a D2 hatása);
- a „mappa nem található” hibák és a hozzájuk tartozó súgó-megkeresések száma.
