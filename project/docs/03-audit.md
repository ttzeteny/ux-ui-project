# Használhatósági és akadálymentességi audit – Track Titan előfizetési folyamat

**Szolgáltatás:** Track Titan (versenytárs: sim racing telemetria-elemző SaaS, freemium modell)
**Feladat:** *Egy középhaladó iRacing-versenyző (Máté, 2. házi persona) eldönti, melyik csomag kell neki, és eljut a regisztrációig.* A fiók létrehozása előtt megálltunk, mert a fizetési lépés belépés nélkül nem érhető el.
**Miért ez a feladat?** A saját termékünk is freemium/előfizetéses lesz. A 2. házi nyitott kérdése az volt, hogy hol legyen a fizetős határ, és mennyire bíznak meg a felhasználók egy fizetős próbában. A versenytárs elemző felülete csak fiókkal érhető el, ezért az előfizetési folyamatot auditáltuk.
**Képernyőképek:** [`03-audit-kepek/`](03-audit-kepek/).

## Képernyők a feladat sorrendjében

| # | Kép | Pillanat |
|---|---|---|
| 1 | `01-cookie.jpg` | Kezdés: süti-hozzájárulás a csomagoldalon |
| 2 | `02-plans.jpg` | Döntés: a négy csomag a marketingoldalon (USD) |
| 3 | `03-faq.jpg` | Információkeresés: GYIK (próbaidő, lemondás) |
| 4 | `04-cancel.jpg` | Információ: „Hogyan mondhatom le?” válasz |
| 5 | `07-app-pricing.jpg` | Döntés: ugyanaz a csomagoldal az appban (Ft) |
| 6 | `08-trial-register.jpg` | A „7 day free trial” gomb után: regisztráció |
| 7 | `05-register.jpg` | Regisztrációs űrlap (kontrasztmérés) |
| 8 | `06-validation.jpg` | Hibaállapot-próba: érvénytelen e-mail („abc”) |

## A 6 lelet (súlyosság szerint rendezve)

Szerkezet: **Megfigyelés** (mit láttunk) · **Alapelv** · **Következmény Máté szemszögéből** · **Javítási irány**.

### L1 – A választott csomag elveszik a regisztrációnál · **NAGY**
*Kép: 07, 08*
- **Megfigyelés:** a marketingoldal mind a négy CTA-ja („Start Free”, 3× „Get Started”) és az app „7 day free trial” gombjai ugyanarra a `/register` címre visznek. A regisztrációs oldal nem írja ki, melyik csomagot vagy próbát választotta a felhasználó, és a próbaidőről sem szól.
- **Alapelv:** Nielsen 6. (felismerés a felidézés helyett), 1. (rendszerállapot láthatósága).
- **Következmény:** Máté nem tudja, hogy a regisztráció után a Plus próbája indul-e, vagy az ingyenes fiók. A döntését fejben kell tartania, és bizonytalanul regisztrál, vagy visszalép.
- **Javítási irány:** a választott csomag és a próba feltételei kísérjék végig a regisztrációt (például „Plus – 7 nap ingyen, utána 2500 Ft/hó” fejléc, „Csomag módosítása” linkkel).

### L2 – A próbaidő utáni terhelés nem látszik a döntés pontján · **NAGY**
*Kép: 07*
- **Megfigyelés:** a „7 day free trial” gombok mellett nincs leírva, mi történik a 7. nap után: lesz-e automatikus terhelés, mennyi lesz, és kér-e a rendszer kártyát. Ezt csak az app GYIK-jának egy mondata sejteti („You can cancel anytime within the 7-day free trial”). A marketingoldal kártyáin a próba egyáltalán nem szerepel.
- **Alapelv:** Nielsen 1. (állapot láthatósága) és 10. (súgó a döntés helyén). 3.4: a *rejtett költség* minta kockázata. Ezt nem állítjuk: a fizetési lépés fiók nélkül nem volt vizsgálható.
- **Következmény:** Máté nem meri elindítani a próbát, mert attól tart, hogy elfelejti lemondani és terhelést kap. Ha mégis elindítja, a váratlan terhelés bizalomvesztést okoz.
- **Javítási irány:** a CTA alatt egy sor: „7 nap ingyen, utána 2500 Ft/hó. A próba vége előtt e-mailben emlékeztetünk, és bármikor lemondhatod.”

