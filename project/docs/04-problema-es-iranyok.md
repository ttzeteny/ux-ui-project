# Probléma és irányok – 4. fejezet (problémadefiniálás és lehetőségkeresés)

> A bizonyítékok a 2. házi kutatására (insightok, affinity-csoportok A–G, `R1-1` típusú cetlik) és a 3. házi auditjára (L1–L6) hivatkoznak. A 2. házi interjúi szintetikusak (AI-generált, oktatói engedéllyel), ezért a „bizonyíték” itt munkahipotézist jelent.
> **Jelölés:** 🟧 = feltevés (még ellenőrizni kell), 📎 = bizonyíték (kutatás vagy audit).

## 1. Projektbrief

| Elem | Tartalom | Forrás |
|---|---|---|
| **Problémakör** | Session utáni telemetria-elemzés iRacingben, natív desktop alkalmazással | brief |
| **Célfelhasználó** | Máté, a középhaladó road-versenyző (2. házi persona): edzés vagy verseny után, fáradtan, kevés idővel elemez. Ismeri a fogalmakat, de az adatolvasás nem rutin neki. | 📎 persona |
| **Elsődleges feladat** | Egy session után megtalálni azt az 1–2 kanyart, ahol a legtöbb időt veszíti, megérteni az okát, és egy kipróbálható teendővel visszaülni | 📎 Insight 1, 2 |
| **Jelenlegi helyzet** | Csatornaközpontú grafikonok (Garage 61, MoTeC i2). Kerülőutak: YouTube és Discord. Sokan feladják az elemzést. | 📎 A, B csoport |
| **Szervezeti cél** | Freemium → havi előfizetés. A felhasználó minden session után térjen vissza. | brief |
| **Korlátok** | Csak iRacing és `.ibt`. Natív desktop (Windows/macOS). Automatikus mappafigyelés (`Documents\iRacing\telemetry`). A felvételt a versenyzőnek kell bekapcsolnia. Egyszerre csak kevés, releváns adat jelenhet meg (kognitív terhelés). Az ingyenes verziónak is hasznosnak kell lennie. | brief, 📎 F csoport |
| **Kutatási kérdések** | Felismerhetők-e automatikusan a kanyarhatárok és a kanyarnevek pályánként? Mennyire bíznak a versenyzők egy gépi javaslatban egy coach-csal szemben? Hol legyen a free és a pro határa? | 🟧 |
| **Sikerkritérium** | Egy új session után a felhasználó 2 percen belül, segítség nélkül megnevezi a legnagyobb időveszteségű kanyart és az okát (5 résztvevőből legalább 4). | 1. házi |
| **Benne van (hatókör)** | A session köreinek listája; a **körhöz tartozó setup tárolása és megjelenítése** (melyik setuppal ment a kör, setup-eltérés jelzése összehasonlításnál); kanyarszintű időveszteség; kanyaronkénti javaslat; referenciakör kiválasztása. | 📎 C csoport (R3-4, R4-4) |
| **Kizárások** | A **setup elemzése és ajánlása** (melyik beállítás miért jobb); más szimulátorok; élő, pálya közbeni overlay; csapat- és ligamegosztás; coaching-piactér; mobilalkalmazás; saját fizetési rendszer (külső szolgáltatót használunk). | döntés |

**Miért marad benne a setup tárolása?** A kutatásban az derült ki, hogy egy kör csak azonos (vagy ismert) setuppal összevetve tanulságos (R3-4, R4-4). Ha a versenyző nem látja, melyik setuppal ment a kör, rossz következtetést vonhat le. Ezért a setup **azonosítása és megjelenítése** a fő feladat része. Az, hogy a setupot elemezzük vagy javaslatot adjunk rá, külön, nagy szakértelmet igénylő termékterület, és a hatókörön kívül esik.

## 2. Érintettek

| Érintett | Cél / érdek | Hatás a projektre | Nyitott kérdés |
|---|---|---|---|
| **Középhaladó versenyző** (Máté, elsődleges szereplő) | Gyorsan megtalálni, hol veszít időt, és mit próbáljon ki | A fő feladat; ő dönt az előfizetésről | Mennyire bízik meg egy gépi javaslatban? 🟧 |
| **Haladó és ligaversenyző** (másodlagos szereplő, R3) | Részletes adat, azonos setupú körök összevetése | Ha leegyszerűsítjük, elveszítjük | Elég-e neki egy „részletek” nézet a kanyarlista mögött? |
| **Coach** | A tanítványa adatainak gyors értelmezése | Ajánlhatja vagy lebeszélheti a tanítványait | Kell-e export vagy megosztás (most kizárás)? |
| **iRacing** (adatforrás, platform) | Szabályos adathasználat | Az `.ibt` formátum és a felvétel működése rajta múlik | Mennyire stabil a formátum, és mit enged a felhasználási feltétel? 🟧 |
| **Saját termékcsapat, üzlet (SaaS)** | Előfizetők szerzése és megtartása | Dönt a funkciókról és a free/pro határról | Mi legyen ingyenes, és mi prémium? |
| **Fizetési szolgáltató** | Szabályos, biztonságos előfizetés | Technikai korlát (próbaidő, emlékeztető, lemondás) | Megoldható-e a próbaidő végéről szóló emlékeztető? (3. házi, L2) |
| **Simracing-közösség** (Discord, YouTube-oktatók) | Tudásmegosztás | Ma ők a kerülőút; véleményük hat a hírnévre | — |

