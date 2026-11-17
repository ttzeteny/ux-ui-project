# Használhatósági teszt, leletek és mini UI-irányelv – 8. fejezet

- **Figma fájl:** https://www.figma.com/design/FuNI5vQfABJU65oCM8jcZR
  - **Finomított prototípus (8. házi)** oldal: a frissített, témázott képernyők és flow-k
  - **UI-irányelv** oldal: színek, kontraszt, szövegstílusok, térközök, elemszabályok
  - A **Wireframe** oldal változatlanul a 6–7. házi állapotát őrzi.
- **Frissített prototípus-link:** https://www.figma.com/proto/FuNI5vQfABJU65oCM8jcZR?node-id=27-1108&starting-point-node-id=27%3A1108

---

## 1. Tesztterv

### Tanulási célok
1. **El tudja-e a versenyző segítség nélkül, 2 percen belül azonosítani a sessionje legnagyobb időveszteségét és annak okát?** Ez a fő hipotézis (4. házi): a rangsorolt kanyarlista és a „fő ok” gyorsabb, mint a csatornák böngészése.
2. **Érti-e a versenyző, mi ingyenes és mi prémium, és mikor és mennyit fizetne?** Ez a paywall tisztessége (3. házi, L2 tanulság).

### Résztvevők
- **Célcsoport:** középhaladó vagy haladó iRacing-versenyzők, akik rendszeresen edzenek, és legalább egyszer néztek már telemetriát.
- **Szűrőkérdések:**
  - Az elmúlt hónapban legalább heti egyszer versenyeztél vagy edzettél iRacingben? (igen kell)
  - Néztél már telemetriát (Garage 61, MoTeC, VRS, Track Titan)? (igen kell, a „nem rendszeresen” is elfogadható)
  - Dolgozol UX-, design- vagy szoftverfejlesztői munkakörben ezen a projekten? (nem kell)
- **Kizárva:** a projekt csapattagjai és közeli barátok.
- **Létszám:** 3 fő (a kurzus minimuma). A minta korlátját a leletekben jelzem („3-ból 2”).

| Kód | Profil (szimulált) |
|---|---|
| R1 | 27 éves, kb. 2 100 iRating, GT3, heti 3–4 edzés. A Garage 61-et néha használja, de „nem tudja, hova nézzen”. |
| R2 | 34 éves, kb. 3 600 iRating, GT3 és LMP2, ligában versenyez. MoTeC-et használ, a setupokat is maga állítja. Esténként, sötét szobában simel. |
| R3 | 22 éves, kb. 1 500 iRating, MX-5 és GT4, heti 2 edzés. Telemetriát csak YouTube-videókból ismer. |

### Feladatok forgatókönyvvel
A feladatok nem nevezik meg a felület elemeit. Közös kiindulás: „Most fejeztél be egy esti edzést Spában a Porsche 911 GT3 R-rel.”

| # | Típus | Forgatókönyv és feladat | Kezdőpont | Sikerkritérium |
|---|---|---|---|---|
| F1 | Tájékozódó | „A csapattársad megkérdezi, melyik setuppal mentél ma. Nézd meg.” | 01 Sessionök | Megnevezi a setupot (spa_race_v3) a sessionlistából vagy az összefoglalóból. |
| F2 | Fő feladat | „Úgy érzed, valahol sok időt hagytál a pályán. Derítsd ki, hol és miért, és döntsd el, mit próbálsz ki legközelebb.” | 01 Sessionök | 2 percen belül, segítség nélkül megnevezi a kanyart (Les Combes) és az okot (korábbi fékpont), és eljut a sikerállapotig (06). |
| F3 | Megértés | „Kíváncsi vagy, mit javasolna az app erre a kanyarra. Mondd el, mi történik, ha ezt kéred, és mibe kerül.” | 05 Paywall (2. flow) | Saját szavaival helyesen elmondja: 7 nap ingyen, utána 2 500 Ft/hó, mikor jön az első terhelés, és mi marad meg ingyen. |