### L3 – A GYIK billentyűzettel nem érhető el · **NAGY** · *akadálymentesség (Tab-próba)*
*Kép: 03*
- **Megfigyelés:** a Tab-próbán a fókusz a Trustpilot-linkről közvetlenül a „Works for PC and console” linkre ugrott. A hat GYIK-kérdés közül egyik sem kap fókuszt. A kérdések `div` elemek, szerep (`role`), `tabindex` és `aria-expanded` nélkül.
- **Alapelv:** WCAG 2.1.1 Billentyűzet (Működtethető), 4.1.2 Név, szerep, érték (Robusztus).
- **Következmény:** aki billentyűzettel vagy képernyőolvasóval böngész, nem tudja meg a próbaidő és a lemondás feltételeit. Pont azokat az információkat, amelyek az L2 miatt máshol sem látszanak.
- **Javítási irány:** natív `<button>` a kérdéseknek (vagy `<details>/<summary>`), `aria-expanded` állapottal és látható fókusszal.

### L4 – Ellentmondó árak és csomagleírások a két oldalon · **KÖZEPES**
*Kép: 02, 07*
- **Megfigyelés:** a marketingoldalon $7.99 / $14.99 / $19.99 szerepel, az appban ugyanez 2500 Ft / 5000 Ft / 6750 Ft. A leírások is eltérnek: a Community csak az appban kap „Real-time coaching overlay”-t; az Ultra az egyik helyen „All Plus & Community”, a másikon „All Plus & Setup”. Az app GYIK-ja egy „Premium” csomagot is említ, ami egyik oldalon sem létezik.
- **Alapelv:** Nielsen 4. (következetesség és szabványok), 2. (egyezés a valós világgal: pénznem).
- **Következmény:** Máté nem tudja, melyik ár az igazi, és mit kap pontosan. Az összehasonlításhoz két fület kell nyitva tartania, és csökken a bizalma.
- **Javítási irány:** egyetlen forrásból generált csomaglista; a helyi pénznem mindenhol, adóval vagy annak jelölésével; a GYIK nevei egyezzenek a csomagnevekkel.

### L5 – Színnel jelölt, alacsony kontrasztú link · **KÖZEPES** · *akadálymentesség (kontrasztmérés – szöveg)*
*Kép: 04*
- **Megfigyelés:** a lemondási válaszban a „settings page on the app” link `#EBA657` színű fehér háttéren, aláhúzás nélkül. **Mért kontraszt: 2,07 : 1** (18 px-es szövegnél az AA 4,5 : 1-et vár). A linket csak a szín különbözteti meg a szövegtől.
- **Alapelv:** WCAG 1.4.3 Kontraszt (minimum), 1.4.1 Szín használata (Észlelhető).
- **Következmény:** gyengénlátó vagy színtévesztő felhasználó, illetve rossz monitoron vagy napfényben bárki átsiklik azon, hol lehet lemondani.
- **Javítási irány:** sötétebb linkszín (legalább 4,5 : 1) és aláhúzás, vagy egy önálló „Előfizetés kezelése” gomb.

### L6 – Gyengén látható űrlapmezők és CTA a regisztrációnál · **KÖZEPES** · *akadálymentesség (kontrasztmérés – felületi elem)*
*Kép: 05*
- **Megfigyelés:** a beviteli mező háttere (`#5D6162`) az oldal hátteréhez (`#2D3031`) képest **2,12 : 1**, a mezőnek nincs kerete. A „Sign up” gomb fehér, normál vastagságú 16 px-es felirata a `#BC680A` háttéren **4,10 : 1**.
- **Alapelv:** WCAG 1.4.11 Nem szöveges kontraszt (AA: 3 : 1), 1.4.3 Kontraszt (AA: 4,5 : 1).
- **Következmény:** gyengébb látásnál vagy rossz kijelzőn nehéz megtalálni, hol kell gépelni, és a fő gomb felirata is gyengén olvasható.
- **Javítási irány:** legalább 3 : 1-es mezőkeret vagy -háttér, sötétebb gombszín vagy félkövér, nagyobb felirat.