**Hatás–érdekeltség rács**
- **Szorosan bevonni** (nagy hatás, nagy érdekeltség): középhaladó versenyző, saját termékcsapat
- **Elégedetten tartani** (nagy hatás, kis érdekeltség): iRacing, fizetési szolgáltató
- **Tájékoztatni** (kis hatás, nagy érdekeltség): haladó és ligaversenyző, coach
- **Figyelni** (kis hatás, kis érdekeltség): simracing-közösség

## 3. User storyk és elfogadási feltételek

**US1 (fő):** *Középhaladó iRacing-versenyzőként szeretném egy session után látni, melyik kanyarban vesztettem a legtöbb időt és miért, hogy a következő sessionben egy konkrét dolgot kipróbálhassak.*
- **Adott**, hogy a session `.ibt` fájlja megjelent a telemetria mappában; **amikor** a versenyző megnyitja a sessiont; **akkor** a kanyarokat névvel és a referenciakörhöz mért időveszteség szerint rangsorolva látja.
- **Adott**, hogy kiválasztott egy kanyart; **amikor** megnyitja a részleteit; **akkor** látja a veszteség fő okát (például korábbi fékpont, alacsonyabb minimumsebesség) és egy kipróbálható javaslatot.

**US2 (setup):** *Versenyzőként szeretném látni, melyik setuppal mentem az adott kört, hogy csak összehasonlítható körökből vonjak le következtetést.*
- **Adott**, hogy két kört hasonlítok össze; **amikor** a két kör setupja eltér; **akkor** a rendszer ezt az összehasonlítás előtt jelzi, és megmutatja mindkét setup nevét.

## 4. Problémaállítás

> **A középhaladó iRacing-versenyző problémája az, hogy a nyers telemetriából nem derül ki, melyik kanyarban és miért veszít időt, ami miatt feladja az elemzést vagy rossz helyen keres javulást, és lassan fejlődik.**

- 📎 Insight 1: „Kanyarban gondolkodnak, az eszköz csatornákban beszél” (A csoport).
- 📎 Insight 2: „Nem adatot keresnek, hanem kipróbálható teendőt” (B csoport).
- Ellenőrzés: nincs benne megoldás (sem „app”, sem „kanyarlista”), egy feladatot fed le (session utáni elemzés), és nem zár ki jó megoldásokat.

## 5. HMW-kérdések

| # | HMW | Technika | Tovább? |
|---|---|---|---|
| H1 | Hogyan tudnánk elérni, hogy a versenyző a kanyarból induljon ki, ne a csatornákból? | az akadály megszüntetése | ✅ |
| H2 | Hogyan tudnánk az adatból egy következő sessionben kipróbálható teendőt csinálni? | a következmény enyhítése | ✅ |
| H3 | Hogyan tudnánk segíteni, hogy összehasonlítható körrel mérje magát (azonos autó, ismert setup)? | az akadály megszüntetése | ✅ |
| H4 | Hogyan tudnánk elérni, hogy ne neki kelljen keresnie, hanem a session végén az elemzés találja meg őt? | a helyzet megfordítása | ✅ |
| H5 | Hogyan tudnánk biztosítani, hogy a fontos kör adata ne vesszen el? | a következmény enyhítése | – (F csoport, kisebb súly) |

## 6. Ötletek (8 perces kör, értékelés nélkül)

| # | Ötlet | HMW |
|---|---|---|
| Ö1 | Rangsorolt kanyarlista névvel és időveszteséggel, ez az első nézet | H1 |
| Ö2 | Pályatérkép-hőtérkép: a kanyarok a veszteség szerint színezve | H1 |
| Ö3 | „Fókuszkanyar” nézet: egyetlen kanyar, 3 csatornával (fék, gáz, sebesség) | H1 |
| Ö4 | Kanyaronként egy szabályalapú javaslat („a referencia 12 m-rel később fékez”) | H2 |
| Ö5 | Edzésterv: 1 fókuszkanyar és egy cél a következő sessionre, utána visszamérés | H2 |
| Ö6 | Hangos tipp vezetés közben, a kanyar előtt | H2 |
| Ö7 | Ajánlott referenciakör: azonos autó, setup-címke, ~0,5–1 mp-cel gyorsabb | H3 |
| Ö8 | Setup-címke minden körön és eltérés-jelzés összehasonlításnál | H3 |
| Ö9 | A saját elméleti legjobb kör (szektorokból összerakva) mint referencia | H3 |
| Ö10 | Asztali értesítés a session végén: „3 kanyar, 0,8 mp – nézd meg” | H4 |
| Ö11 | Heti összefoglaló e-mail a fejlődésről | H4 |
| Ö12 | Figyelmeztetés, ha az iRacing fut, de a felvétel nincs bekapcsolva | H5 |

