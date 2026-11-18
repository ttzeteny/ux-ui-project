# Projektprezentáció, önreflexió és portfólióeset-vázlat – 10. fejezet

- **Prezentáció (Figma, „Prezentáció” oldal):** https://www.figma.com/design/FuNI5vQfABJU65oCM8jcZR?node-id=50-383
- **Diavetítés:** https://www.figma.com/proto/FuNI5vQfABJU65oCM8jcZR?node-id=50-383&starting-point-node-id=50%3A383
  - → vagy kattintás: következő dia; ←: előző dia.
- **Végső prototípus (demó):** https://www.figma.com/proto/FuNI5vQfABJU65oCM8jcZR?node-id=27-1108&starting-point-node-id=27%3A1108
- **PDF-export:** [`project/pdf/10-prezentacio.pdf`](../pdf/10-prezentacio.pdf) (Figma → File → Export frames to PDF a „Prezentáció” oldalon).

## Fő állítás egy mondatban
Egy rangsorolt kanyarlista és kanyaronként egy kipróbálható javaslat 2 percen belül megmondja a versenyzőnek, hol és miért veszít időt.

## Diák (állításcímek)
12 dia, 1920×1080, a projekt saját szövegstílusaival és színváltozóival (sötét mód). Időzítés: kb. 9 perc, ebből 90 mp élő demó. Az előadói jegyzetek a vásznon, minden dia mellett jobbra vannak.

| # | Blokk | Állításcím | Bizonyíték a dián | Idő |
|---|---|---|---|---|
| 1 | Téma | A simracerek tudják, hogy lassúak – azt nem, hol és miért | fő állítás, témaválasztás indoka | 40 mp |
| 2 | Probléma, felhasználó | Öt versenyzőből három nem találja meg az adatban a problémás kanyart | interjúidézet és megfigyelések, persona (Máté) | 60 mp |
| 3 | Kutatás (journey) | A mélypont a hiba keresése: a versenyző kanyarban gondolkodik, az eszköz csatornákban beszél | journey érzésgörbe, 2 insight | 50 mp |
| 4 | Döntés | Csatornák helyett: kanyarlista → egy kanyar 3 csatornával → egy kipróbálható javaslat | HMW, insightok, sikerkritérium, hatókör, freemium-határ | 50 mp |
| 5 | Prototípus | A fő képernyő egyetlen kérdésre válaszol: hol veszítettem időt? | a fő képernyő kiemeléssel, 3 számozott pont | 45 mp |
| 6 | Demó | Demó: Spa-edzés után három kattintással a kipróbálható teendőig | feladat, útvonal, prototípus-link | 90 mp |
| 7 | Teszt, lelet | Első tesztkör: három résztvevőből kettő azt hitte, a gomb átírja a setupját | idézet, előtte–utána | 60 mp |
| 8 | Iteráció | Ami ingyen megmarad, azt a döntés helyén, jól láthatóan mondjuk ki | idézet, előtte–utána (paywall) | 45 mp |
| 9 | Eredmény | A második körben a fő feladat és a paywall megértése 3/3 – a setup-címke még nyitott | sikerkritérium-táblázat (1. vs. 2. kör), korlát | 60 mp |
| 10 | Rendszer | A sötét mód és a közös komponensek a használati helyzetből következnek | idézet, komponenspéldányok, kontraszt | 40 mp |
| 11 | Zárás | Tanulság: a valós adat kérdését korábban kellett volna megfogni | tanulságok, nyitott kérdés, következő lépés | 50 mp |
| 12 | Tartalék | Tartalék a demóhoz: a fő út négy képernyőben | 4 képernyő | – |

**Kis minta, szimulált résztvevők:** a 2., 7., 8., 9. és 10. dián jelölve, a 9. dián külön korlátdobozban.

## Önreflexió

**Mi történt?**
- A projekt egy problémából indult: a középhaladó versenyző nem találja meg az adatban, hol veszít időt. Ebből egy kanyarközpontú session-összefoglaló lett, amit wireframe, kattintható prototípus, két tesztkör és két iteráció után design systemmé és átadási csomaggá dolgoztam ki.
- A kutatást és a teszteket szimulált (AI-generált) résztvevőkkel végeztem.

**Mi a legerősebb bizonyítékom?**
- Az L1 → D1 lánc: az 1. körben 2/3 résztvevő megállt a „Kipróbálom a következő sessionben” gomb előtt, mert azt hitte, módosítja a setupját.
- A hipotézis egyetlen változtatásról szólt (a felirat a következményt nevezi meg). A 2. körben 3/3 segítség nélkül eljutott a sikerállapotig.
- Ez az egyetlen pont, ahol a teljes ciklus (lelet → hipotézis → változtatás → újrateszt) végigment, ezért ez a legerősebb, bár kis és szimulált mintán.