## Kontrasztmérések (WCAG 2.x képlet, a számított CSS-színekből)

| Elem | Előtér | Háttér | Arány | AA-elvárás | Eredmény |
|---|---|---|---|---|---|
| GYIK link („settings page on the app”), 18 px | `#EBA657` | `#FFFFFF` | **2,07 : 1** | 4,5 : 1 | ❌ (L5) |
| Regisztrációs mező kontra oldalháttér | `#5D6162` | `#2D3031` | **2,12 : 1** | 3 : 1 | ❌ (L6) |
| „Sign up” gomb felirata, 16 px, normál | `#FFFFFF` | `#BC680A` | **4,10 : 1** | 4,5 : 1 | ❌ (L6) |
| Süti-sáv „Deny” / „Accept All”, 14 px | `#FDFDFD` | `#F1860D` | **2,53 : 1** | 4,5 : 1 | ❌ (további észrevétel) |
| GYIK válaszszöveg | `#141414` | `#FFFFFF` | 18,42 : 1 | 4,5 : 1 | ✅ |

## Tab-próba (kézi, csomagoldal)
- A süti-sáv **billentyűzettel kezelhető**, a fókusz jól látható (például a „Deny” gombon). ✅
- Az Ultra kártya „Get Started” gombja után a fókusz sorrendje: előfizetés-banner → vélemény-karusszel nyilai → Trustpilot → **„Works for PC and console”**. **A teljes GYIK kimarad.** ❌ (L3)
- Az app oldalán van **„Skip to main content”** link, és az ikonos oldalsáv elemeinek van `aria-label`-je. ✅

## Állapotlista (a vizsgált folyamatban)

| Állapot | Megtaláltam? | Minőség |
|---|---|---|
| **Normál** | Igen | Jó: a csomagkártyák áttekinthetők, az ár és a CTA egyértelmű. |
| **Betöltő** | Nem érdemben | A lapok gyorsan betöltöttek, folyamatjelzőt vagy vázszerkezetet nem láttunk. |
| **Üres** | Nem vizsgálható | Fiók nélkül nincs lista vagy keresési eredmény. |
| **Hiba** | Részben | Gyenge: az „abc” e-mail mezőelhagyáskor nem kap jelzést (a böngésző érvénytelennek tartja, de üzenet nem jelenik meg), és a jelszó-követelmények sem látszanak előre (megelőző hibakezelés hiányzik). Beküldést nem végeztünk. |
| **Siker** | Részben | A süti-elutasítás után a sáv eltűnik, visszaigazolás nélkül (elfogadható). A regisztráció sikerállapota fiók nélkül nem vizsgálható. |
| **Tiltott** | Igen | Gyenge: bejelentkezés nélkül a „7 day free trial” nem tiltott gomb, hanem magyarázat nélkül a regisztrációra visz (L1). Azt nem mondja meg, miért és mi kell hozzá. |

## Persona-frissítés (Máté)
- **Új kockázat:** egy fizetős próbánál nem látja előre, mikor és mennyit terhelnek, ezért vagy nem próbálja ki a prémiumot, vagy váratlan terhelés éri, és elveszíti a bizalmát (L2, L4).
- **Új korlát:** a csomagok összehasonlításához több oldal között kell ugrálnia, és fejben tartania, mit választott (L1, L4).

## Mit viszünk át a saját termékünkbe?
1. A paywall **mindig mondja meg a próba utáni árat és dátumot**, és a próba vége előtt küldjön emlékeztetőt.
2. A választott csomag **kísérje végig** a regisztrációt és a fizetést.
3. **Egy árforrás**, helyi pénznemben.
4. A GYIK és minden kinyitható elem **natív, billentyűzettel kezelhető** vezérlő legyen.
5. A lemondás legyen ugyanolyan egyszerű, mint a feliratkozás (ezt a Track Titan jól csinálja).
