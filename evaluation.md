Kedves Klára!

Gratulálok, hogy elkészültél az első heti beadandóval. Tudom, hogy rengeteg munkát és gondolatot tettél bele, bízom benne, hogy alkotás közben is sokat tanultál és fejlődtél.

Az értékelést több részre osztottam, hogy könnyen olvasható maradjon. Az értékelés alapjául a mi [mintamegoldásunk](https://codeberryschool.github.io/sitebuilder-practice-blog-hu/) szolgált, ezen felül a kódod szintaktikai helyességét [validátor](https://validator.w3.org) segítségével ellenőriztem.

A repozitoridat letöltöttem, megnyitottam VS Code szerkesztőben, és elindítottam egy LiveServer segítségével. Ezt követően megtekintettem Chrome böngészőben.


# Dizájn
A szemrevételezést során azt tapasztaltam, hogy a dizájnspecifikáció egyes részeit remekül valósítottad meg. A dizájntervben szereplő architektúra láthatóan visszaköszön a megoldásodban, helyesen olvastad le és alkalmaztad a színpalettát. Az egyes tartalmi elemek is megfelelnek annak, amit a feladat elvárt tőled.

Alaposabb megtekintést követően látható az is, hogy lényegi pontokban eltér a megoldásod az eredeti tervektől. A gombok megjelenése, a felső menüsor eltérő, a tipográfia több helyen nem egyezik. Ezen felül eltérőek a térközök, ettől bizonyos komponensek szétesnek (pl. Latest News), a "Categories" komponens pedig szintén jelentősen különbözik a mintamegoldásban is láthatótól.


# HTML
Ahogyan azt feljebb is írtam, a kódodat első lépésben megmutattam egy validátornak, és egy errort és több figyelmeztetést is mutatott. Az error onnan ered, hogy a nyelvi attribútumot nem helyesen adtad meg, hiányzik egy kötőjel. Helyesen:
```html
<html lang="en-US">
<!-- vagy -->
<html lang="en">
```
Azt mondhatom, hogy a kapott tervet sikeresen tudtad részeire bontani, azokból egy logikus és szépen struktúrált HTML architektúrát felépíteni. Ismered és használni is tudod a legfontosabb HTML elemeket, amelyeket ellátsz a szükséges és kötelező attribútumokkal.

Örültem annak, hogy használtál szemantikus HTML elemeket is, mint a `<header>`, `<nav>` vagy `<footer>`, bár a feladat lehetővé tette volna további elemek használatát is. Pl. a honlap fő egysége kerülhetett volna egy `<main>` elembe, a dátumok egy `<time>` elembe...stb. A szemantikus elemek használata több szempontból is előnyös. Egyrészt a keresőmotorok előnyben részesítik azokat az oldalakat, amelyek alkalmazzák ezeket, hiszen könnyebben azonosítják az egyes tartalmi elemeket. (Pl. a Google kereső is részben ezért is tudja kiemelni egy keresett étterem címét.) Mésrészt sok szemantikus elem rendelkezik olyan beépített funkcióval, amelyek segítik és támogatják a felhasználókat. Ha többet szeretnél megtudni ezekről az elemekről, akkor tudom javasolni ezt a [cikket](https://www.dofactory.com/html/semantics).

Remek, hogy több CSS fájlt is használtál - erről részletesebben majd a CSS szekcióban - és ezeket remekül be is importáltad a HTML kódodba. A következő fejlődési szint az lehet, ha ezeket nem közvetlenül ide, hanem egy `main.css` fájlba importálod be, és ide már csak az kerül be. Egyszerűen elegánsabb, ha a CSS architektúrád nem dagasztja a `<head>` elemet.

Jó gyakorlat, hogy a fejlesztés közben kommentekkel támogatod önmagad. Viszont ezeket érdemes törölni, mielőtt beküldöd a megoldásod. Jó alapelv, hogy legyen a HTML architektúrád letisztult, használj szemantikus elemeket, és akkor nincs igazán szükséged magyarázó kommentekre. Ebben a konkrét helyzetben nekem, mint kódot olvasó személynek, a kommentek nem mondanak semmit, inkább nehezítik, semmint segítik a megértést.


# CSS
A CSS kódodat, hasonlóan a HTML-hez, megmutattam a validátornak, és az bizony az egyik fájlban hibát talált. A `layout.css` 10. sorában a `border-radius` értéke előtt van egy felesleges pont:
```css
border-radius: .1.786rem;
/* HELYESEN */
border-radius: 1.786rem;
```

Örömmel láttam, hogy követted a OOCSS architektúrát, méghozzá remekül: szépen elkülönülnek az egyes területek. Kiválóan tudod alkalmazni a BEM struktúrát az osztályok elnevezésekor, ami mindenképpen egy elismerésre méltó készség. Használtál CSS resetet (`normalize.css`), ami már kifejezetten a professzionális weblapfejlesztés irányába mutat.

A kapott dizájnspecifikációt képes voltál elemeire bontani, és azokból egy ügyes CSS architektúrát felépíteni. Ismered és szintaktikailag helyesen használni is tudod a legfontosabb CSS szabályokat. A kódod olvashatóságát hasznos kommentekkel javítottad, ez pl. egy remek példa arra, amikor a komment nem hátráltat és nem is öncélú.

Eggyel szebb lehet a CSS architektúrád, ha a CSS resetet nem külön fileként, hanem egy CDN linken keresztül importálod a HTML `<head>` elemébe. Pl. a [Meyer-reset](https://cdnjs.com/libraries/meyer-reset) esetében valahogy így:
```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/meyer-reset/2.0/reset.min.css" integrity="sha512-NmLkDIU1C/C88wi324HBc+S2kLhi08PN5GDeUVVVC/BVt/9Izdsc9SVeVfA1UZbY3sHUlDSyRXhCzHfr6hmPPw==" crossorigin="anonymous" referrerpolicy="no-referrer" />
```
Ez vélhetően pontosan ugyanazt csinálja, mint a te `normalize.css` fájlod, de sokkal tisztább és egyértelműbb, hogy nem a te kódod, másoktól kölcsönzöd. (Ami teljesen megszokott a programozásban.) Így a CSS fájlokba már tényleg csak az kerülhet, amit te írtál.

Őszintén tisztelem azt, hogy felépítetted ezt a layoutot pusztán `float`-okat használva. Szerencsére van már modernebb és könnyebb megoldás egy honlap struktúrájának kialakítására, a flexbox és a grid. Javaslom, hogy legyél bátor és a kurzus részeként próbáld ki ezeket a technológiákat is.


# Pontszámok
[_szerzett pontok / maximális pontok_]

__dizájn__: 10 / 20 pont - minden lényegi eltérést után levontam 2-2 pontot, összesen 10 pontot.

__html__: 7 / 10 pont - a validátor által dobott error utána levontam 2 pontot, további 1 pontot a szemantikus elemek hiánya miatt.

__css__: 8 / 10 pont - a validátor error után levontam 2 pontot.

Összesen __25 pontot__ szereztél a maximális 40 pontból, ami egy __62,5%-os teljesítményt__ jelent. Gratulálok!


# Összegzés, javaslatok
Összességében azt mondhatom, hogy egy remek honlapot raktál össze. Pedig nem volt mindig könnyű dolgod vele, floatokból felépíteni egy honlapot igazán nemes kihívás. Ha megnézed, a legtöbb pontot most a pontatlanságok miatt veszítetted. Ezek egy részére megoldás lehet, ha egy könnyebben alkalmazható és pontosabb CSS technológát alkalmazol az oldal layoutjának felépítésekor, mint a flexbox és a grid.

Mindenképpen csak javasolni tudom, hogy használj validátort. Természetes jelenség, hogy sokórányi programozást követően már nem vesszük észre az apró elütéseket, hibákat a saját kódunkban. De nem is kell, mert erre van a validátor. Négy pontot (10%-ot) veszítettél olyan elütés miatt, amit ezzel a módszerrel ki lehet szűrni.

Ezek az apróságok azon a szinten, ahol te vagy, már igenis számítanak. Az már nem okoz gondot, hogy egy objektum orientált CSS archnitektúrát felépíts, ahogyan a BEM nevezéktan is a kisújjadban van. Éppen ezért számodra a következő lépés a finomhangolás, az apróságokra való tudatos odafigyelés. Biztos vagyok benne, hogy ez sem lesz számodra nehezebb, mint az eddigiek megtanulása. Szemmel láthatóan van hozzá érzéked. Szóval hajrá és csak így tovább! 