**Mit tanultam?**
1. **A hipotézis fegyelmez.** Ha egy változtatáshoz kimondtam az okot és a várt hatást, kiderült, mit kell újratesztelni. A setup-címkénél (D4) az első javítás nem volt elég, és ezt csak azért vettem észre, mert előre rögzítettem, mit várok.
2. **A legnagyobb bizonytalanság nem a felületben van, hanem az adatban.** Minden teszt egyetlen kitalált sessionre épült, így a felület érthetőségét vizsgáltam, azt nem, hogy a „fő ok” valós adaton helyes-e. Ha a fő ok rossz, a jól érthető felület is rossz döntéshez vezet.

**Mit csinálnék másképp, és hogyan?**
- A valós adat kérdését már a 2–4. héten bevonnám: legalább egy saját vagy önkéntes .ibt-fájlból kézzel elkészített kanyarrangsorral (Wizard of Oz), még a wireframe előtt.
- A szimulált résztvevők helyett, vagy mellettük, legalább 2–3 valódi simracerrel tesztelnék. A szimulált válaszok jók voltak a módszer gyakorlására, de nem mondanak semmit a valós bizalomról és a valós adatról.

**Következő lépés:** Wizard of Oz-teszt 5 valódi simracerrel a saját .ibt-adataikkal. Siker: legalább 4/5 szerint a rangsor első kanyarja valóban a fő gyengeségük, és legalább 3/5 a „fő okot” is helyesnek tartja (9. házi, 5. pont).

## Hallgatótársi visszajelzés
*(Kitöltendő a próbaelőadás után: egy hallgatótárs válaszai.)*
- Mi volt a fő állítás?
- Mi volt nehezen érthető?
- Mi maradt meg a legjobban?
- Változtattam-e utána valamin?

---

## Portfólióeset (vázlat)

**Cím:** Két perc a session után – kanyarközpontú telemetria-elemzés iRacing-versenyzőknek

**1. Kontextus, szerep, korlátok**
- Egyéni egyetemi projekt (PTE MIK, UX/UI kurzus), 10 hét.
- Szerepem: minden szakasz, a kutatástól az átadásig.
- Korlátok:
  - nem volt valós felhasználói adat és fejlesztői partner;
  - a kutatás és a tesztek résztvevői szimuláltak voltak (AI-generált, oktatói engedéllyel);
  - a platform natív desktop app, az adatforrás csak iRacing.

**2. Probléma és cél**
- A középhaladó simracer tudja, hogy lassú, de a csatornákra bontott telemetriából nem derül ki, *melyik kanyarban* és *miért*.
- Sikerkritérium: egy új session után 2 percen belül, segítség nélkül megnevezi a legnagyobb veszteségű kanyart és az okát.

**3. Kutatás és insightok**
- Módszer: 5 interjú (szimulált), affinity map, persona, journey.
- Insight 1: a versenyző kanyarban gondolkodik, az eszköz csatornákban beszél.
- Insight 2: nem adatot keres, hanem kipróbálható teendőt.
- Audit (Track Titan előfizetés): a rejtett feltételek rontják a bizalmat.

**4. Kulcsdöntések**
- Az első nézet egy rangsorolt kanyarlista, és csak egy kanyarhoz jelenik meg 3 csatorna.
- Kanyaronként egy javaslat, ez a prémium rész. A kanyar és az ok ingyenes marad, így az ingyenes csomag is megoldja a fő feladatot.
- A setup tárolása és az eltérés jelzése benne van, a setup elemzése nincs.
- A sötét mód az alapértelmezett, mert a felhasználók sötét szobában használják az appot.

**5. Teszt, iteráció, eredmény**
- Két kör, 3 + 3 fő (szimulált).
- 5 lelet; a legfontosabbak a félreérthető gombfelirat és a paywall rejtett „ingyenes” része.
- A 2. körben a fő feladat 3/3, a sikerállapot 3/3 (az 1. körben 2/3), a paywall megértése 3/3 (az 1. körben 1/3).
- Nyitott: a setup-címke (2/3) és a veszteség viszonyítási alapja.
- **Korlát:** kis, szimulált minta és egyetlen kitalált session.

**6. Tanulság és következő lépés**
- A felület érthetősége a vizsgált résztvevőknél működött.
- A termék alapígérete (helyes-e a „fő ok” valós adaton) még nincs bizonyítva.
- Következő lépés: Wizard of Oz-teszt valós .ibt-adatokkal.

**Képek (képaláírással):**
- journey érzésgörbe;
- a fő képernyő kiemeléssel;
- a gomb előtte–utána;
- a sikerkritérium-táblázat;
- a design system oldal.