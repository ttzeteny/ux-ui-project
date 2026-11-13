# Információarchitektúra és user flow – 5. fejezet

> A kártyarendezés résztvevői (P1–P3) **szintetikusak**: a csoportosításokat AI generálta a 2. házi personáinak mintájára. Az eredmények munkahipotézisek, a szerkezetet később fa-teszttel kell ellenőrizni.
> A kiinduló irány a 4. házi döntése: **kanyarközpontú session-összefoglaló**. A körhöz tartozó setup tárolása és megjelenítése a hatókör része, a setup elemzése nem.

## 1. Tartalomleltár (20 kártya)

| # | Kártya | Fontosság a fő feladathoz |
|---|---|---|
| K1 | Sessionök listája | Elsődleges |
| K2 | Session-összefoglaló (köridők) | Elsődleges |
| K3 | Kanyarlista időveszteséggel | Elsődleges |
| K4 | Kanyar részletei (fék, gáz, sebesség) | Elsődleges |
| K5 | Javaslat a következő sessionre | Elsődleges |
| K6 | Referenciakör kiválasztása | Elsődleges |
| K7 | Saját legjobb kör | Másodlagos |
| K8 | Setup-címke és eltérés-jelzés | Elsődleges |
| K9 | Körök összehasonlítása | Másodlagos |
| K10 | Pálya-előzmények (fejlődés pályánként) | Másodlagos |
| K11 | Pályatérkép | Másodlagos |
| K12 | Edzésterv / fókuszkanyar | Másodlagos |
| K13 | Értesítés a session végén | Másodlagos |
| K14 | Telemetria-mappa beállítása | Harmadlagos |
| K15 | Súgó: a felvétel bekapcsolása | Másodlagos |
| K16 | Előfizetés és számlázás | Harmadlagos |
| K17 | Próbaidő állapota | Másodlagos |
| K18 | Profil és autók | Harmadlagos |
| K19 | Fogalomtár (trail braking, apex…) | Harmadlagos |
| K20 | Általános beállítások (mértékegység, nyelv) | Harmadlagos |

## 2. Nyílt kártyarendezés (3 szintetikus résztvevő)

**P1 – középhaladó GT3-as (R1-hez hasonló profil)**
- *Sessionjeim:* K1, K2, K3, K4, K5, K11
- *Összehasonlítás:* K6, K7, K8, K9
- *Fejlődés:* K10, K12
- *Fiók:* K16, K17, K18
- *Beállítások:* K13, K14, K15, K19, K20

**P2 – kezdőbb középhaladó (R2-höz hasonló profil)**
- *Hol lassultam?:* K2, K3, K4, K11
- *Mit csináljak?:* K5, K12
- *Köreim:* K1, K6, K7, K8, K9
- *Előzmények:* K10
- *Fiókom:* K16, K17, K18
- *Segítség:* K15, K19
- *Beállítások:* K13, K14, K20

**P3 – haladó ligaversenyző (R3-hoz hasonló profil)**
- *Sessions:* K1, K2, K9
- *Analízis:* K3, K4, K5, K11
- *Referencia:* K6, K7, K8
- *Edzés:* K10, K12
- *Account:* K16, K17, K18
- *Settings:* K13, K14, K15, K19, K20

### Összegzés
- **Visszatérő csoportok (3/3):**
  - a session elemzésének tartalma együtt van (K2, K3, K4);
  - fiók, előfizetés és próbaidő együtt (K16, K17, K18);
  - beállítások külön csoportban.
- **A setup-címke (K8) mindhárom résztvevőnél a referenciával vagy az összehasonlítással került egy csoportba**, a session-elemzéssel nem. → A setup az összehasonlításhoz tartozik.
- **Elnevezések:** „Sessionjeim / Sessions”, „Összehasonlítás / Referencia”, „Fejlődés / Edzés / Előzmények”. P2 **kérdésekkel** nevezett el („Hol lassultam?”, „Mit csináljak?”).
- **Meglepő:**
  - P2 a javaslatot (K5) önálló csoportba tette („Mit csináljak?”). Neki a javaslat cél, nem részlet.
  - P3 angol szavakat használt.
  - A felvétel-súgót (K15) ketten a beállításokhoz, egy résztvevő a segítséghez tette.

## 3. Sitemap (natív desktop, oldalsó menü)

```
Alkalmazás (oldalsó menü)
├── Kezdőlap = Legutóbbi session  ◀ belépési pont: az app indítása
├── Sessionök
│   └── Session-összefoglaló „Hol veszítettem időt?” (kanyarlista, köridők, pályatérkép)  ◀ belépési pont: session-végi értesítés
│       ├── Kanyar részletei (3 csatorna + javaslat)  ★ fő feladat vége
│       └── Körök összehasonlítása (referenciakör, setup-eltérés)
├── Referenciakörök (saját legjobb, mentett referenciák, setup-címkével)
├── Fejlődés (pálya-előzmények, fókuszkanyar)
├── Fiók és előfizetés (profil, előfizetés, próbaidő)
├── Beállítások (telemetria mappa, értesítések, általános)
└── Súgó (a felvétel bekapcsolása, fogalomtár)

Csak hivatkozásból elérhető: Előfizetés / próbaidő (paywall) a javaslatból · Felvétel-útmutató a „Nincs felvétel” állapotból
```