### Rögzített mérőszámok
- **Feladatsiker** (igen / részben / nem), minden feladatnál.
- **Segítségkérés** száma.
- **Hibák** (rossz útvonal, zsákutca) és a **kritikus hiba** léte.
- **Megértés:** F3-nál saját szavakkal elmondja a feltételeket.
- **Feladatidő:** csak tájékoztató (hangos gondolkodás mellett), F2-nél a 2 perces sikerkritérium miatt.
- **SUS:** nem használtam, mert 3 fős mintán nem értelmezhető, és nincs összehasonlítandó változat.

### Környezet
- Moderált, távoli teszt videóhívásban, képernyőmegosztással.
- A résztvevő a saját gépén nyitja meg a Figma prototípus-linket, Present módban, 1280 px széles ablakban.
- Kb. 20 perc. Egy moderátor és egy jegyzetelő.

---

## 2. Szóbeli tájékoztató és hozzájárulás (a teszt elején felolvasva)

> Köszönöm, hogy segítesz! Egy sim racing telemetria-app tervét teszteljük, **nem téged**: ha valami nem megy, az a terv hibája, és pont ezt keressük. Nincs rossz válasz. Arra kérlek, hogy gondolkodj hangosan, mondd el, mit nézel, mit vársz, és min lepődsz meg.
>
> Ez egy prototípus. Nem minden működik benne, és az adatok kitaláltak. Nem kérek jelszót vagy személyes adatot.
>
> Jegyzetet készítek, a neved nem szerepel benne (R1, R2… kódot használok). **Felvételt csak akkor készítünk, ha most kifejezetten engedélyezed**; azt csak a projekt két tagja látja, és a félév végén (2027. január 31.) töröljük. A képernyőmegosztást bármikor leállíthatod, bármelyik feladatot kihagyhatod, és bármikor abbahagyhatod; ebből semmilyen hátrányod nem származik.
>
> Rendben van így? Kérhetek felvételt, vagy maradjunk a jegyzetnél?

*(Szimuláció: R1 és R3 jegyzetet engedélyezett, R2 felvételt is.)*

---

## 3. Megfigyelési jegyzetek (anonimizált, szimulált)

Jelölés: **M** = megfigyelés (mit láttunk), **I** = szó szerinti idézet, **É** = értelmezés (hipotézis, nem tény).

### R1
| Feladat | Típus | Jegyzet |
|---|---|---|
| F1 | M | A sessionlistában a sorokat nézte, a setup-címkét nem találta. Megnyitotta az összefoglalót, ott a referenciasávban olvasta ki („Setup: spa_race_v3”). Kb. 50 mp. Siker: igen, de kerülőúton. |
| F1 | I | „Ja, itt van… a listában is ott volt, csak elsikkadt a sok szám között.” |
| F1 | É | A setup-címke a sorban vizuálisan egyenrangú a köridőkkel, nem tűnik fel → L4. |
| F2 | M | Az első kanyarsorra kattintott, a „Fő ok” dobozt olvasta el először. 1 perc 5 mp alatt megnevezte a kanyart és az okot. Siker: igen. |
| F2 | M | A javaslatkártyán 6 mp-et várt a gomb előtt, az egeret a gomb fölött tartotta. |
| F2 | I | „Kipróbálom… ez most átír valamit a setupban? Mert azt nem szeretném.” |
| F2 | É | A gomb felirata nem mondja meg a következményt, és a felhasználó a setup módosulásától tart → L1. |
| F3 | M | Helyesen mondta, hogy 7 nap ingyen, utána 2 500 Ft/hó. Siker: igen. |