**Szavazás (5 pont):** Ö1 ●●, Ö4 ●●, Ö7 ●

## 7. Hatás–kivitelezhetőség mátrix

| Ötlet | Hatás | Kivitelezhetőség | 📎 Bizonyíték a hatásra | 🟧 Feltevés a kivitelezhetőségről |
|---|---|---|---|---|
| Ö1 Kanyarlista | Nagy | Könnyű | Insight 1, A csoport (3/5), journey 4. lépés (mélypont) | A kanyarhatárok pályánként egy kanyartáblával felismerhetők |
| Ö3 Fókuszkanyar | Nagy | Könnyű | Insight 1 következménye | A 3 csatorna elég a fő okok megmutatásához |
| Ö8 Setup-címke | Közepes | Könnyű | C csoport (R3-4, R4-4) | Az `.ibt` session-adataiban benne van a setup azonosítója |
| Ö4 Javaslat | Nagy | Közepes | Insight 2, B csoport, R2-5 | Szabályalapú összevetéssel (fékpont, minimumsebesség, gázra lépés) gépi tanulás nélkül is elég jó javaslat születik |
| Ö5 Edzésterv | Nagy | Közepes | Insight 2, sikerkritérium | A versenyzők a következő session után visszajönnek |
| Ö7 Ajánlott referencia | Nagy | Nehéz | C csoport (R1-5, R4-4) | Kell hozzá egy közösségi kör-adatbázis; saját vagy csapattárs-körökkel könnyebb |
| Ö2 Hőtérkép | Közepes | Közepes | R1-4 (térképen keresi a kanyart) | A pályatérkép a telemetria pozícióadataiból kirajzolható |
| Ö10 Értesítés | Közepes | Könnyű | E csoport (vegyes elemzési idő) | Az értesítés nem zavaró |
| Ö9 Elméleti legjobb | Kicsi | Könnyű | R5-4 | Nem ad külső mércét |
| Ö11 Heti e-mail | Kicsi | Könnyű | Nincs bizonyíték | Teljes egészében feltevés |
| Ö12 Felvétel-figyelmeztetés | Közepes | Nehéz | F csoport (R2-4, R5-1) | A futó iRacing és a felvétel állapota kiolvasható |
| Ö6 Hangos tipp | Kicsi a hatókörben | Nehéz | – | Élő overlay = **kizárás** |

**A négy negyed:**
- **Elsőként** (nagy hatás, könnyű): Ö1, Ö3, Ö8
- **Vizsgálni** (nagy hatás, nehéz): Ö4, Ö5, Ö7, Ö12
- **Ha marad idő** (kis hatás, könnyű): Ö10, Ö9, Ö11, Ö2
- **Elvetni vagy később** (kis hatás, nehéz): Ö6

## 8. A kiválasztott irány

**Kanyarközpontú session-összefoglaló:** rangsorolt kanyarlista (Ö1) → egy kanyar részletei 3 csatornával (Ö3) → kanyaronként egy kipróbálható javaslat (Ö4). Minden kör setup-címkét kap, és az összehasonlítás jelzi az eltérést (Ö8).

**Indoklás:** Ez az irány közvetlenül a journey legmélyebb pontjára (a hiba keresése) és a két legerősebb insightra válaszol: a versenyző kanyarban gondolkodik, és teendőt keres, nem adatot. A kanyarlista és a setup-címke könnyen kivitelezhető, a javaslat (Ö4) pedig a legnagyobb értékű, de bizonytalan elem, ezért ezt kell elsőként prototipizálni és tesztelni. Most elhagyjuk az élő hangos tippet (kizárás), a heti e-mailt (nincs rá bizonyíték) és a közösségi referencia-adatbázist. Referenciának egyelőre a saját legjobb kör és a kézzel választott kör marad. **Bizonytalan:** felismerhetők-e megbízhatóan a kanyarhatárok, mennyire bíznak meg a felhasználók egy szabályalapú javaslatban, és hol legyen a freemium-határ. Feltevés: a kanyarlista ingyenes, a javaslat és a referenciaajánlás a prémium része.

## 9. Ellenőrizendő feltevések
1. 🟧 A kanyarhatárok és a kanyarnevek pályánként egy kanyartáblával felismerhetők. *(technikai prototípus)*
2. 🟧 Az `.ibt` fájl tartalmazza a setup azonosítóját. *(fájl-elemzés)*
3. 🟧 Szabályalapú javaslat is elég jó és hihető. *(használhatósági teszt, 8. fejezet)*
4. 🟧 A javaslat mélysége megfelelő free/pro határ. *(a feature-set döntésnél)*
5. 🟧 A versenyzők a következő session után visszanézik, működött-e a javaslat.
