---
week: 03
neptun: YV4RVH
---
Használhatósági és akadálymentességi audit: a **Track Titan** (versenytárs telemetria-SaaS) előfizetési folyamata.

**Feladat:** egy középhaladó iRacing-versenyző (Máté, a 2. házi personája) kiválasztja a neki való csomagot, és eljut a regisztrációig. A fiók létrehozása előtt megálltunk. A versenytárs elemző felülete csak fiókkal érhető el, ezért az előfizetési folyamatot vizsgáltuk. Ez közvetlenül hasznos a saját freemium/paywall döntéseinkhez.

**FigJam-board („3. Audit” szekció):** https://www.figma.com/board/rcQ2oV1cd0kX9QzXVfd2Fm?node-id=5-512
**Annotált audit-board képként is:** [03-audit-board.png](../../project/docs/03-audit-kepek/03-audit-board.png)
**Részletes leírás:** [project/docs/03-audit.md](../../project/docs/03-audit.md)
**Képernyőképek:** [project/docs/03-audit-kepek/](../../project/docs/03-audit-kepek/)

## A 6 lelet

| # | Lelet | Alapelv | Súlyosság |
|---|---|---|---|
| L1 | A választott csomag elveszik a regisztrációnál | Nielsen 6., 1. | **Nagy** |
| L2 | A próba utáni terhelés nem látszik a döntés pontján | Nielsen 1., 10.; 3.4 (rejtett költség kockázata) | **Nagy** |
| L3 | A GYIK billentyűzettel nem érhető el *(Tab-próba)* | WCAG 2.1.1, 4.1.2 | **Nagy** · akadálymentesség |
| L4 | Ellentmondó árak és csomagleírások (USD kontra Ft) | Nielsen 4., 2. | Közepes |
| L5 | Színnel jelölt link, 2,07 : 1 *(kontrasztmérés: szöveg)* | WCAG 1.4.3, 1.4.1 | Közepes · akadálymentesség |
| L6 | Mezőháttér 2,12 : 1, gombfelirat 4,10 : 1 *(kontrasztmérés: felületi elem)* | WCAG 1.4.11, 1.4.3 | Közepes · akadálymentesség |

## Kötelező elemek
- **Tab-próba:** a süti-sáv billentyűzettel kezelhető, de a GYIK teljesen kimarad a fókuszsorrendből (L3).
- **Kontrasztmérés:** 5 mérés a WCAG-képlettel a számított CSS-színekből. Ebből 4 nem éri el az AA szintet.
- **Állapotlista:** a hat állapot mindegyike értékelve (normál, betöltő, üres, hiba, siker, tiltott).
- **Persona-frissítés:** új kockázat (nem látja előre a próba utáni terhelést) és új korlát (fejben kell tartania a választott csomagot).
- **Pozitív példák is:** egyforma hangsúlyú „Deny” és „Accept All”, önkiszolgáló lemondás, skip link.

## Mit tanulunk belőle a saját termékünkhöz?
A paywall mondja meg a próba utáni árat és dátumot, és a próba vége előtt küldjön emlékeztetőt. A választott csomag kísérje végig a regisztrációt. Egy árforrás legyen, helyi pénznemben. A GYIK és minden kinyitható elem billentyűzettel is kezelhető legyen. A lemondás legyen ugyanolyan egyszerű, mint a feliratkozás.