### R2
| Feladat | Típus | Jegyzet |
|---|---|---|
| — | I | (bemelegítés) „Este simelek, lekapcsolt villannyal. Ha egy app vakítóan fehér, a második monitoron le is húzom a fényerőt.” |
| — | É | A sötét téma nem ízlés, hanem a használati környezet következménye → alapértelmezett mód (UI-irányelv). |
| F1 | M | Azonnal kiolvasta a setupot a listából. Siker: igen, kb. 10 mp. |
| F2 | M | Az összefoglalón először a pályatérképre kattintott (a kártyán „Kattintásra a kanyar részletei nyílnak” felirat volt), és a „Nem érhető el a prototípusban” képernyőre jutott. Vissza, majd a kanyarsor. 1 perc 30 mp, siker: igen, egy hibával. |
| F2 | I | „A térképen szoktam kiválasztani a kanyart, a MoTeC-ben is így megy.” |
| F2 | É | A térkép a haladó felhasználók elsődleges belépési pontja lehet, és most zsákutca → L5. |
| F2 | M | A „Kipróbálom a következő sessionben” gombra habozás nélkül kattintott, a siker képernyőn elolvasta a visszaigazolást. |
| F3 | M | Elmondta az árat és a próbát. Megkérdezte: „És ha nem fizetek, a kanyarlista is eltűnik?” A „A kanyart és a fő okot ingyen is látod” segédszöveget nem vette észre. Siker: részben. |
| F3 | É | Az ingyen megmaradó rész kis, halvány segédszövegben van, a döntésnél nem látszik → L2. |

### R3
| Feladat | Típus | Jegyzet |
|---|---|---|
| F1 | M | A listában nem találta, megkérdezte: „A setup az mi alapján van, a fájlnévből?” (segítségkérés: 1). Utána az összefoglalóban találta meg. Siker: részben. |
| F1 | É | Ugyanaz, mint R1-nél: a setup-címke nem tűnik fel → L4. |
| F2 | M | A „Les Combes részletei” gombbal ment tovább. A grafikon-helyőrzőket átugrotta, a fő okot felolvasta. 1 perc 40 mp, siker: igen. |
| F2 | M | A javaslat gombja előtt megállt, és nem kattintott, amíg a moderátor vissza nem kérdezett („Mit vársz, mi történne?”). |
| F2 | I | „Félek, hogy beállít valamit a játékban, és akkor a következő versenyen fura lesz az autó.” |
| F2 | É | A gomb félreértése ugyanaz, mint R1-nél → L1. Az egyik résztvevőnél a sikerállapot csak moderátori kérdés után jött → súlyos. |
| F3 | M | Úgy értette, hogy a próba indításakor azonnal fizet („akkor most levonja a 2 500-at?”), csak az újraolvasás után javította ki. Siker: részben. |
| F3 | É | Az első terhelés időpontja nincs kimondva; a „7 napig ingyenes” és az ár egy mondatban van → L3. |

### Összesítés
| Feladat | R1 | R2 | R3 | Megjegyzés |
|---|---|---|---|---|
| F1 setup | igen (kerülővel) | igen | részben (1 segítség) | 2/3 nem a listában találta |
| F2 fő feladat | igen, 1:05 | igen, 1:30 (1 hiba) | igen, 1:40 | A 2 perces kritérium 3/3-nál teljesült; a javaslat gombjánál 2/3 habozott |
| F3 paywall | igen | részben | részben | 2/3 félreértett egy feltételt |

---

## 4. Leletek súlyossági sorrendben

Skála (8.3 lecke): 4 kritikus, 3 súlyos, 2 közepes, 1 kozmetikai. A súlyosság a hatás, a gyakoriság és a helyreállíthatóság együttese. 3 fős mintán ez erős jelzés, nem bizonyíték.

### L1 – A javaslat fő gombjának következménye félreérthető · **3 (súlyos)**
- **Feladat:** F2 (döntés: mit próbál ki legközelebb).
- **Megfigyelés:** 2/3 résztvevő (R1, R3) megállt a „Kipróbálom a következő sessionben” gomb előtt; R3 csak moderátori kérdés után kattintott.
- **Bizonyíték:** R1: „Ez most átír valamit a setupban?”; R3: „Félek, hogy beállít valamit a játékban.”
- **Következmény:** a fő feladat utolsó lépése elakad, a felhasználó a setupja módosulásától tart (ez bizalmi kérdés).
- **Feltételezett ok:** a „Kipróbálom” ige cselekvést sugall a játékban; nincs kimondva, hogy az app csak megjegyzi a kanyart.
- **Javítási irány:** a felirat nevezze meg a valódi következményt („Fókuszba teszem a következő sessionre”), alatta segédszöveg: nem módosít semmit az iRacingben.

