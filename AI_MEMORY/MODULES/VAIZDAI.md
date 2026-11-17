# Modulis `vaizdai`

## 1. Paskirtis

Laikyti svetainės ženklą, šriftus, nuotraukas, iliustracijas, programos ekranų vaizdus ir klientų logotipus. Modulis neturi vykdomosios logikos.

## 2. Pagrindinės funkcijos

- Logotipas antraštėje ir SVG piktograma.
- Hero ir kortelių paveikslai `picture` elementuose, AVIF ir WebP.
- Koncepcijos ekranai skyriuje apie kuriamą REVISION 2.0.
- Klientų ženklai.
- Open Graph paveikslas.

## 3. Naudotojo eiga

Lankytojas paveikslus mato puslapiuose. Atskiro galerijos įrankio nėra.

## 4. Įvestis ir išvestis

Įvesties nėra. Išvestis yra statiniai failai.

## 5. Failai `site.zip` viduje

| Vieta | Kas ten yra pagal kelius ir `alt` | Pastaba |
| --- | --- | --- |
| `assets/brand/` | `revision-logo-horizontal.svg`, `revision-logo-horizontal-white.svg`, `revision-symbol.svg` | Ženklas |
| `assets/img/ai/` | `ai01`, `ai08`, `ai09`, `ai10`, `ai12` rinkiniai 480, 960, 1600, AVIF ir WebP | `alt` prasideda „Iliustracija“ |
| `assets/img/foto/` | `f09`, `f10`, `g1`–`g7` rinkiniai | `alt` aprašo žmones, mokymus, etiketes. Tikrumas `NOT VERIFIED` |
| `assets/img/koncepcija/` | `m-a…`, `m-b…`, `m-e…` ekranų failai | `alt` prasideda „Koncepcija“ |
| `assets/img/logos/` | `barbora`, `ds-smith`, `esamda`, `ivabalte`, `kotryna-group`, `lietuvos-oro-uostai`, `pigu`, `varle`, `varztu-pasaulis`, `vilniaus-viesasis-transportas` | Naudojimo teisės `NOT VERIFIED` |
| `assets/img/` šaknis | `app-android-lokacijos.webp`, `app-web-*.webp`, `ri2-android-rezultatai.webp`, `ri2-web-vadovas.webp`, `demo-v4-vadovo.webp`, `grantas-pazera-portretas.webp` | Ekranų ir portreto kilmė `NOT VERIFIED` |
| `assets/og-image.png` | 1200×630 pagal meta žymas | Failo turinys pikselių lygmeniu nežiūrėtas |
| `assets/fonts/` | Barlow Semi Condensed 300–700, latin ir latin-ext, `OFL.txt` | Vietiniai šriftai |

Archyve yra 64 AVIF, 83 WebP, 1 PNG, 3 SVG ir 10 WOFF2. AVIF, WebP, PNG ir SVG yra paveikslai bei ženklas. WOFF2 yra šriftai.

## 6. API

Nėra.

## 7. Duomenų bazė

Nėra.

## 8. Priklausomybės

Puslapiai nurodo failus santykiniais keliais. `404.html` nurodo ženklą ir stilius absoliučiu `/revision-web-preview/` keliu.

## 9. Teisės ir pateikimo taisyklė

Savininko taisyklė: dirbtinio intelekto sugeneruotas vaizdas negali būti pateiktas kaip tikras darbuotojas, tikras klientas ar tikras projektas.

Dabartiniame HTML visi rasti `assets/img/ai/` paveikslų `alt` prasideda žodžiu „Iliustracija“. Poraštėje yra „Dalis vaizdų – iliustracijos“. Pilnas vizualus patikrinimas, ar kuris nors AI failas panaudotas be šio žodžio kitoje žymoje, atliktas pagal `img alt` paiešką, ne pagal kiekvieną `picture` `source`. Nauji AI vaizdai dedami į `assets/img/ai/` ir gauna „Iliustracija“ `alt`. Jų negalima dėti į `assets/img/foto/` ir negalima aprašyti kaip REVISION darbuotojų, klientų objektų ar įvykusių projektų.

Koncepcijos ekranai lieka pažymėti kaip koncepcija. `p71.css` komentaras skiria „REVISION 2.0 (koncepcija)“ nuo veikiančios REVISION ONLINE.

Klientų logotipų teisės saugykloje neįrodytos. Naujų klientų ženklų nedėti be savininko patvirtinimo.

Šriftų licencija yra `assets/fonts/OFL.txt`. Jos teksto čia nekopijuojame.

## 10. Klaidos ir ribos

OG `url` rodo į `https://revision.lt/assets/og-image.png`, ne į github.io peržiūrą. Jei peržiūra dalijama socialiniuose tinkluose, paveikslas imamas nuo `revision.lt`. Ar tas failas ten yra, `NOT VERIFIED`.

## 11. Testavimo scenarijai

Patikrinti, kad kiekvienas `assets/img/ai/` `img` turi `alt`, prasidedantį „Iliustracija“, ir kad 2.0 skyrius vis dar turi koncepcijos požymį. Šioje užduotyje tai atlikta tekstine paieška, ne naršyklėje.

## 12. Apribojimai

Vaizdų autorius ir gamybos įrankis failuose neįrašyti. Katalogo pavadinimas `ai` ir `alt` priešdėlis yra turimas įrodymas, ne EXIF auditas. Nuotraukų `foto/` tikrumas neįrodytas ir nepaneigtas.