**A fő feladat legrövidebb útja:** session-végi értesítés → Session-összefoglaló → Kanyar részletei (**2 kattintás**).

**Címkék és eltérések a kártyarendezéstől:**
- **„Sessionök”:** P1 és P3 elnevezése alapján (a simracing-szleng része).
- **„Hol veszítettem időt?”** a session-összefoglaló **címe**, P2 kérdés-alapú elnevezése nyomán. A menüben „Sessionök” marad, mert a menüpontnak rövidnek kell lennie.
- **„Referenciakörök”** önálló menüpont (P1, P3), és a setup-címke itt is látszik (K8 3/3).
- **A javaslat nem önálló menüpont** (eltérés P2-től): mindig egy kanyarhoz tartozik, ezért a kanyar részleteinél jelenik meg, a kanyar részletei oldalon a legfontosabb elemként.
- **A „Súgó” önálló menüpont** (csak P2 javasolta), mert a „Nincs felvétel” kivételes állapotból közvetlenül el kell érni.

## 4. User flow – fő feladat

**Cél:** egy session után megtalálni a legnagyobb időveszteségű kanyart, megérteni az okát, és kapni egy kipróbálható teendőt.

**Fő út:** session vége (iRacing) → új `.ibt` észlelése → beolvasás → értesítés → session-összefoglaló → *pálya felismerve?* → *van referencia?* → *egyezik a setup?* → rangsorolt kanyarlista → kanyar részletei → *prémium vagy próbaidő?* → kipróbálható javaslat → **siker**.

| Döntési pont | A döntéshez szükséges információ | Forrás |
|---|---|---|
| D1 Van új `.ibt` a mappában? | Megjelent-e új fájl | Mappafigyelés (`Documents\iRacing\telemetry`) |
| D2 Ép és teljes a fájl? | A körök épsége | `.ibt` fejléc és körhatárok |
| D3 Felismerte a pályát és a kanyarokat? | Pálya-azonosító és kanyartábla | `.ibt` session-adat + saját kanyartábla (feltevés) |
| D4 Van összehasonlítható referenciakör? | Azonos autóval és pályán futott kör | Helyi kör-előzmények |
| D5 Egyezik a setup? | A setup neve mindkét körnél | `.ibt` session-adat (feltevés) |
| D6 Prémium vagy próbaidő? | Az előfizetés állapota | Fiók / fizetési szolgáltató (külső rendszer) |
| D7 Elindítja a próbát? | Ár, a próbaidő vége, a lemondás módja | Paywall (3. házi, L2 tanulsága) |

**Kivételes ágak és kimenetük:**
| Ág | Mi történik | Kimenet |
|---|---|---|
| E1 – D1: nem volt felvétel | Figyelmeztetés + útmutató a felvétel bekapcsolásához | 🔴 Ez a session nem elemezhető; a következőnél be lesz kapcsolva |
| E2 – D2: hiányos vagy megszakadt fájl | Csak a teljes körök elemezve, a hiányosak jelölve | ↩ Folytatás az értesítéssel |
| E3 – D3: a kanyartábla hiányzik | Szektorszintű nézet + jelzés („kanyarok erre a pályára még nem elérhetők”) | ↩ Folytatás D4-gyel (gyengébb, de használható) |
| E4 – D4: nincs referenciakör | A saját elméleti legjobb kör lesz a referencia, jelölve | ↩ Folytatás D5-tel |
| E5 – D5: eltérő setup | Figyelmeztetés mindkét setup nevével: másik kör választása vagy tudatos folytatás | ↩ Folytatás a kanyarlistával |
| E6 – D6/D7: nincs prémium, nem indít próbát | Paywall: mit ad a javaslat, 2500 Ft/hó, 7 nap próba, mikor terhel, hogyan lehet lemondani | 🟢 Részleges siker: a kanyar és az ok ingyen megvan (a sikerkritérium teljesül), javaslat nélkül |

## 5. Wireframe-képernyők a 6. házihoz
1. **W1 Session-összefoglaló („Hol veszítettem időt?”):** rangsorolt kanyarlista, köridők, setup-címke. *Fő képernyő.*
2. **W2 Kanyar részletei:** 3 csatorna, a fő ok és a kipróbálható javaslat.
3. **W3 Sessionök listája:** setup-címkével, a „Nincs felvétel” állapottal (E1).
4. **W4 Referenciakör választása / setup-eltérés figyelmeztetés** (E4, E5).
5. **W5 Paywall és próbaidő** (E6): az ár, a próbaidő vége és a lemondás a döntés pontján látszik.