### L2 – A paywallnál nem látszik, mi marad ingyenes · **3 (súlyos)**
- **Feladat:** F3.
- **Megfigyelés:** 1/3 (R2) azt hitte, a kanyarlista is elvész fizetés nélkül; az ezt cáfoló segédszöveget nem vette észre.
- **Bizonyíték:** R2: „És ha nem fizetek, a kanyarlista is eltűnik?”
- **Következmény:** téves döntés az előfizetésről (nyomás alatt fizet, vagy otthagyja az appot), és sérül a bizalom (a 3. házi L2 tanulsága).
- **Feltételezett ok:** a megnyugtató információ 12 px-es, halvány segédszövegben van.
- **Javítási irány:** az ingyenesen megmaradó funkciók felsorolása törzsszövegben, elsődleges színnel, a zárolt funkció leírása fölött.
- **Miért 3, ha csak 1/3-nál fordult elő?** Pénzügyi döntést érint, és a következmény (felesleges fizetés vagy elpártolás) a felületen belül nem hozható helyre.

### L3 – Az első terhelés időpontja nem egyértelmű · **2 (közepes)**
- **Feladat:** F3.
- **Megfigyelés:** 1/3 (R3) úgy értette, a próba indításakor azonnal fizet; újraolvasás után kijavította.
- **Bizonyíték:** R3: „akkor most levonja a 2 500-at?”
- **Következmény:** bizonytalanság a próba indítása előtt; helyreállítható (a résztvevő maga korrigált).
- **Feltételezett ok:** a „7 napig ingyenes, utána 2 500 Ft/hó” mondat nem mondja ki, *mikor* történik a terhelés.
- **Javítási irány:** az első terhelés napját ki kell írni („az első terhelés a 8. napon”), az emlékeztető időpontjával együtt.

### L4 – A setup-címke nem tűnik fel a sessionlistában · **2 (közepes)**
- **Feladat:** F1.
- **Megfigyelés:** 2/3 (R1, R3) nem a listában találta meg a setupot; R3 segítséget kért.
- **Bizonyíték:** R1: „…a listában is ott volt, csak elsikkadt a sok szám között.”
- **Következmény:** lassabb tájékozódás; a felhasználó számára fontos információ (4. házi: „melyik setuppal ment a kör”) rejtve marad. Helyreállítható, mert az összefoglalóban megtalálható.
- **Feltételezett ok:** a címke kis, normál vastagságú szöveg, felirat nélkül (csak a setup neve).
- **Javítási irány:** „Setup:” előtag és kiemelt címkestílus.

### L5 – A pályatérkép kattinthatónak látszik, de zsákutca · **2 (közepes)**
- **Feladat:** F2.
- **Megfigyelés:** 1/3 (R2) a térképen kezdte; a 7. házi próbáján is előfordult ugyanez. Ez együtt 2 alkalom.
- **Bizonyíték:** R2: „A térképen szoktam kiválasztani a kanyart, a MoTeC-ben is így megy.”
- **Következmény:** egy felesleges kör (zsákutca, majd vissza); helyreállítható.
- **Feltételezett ok:** a keretes kártya és a felirat kattinthatóságot ígér (a jelző nem egyezik a viselkedéssel, 7.1 lecke).
- **Javítási irány:** a jelzőnek egyeznie kell a viselkedéssel. A térkép kanyarszámai legyenek kattinthatók, és vigyenek a kanyar részleteire, a felirat pedig mondja meg, mire kell kattintani.

### Pozitív megfigyelések (ezeket nem szabad elrontani)
- **P1:** a rangsorolt kanyarlista mellé írt időveszteség 3/3 résztvevőnek azonnal érthető volt; senki sem nyitott grafikont a kanyar megnevezéséhez.
- **P2:** a „Fő ok” doboz a csatornák előtt működik: 3/3-an innen olvasták ki az okot, a fő feladat mindenkinél 2 percen belül teljesült.
- **P3:** a siker képernyő visszaigazolása (R2) egyértelmű volt.

---

