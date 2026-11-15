# Kattintható prototípus – 7. fejezet

**Figma fájl:** https://www.figma.com/design/FuNI5vQfABJU65oCM8jcZR (Prototype fül; a forgatókönyv, a korlátok és a megfigyelések a **Jegyzetek** oldal alján)
**Prototípus-link (fő út):** https://www.figma.com/proto/FuNI5vQfABJU65oCM8jcZR?node-id=2-2&starting-point-node-id=2%3A2

## Hűség
- **Vizuális:** alacsony (a 6. házi szürke wireframe-je).
- **Tartalmi:** magas (valódi kanyarnevek, időveszteségek, okok, árak és szövegek).
- **Interakciós:** közepes. A fő út és 2 kivétel kattintható. Átmenetek: Dissolve 200 ms; a sikerállapotra Smart animate 300 ms, mert a két képernyő közös elemei a helyükön maradnak.

## Flow-k (kiindulópontok)
| Flow | Útvonal |
|---|---|
| **1 – Fő út: hol veszítettem időt?** | 01 Sessionök → „Összefoglaló megnyitása” → 02 Összefoglaló → kanyarsor vagy „Les Combes részletei” → 03 Kanyar részletei → „Kipróbálom a következő sessionben” → **06 Siker** → „Vissza a sessionökhöz” → 01 |
| Kivétel a fő úton (E5) | 02 → „Referencia módosítása” → 04 Eltérő setup → „Azonos setupú kör választása” vagy „Folytatás így” → 02 |
| **2 – Kivétel: nincs prémium (E6)** | 05 Paywall → „Most nem, maradok az ingyenesnél” → 02 |
| **3 – Kivétel: nincs felvétel (E1)** | 01b → „Rendben, értem” → 01 |

- **Back akciót** kapott a „Vissza a kanyarlistához”, a „Visszavonás” és a „Nem érhető el” képernyő „Vissza” gombja.
- **Zsákutcák helyett** a következők a semleges „99 – Ez a rész most nem érhető el a prototípusban” képernyőre visznek: a nem kidolgozott kanyarok, a szektornézet, a pályatérkép, a többi menüpont, a próba indítása és a felvételi útmutató.

## Változtatások a wireframe-en
- **03:** új elsődleges művelet: „Kipróbálom a következő sessionben”. A „Következő kanyar” szöveges link lett, hogy képernyőnként egy fő gomb maradjon.
- **Új 06-os sikerállapot:** „Les Combes bekerült a fókuszba”, mentésjelző sávval (mikrointerakció) és „Visszavonás” linkkel. Megerősítő ablak helyett visszavonás, a 7.1 lecke szerint.
- **Új 99-es képernyő:** „Nem érhető el a prototípusban”.

## Forgatókönyv és feladat
- **Forgatókönyv:** Most fejeztél be egy edzést Spában a Porsche 911 GT3 R-rel. Úgy érzed, valahol sok időt hagytál a pályán, és a következő edzésre szeretnél egy konkrét dolgot, amin dolgozhatsz.
- **Feladat:** Derítsd ki, hol veszítetted a legtöbb időt, és miért. Utána döntsd el, mit próbálsz ki legközelebb.
- **Kezdőpont:** 01 – Sessionök listája (flow 1).
- **Sikerkritérium:** a résztvevő 2 percen belül, segítség nélkül megnevezi a kanyart (Les Combes) és az okát (korábbi fékpont), és eljut a 06-os sikerállapotig. Más ésszerű út (például a kanyarsorra kattintás) nem hiba.

## Korlátok
- Nincs valós .ibt-beolvasás; egyetlen kitalált Spa-session adatai szerepelnek.
- Csak a Les Combes részletei vannak kidolgozva; a többi elem a „Nem érhető el” képernyőre visz.
- Nincs valódi fizetés.
- A grafikonok helyőrzők; a próba a szerkezetet és a szövegek megértését vizsgálja, nem az adatvizualizációt.
- Asztali nézet, 1280×800; a 960 px-es változat csak a részletekig kattintható.