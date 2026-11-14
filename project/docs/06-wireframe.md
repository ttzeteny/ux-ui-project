# Low-fidelity wireframe – 6. fejezet

**Figma design fájl:** https://www.figma.com/design/FuNI5vQfABJU65oCM8jcZR (oldalak: **Wireframe**, **Jegyzetek**)

## Képernyők (Wireframe oldal)

| Frame | User flow lépés (5. házi) | Elsődleges művelet |
|---|---|---|
| **01 – Sessionök listája** | Értesítés / session megnyitása | „Összefoglaló megnyitása” |
| **02 – Session-összefoglaló (fő képernyő)** | Rangsorolt kanyarlista, D4 referencia | „Les Combes részletei” |
| **03 – Kanyar részletei + javaslat** | Kanyar részletei, javaslat | „Következő kanyar: Bus Stop” |
| **01b – Állapot: nincs felvétel (E1)** | D1 = nem | „Hogyan kapcsolom be a felvételt? (Alt+L)” |
| **04 – Állapot: eltérő setup (E5)** | D5 = nem | „Azonos setupú kör választása” |
| **05 – Paywall: javaslat prémium (E6)** | D6/D7 | „7 napos próba indítása” |
| **02 – Kompakt ablak (960 px)** | A fő képernyő kisebb ablakban | „Les Combes részletei” |

## Szabályok, amiket betartottam
- **Szín nélkül**: fehér háttér és 3 szürke árnyalat (#F2F2F2, #BDBDBD, #424242). Nincs fotó vagy díszítő ikon.
- **Valódi szöveg** minden gombon, címkén és állapotüzeneten. A gombok a következményt nevezik meg („Összefoglaló megnyitása”, „7 napos próba indítása”).
- **Egy elsődleges művelet képernyőnként** (sötét gomb); a többi másodlagos gomb vagy szöveges link.
- **Auto Layout mindenhol:** a képernyő vázától a tartalomoszlopig, a listáktól a sorokig. Szélsőséges tartalom próbája: a „Circuit de Spa-Francorchamps – 24 Hours layout (hosszú név teszt)” két sorba tördelődik, a sor magassága nő, semmi nem csúszik egymásra.
- **Komponensek** (Wireframe oldal, bal oldalt): Oldalsó menü, Session sor, Kanyar sor, Állapotsáv, Grafikon helyőrző, Gomb (elsődleges, másodlagos, szöveges link). A képernyőkön ezek példányai szerepelnek, szöveges komponens-tulajdonságokkal.
- **Beszédes rétegnevek:** például „Referencia sáv”, „Kanyarlista”, „Javaslat kártya”, „Párbeszédablak – eltérő setup”.

## Jegyzetek oldal
- **Wireflow:** a képernyők kicsinyített másolatai, nyilakkal és feliratokkal:
  - 01 → 02 → 03 (fő út);
  - 01 → 01b (E1), 02 → 04 (E5), 03 → 05 (E6);
  - 02 ↔ kompakt ablak.
- **Annotációk** (számozott jelölők + lista):
  1. A mappafigyelés automatikus, nincs kézi feltöltés; a setup-címke minden sorban látszik.
  2. A kanyarlista rangsorolása és a „fő ok” forrása; a kanyartábla feltevése (E3: szektorszintű nézet).
  3. Alapértelmezett referencia: a saját legjobb kör; ha nincs, az elméleti legjobb (E4).
  4. A javaslat szabályalapú, kanyaronként egy; pontosnak csak azonos setupnál jelöljük.
  5. Eltérő setup: figyelmeztetés, nem tiltás; a setup neve az .ibt fájlból jön (feltevés).
  6. A paywall a döntés pontján mutatja az árat, a próba végét, az emlékeztetőt és a lemondást (3. házi, L2); a kanyar és az ok ingyen megmarad.
  7. Nincs felvétel: a session a listában marad, útmutató az Alt+L-hez, a korábbi adatok nem vesznek el.
  8. Kisebb ablak (töréspont-feltevés: ~1100 px alatt): a menü ikonsávvá csukódik, a térkép lenyitható, a mag megmarad.