## 5. Kiválasztott javítások és indoklásuk

| Prioritás | Lelet | Javítás (a Finomított prototípus oldalon) | Miért ez a sorrend | Hogyan segíti a fő feladatot |
|---|---|---|---|---|
| 1 | L1 (3) | 03: „Fókuszba teszem a következő sessionre” + segédszöveg: „Csak az appban jelöljük meg: nem módosít semmit az iRacingben vagy a setupodban.” | Súlyos, a fő feladat utolsó lépését akasztja meg; olcsó (szövegmódosítás) | **Érthetőség:** a gomb a következményt nevezi meg (7.1 lecke: a jelentés egyezzen a viselkedéssel), és eloszlatja a setup módosulásától való félelmet. |
| 2 | L2 (3) | 05: „Ingyen is megmarad: a kanyarlista, az időveszteség és a fő ok.” törzsszövegben, elsődleges színnel | Súlyos, bizalmi és pénzügyi következményű; olcsó | **Érthetőség:** a döntéshez szükséges információ a döntés helyén, nem segédszövegben; nincs rejtett költség, ezzel elkerüli a megtévesztő mintát. |
| 3 | L3 (2) | 05: „…az első terhelés a 8. napon. 2 nappal a próba vége előtt e-mailben emlékeztetünk.” | Közepes, de szinte ingyen javítható, és L2-vel egy helyen van | **Érthetőség:** a feltétel konkrét időponttal, nem értelmezést igénylő mondattal. |
| 4 | L4 (2) | 01: a Session sor komponensben a setup-címke „Setup: …” előtagot és Címke kiemelt stílust kapott, elsődleges szövegszínnel | Közepes; komponensszintű, egy módosítás minden sorra hat | **Érthetőség és hozzáférhetőség:** a felirat megnevezi az adatot (nem kell kitalálni, mi az a „spa_race_v3”), és a vastagabb, kontrasztosabb szöveg gyorsabban olvasható. |
| 5 | L5 (2) | 02: a térkép kanyarszámaira kattintva a kanyar részletei nyílnak meg (prototípusban: Les Combes); a felirat: „Kattints egy kanyarszámra a részletekhez.” | Közepes; a jelző és a viselkedés eltérése | **Érthetőség:** a jelző és a viselkedés egyezik. A haladók megszokott belépési pontja működik, a kanyarlista megmarad az alapútnak. **Bizonytalan:** hogy a térkép jobb-e, mint a lista, azt újra kell tesztelni. |

Nem javítottam (ezek indokolt döntések):
- A grafikon-helyőrzőket R3 átugrotta. Ez nem hiba: a fő feladathoz nem kellenek. Ez a P2 megerősítése.
- Hangsúlyosabb paywall-ár: nem kell, F3-ban 3/3 helyesen mondta az árat.

---

## 6. Mini UI-irányelv (Figma: UI-irányelv oldal)

### Változók
- **Paletta** gyűjtemény (alapértékek, szerep nélkül):
  - szürke/0–900 (8 fokozat);
  - kék/300–700 (4 fokozat, elsődleges szín);
  - zöld, sárga, piros (400/700: állapotszínek).
- **Téma** gyűjtemény (szemantikus, két mód: **Sötét** alapértelmezett, **Világos**):
  - felület/háttér, oldalsáv, kártya, mélyített, kiemelt, keret, keret-erős;
  - szöveg/elsődleges, másodlagos, gombon;
  - művelet/elsődleges, művelet/link, fókusz;
  - állapot/siker, figyelmeztetés, hiba;
  - adat/saját kör, adat/referencia.
- **Térköz** gyűjtemény: 4, 8, 12, 16, 24, 32 px (térköz/0,5 … térköz/4). Az Auto Layout gap és padding értékekhez kötve.
- **A finomított képernyők** csak a Téma változóit és a szövegstílusokat használják. **Módváltás tesztje:** a „02 – Világos mód (módváltás teszt)” frame ugyanaz a képernyő Világos módra állítva, és minden elem követi a módot.

### Miért sötét az alapértelmezett?
R2 megfigyelése, és a 2. házi interjúi szerint a felhasználók elsötétített szobában, a szimulátor mellett, második monitoron használják az appot. Ez a használati környezetből következik, nem ízlésből.

### Kontraszt (számolva, WCAG 2.2 AA)
| Pár | Min. | Sötét | Világos |
|---|---|---|---|
| szöveg/elsődleges – felület/háttér | 4,5 | 16,61 | 16,61 |
| szöveg/elsődleges – felület/kártya | 4,5 | 13,83 | 17,96 |
| szöveg/másodlagos – felület/háttér | 4,5 | 9,61 | 9,63 |
| szöveg/másodlagos – felület/kártya | 4,5 | 8,00 | 10,41 |
| szöveg/másodlagos – felület/oldalsáv | 4,5 | 8,00 | 8,40 |
| szöveg/elsődleges – felület/kiemelt | 4,5 | 9,63 | 9,61 |
| szöveg/gombon – művelet/elsődleges | 4,5 | 6,31 | 5,57 |
| művelet/link – felület/háttér | 4,5 | 9,65 | 7,43 |
| művelet/link – felület/kártya | 4,5 | 8,03 | 8,03 |
| felület/keret – felület/háttér | 3 | 4,77 | 3,48 |
| felület/keret – felület/kártya | 3 | 3,97 | 3,77 |
| fókusz – felület/háttér | 3 | 9,65 | 7,43 |
| állapot/siker – felület/kártya | 3 | 6,75 | 6,08 |
| állapot/figyelmeztetés – felület/kártya | 3 | 8,91 | 6,65 |
| állapot/hiba – felület/kártya | 3 | 5,92 | 6,47 |
| adat/saját kör – felület/kártya | 3 | 5,25 | 5,57 |
| adat/referencia – felület/kártya | 3 | 8,00 | 3,77 |

Minden pár megfelel az AA szintnek, eltérés nincs.

**Megjegyzés:** a nem elemezhető (01b) és a párbeszédablak mögötti (04) elemek szándékosan halványítottak. Ezek tiltott vagy háttérbe szorult elemek, és a WCAG 1.4.3 kivételei közé tartoznak.

### Szövegstílusok (Inter)
| Stílus | Méret / vastagság / sorköz |
|---|---|
| Cím | 28 Bold / 125% |
| Alcím | 20 Bold / 130% |
| Kiemelt szöveg | 15 Semi Bold / 140% |
| Törzs | 14 Regular / 150% |
| Törzs kiemelt | 14 Semi Bold / 150% |
| Címke | 12 Regular / 140% |
| Címke kiemelt | 12 Semi Bold / 140% |
| Gomb felirat | 14 Semi Bold / 120% |

A 14 px-es törzsszöveg indoka: asztali, egérrel használt, adat-sűrű felület, vagyis a 6.3 lecke skálájának desktop-változata. 12 px a legkisebb méret, és csak kiegészítő információra használjuk.

### Elemszabályok (röviden; a teljes szöveg a Figmában)
- **Gomb:**
  - képernyőnként egy elsődleges, a felirat a következményt nevezi meg;
  - állapotok: alap, rámutatás, fókusz (2 px fókusz-keret), lenyomott, tiltott (indoklással), betöltés;
  - legalább 24×24 px kattintási felület.
- **Beviteli mező / szűrő:**
  - a címke a mező fölött;
  - a hiba keret + szöveges üzenet, ami megmondja a javítást;
  - a hibát sosem csak a szín jelzi.
- **Ikon:**
  - egy ikonkészlet;
  - kétértelmű műveletnél ikon + szöveg;
  - minden ikonnak van szöveges alternatívája.
- **Grafikon:** a saját kör folytonos, a referencia szaggatott vonal, így nem csak a szín különbözteti meg őket (WCAG 1.4.1).
- **Állapotüzenet:**
  - színes keret + ikon + szöveges cím;
  - siker után visszavonás, nem megerősítő ablak.
- **Prémium jelölés:**
  - a zárolt funkció a helyén, a feltételekkel együtt;
  - ami ingyen megmarad, az törzsszövegben szerepel (L2).
