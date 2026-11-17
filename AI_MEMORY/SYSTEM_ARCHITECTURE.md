# Sistemos architektūra

Patikra: 2026-11-10, commit `53843f8`. Šaltiniai: saugyklos medis, `.github/workflows/deploy.yml`, GitHub Pages API, `site.zip` HTML, CSS ir JS. Išoriniai serveriai neatidaryti.

## Tipas

Statinė svetainė be kūrimo įrankio šioje saugykloje. Nėra `package.json`, testų, duomenų bazės kliento ir puslapių generatoriaus pėdsakų HTML komentaruose. Kaip `site.zip` surenkamas už šios saugyklos ribų, yra `UNKNOWN`.

GitHub Pages negeneruoja svetainės per Jekyll: archyve yra `.nojekyll`.

## Publikavimo srautas

```text
site.zip  →  actions/checkout@v4
          →  unzip į _site
          →  actions/configure-pages@v5
          →  actions/upload-pages-artifact@v3 (path: _site)
          →  actions/deploy-pages@v4
          →  https://grantaspazera-dot.github.io/revision-web-preview/
```

Workflow pavadinimas: „Deploy site to GitHub Pages“. Paleidimas:

- `push` tik į šaką `main`
- `workflow_dispatch` be šakų filtro

Leidimai: `contents: read`, `pages: write`, `id-token: write`. Lygiagretumas: grupė `pages`, `cancel-in-progress: true`. Aplinka: `github-pages`.

Push į ne `main` šaką šio trigerio neatitinka ir peržiūros puslapio neatnaujina. Rankinis `workflow_dispatch` gali būti paleistas iš kitos šakos. Šios atminties šaka to nenaudoja.

Šis srautas publikuoja peržiūrą. Jis nekeičia `revision.lt` DNS. DNS keitimas šioje saugykloje nekonfigūruotas.

## Vykdymo metu naršyklėje

Puslapiai yra ranka sudėti HTML dokumentai. Bendras karkasas kartojasi kiekviename puslapyje, ne per šablonų variklį.

Stiliai jungiami sluoksniais. Turinio puslapiai (`index.html`, paslaugų puslapiai, `apie-mus.html`, `kontaktai.html`, `izvalgos.html`, `revision-online.html`) krauna:

`fonts.css`, `style.css`, `p0.css`, `p4.css`, `p5.css`, `p5final.css`, `p6.css`, `p7.css`, `p71.css`, `p72.css`

`uzklausa.html` papildomai krauna `p1.css` ir `pack.css`.

`404.html` ir `privatumas.html` krauna senesnį rinkinį: `fonts.css`, `style.css`, `p0.css`, `p1.css`, `pack.css`, `p2.css`, `p3.css`, `p4.css`. Jie nekrauna `p5`–`p72`.

Skriptai:

- `assets/main.js` – mobilus meniu, sumažinto judesio paisymas, skaitiklių animacija. Komentare nurodyta, kad tinklo užklausų, slapukų ir saugyklos nėra.
- `assets/p4.js` – užklausos modalas. Nieko nesiunčia. „Tęsti“ atidaro `uzklausa.html?kryptis=…`.
- `assets/form.js` – tik `uzklausa.html`.

Šriftas: Barlow Semi Condensed, vietiniai `.woff2`, licencijos tekstas `assets/fonts/OFL.txt`. Išorinio šriftų CDN HTML ir JS paieškoje nerasta.

Spalvos baziniame `style.css`: `--brand:#115B87`, `--brand-light:#5BB4EA`. `p4.css` komentare tos pačios spalvos ir Barlow Semi Condensed.

## Duomenų srautai

### Puslapio skaitymas

Naršyklė gauna statinius failus iš GitHub Pages. Formos ir analitikos užklausos vien skaitant puslapį, pagal `main.js` ir `p4.js`, nevyksta.

### Užklausa

1. Modalas pasirenka kryptį ir atidaro `uzklausa.html?kryptis=` su viena iš reikšmių: `konsultacija`, `auditas`, `inventorizacija`, `mokymai`, `iranga`, `programa`.
2. `form.js` laiko būseną atmintyje. Slapukų ir `localStorage` nenaudoja. Yra paslėptas laukas `website` ir nuo atidarymo skaičiuojamas `elapsed`.
3. Siuntimas: `POST` JSON į `https://forma.revision.lt/send.php`, `mode: cors`, `credentials: omit`, laukimo riba 20 s.
4. Sėkmė kliento kode: JSON `ok`. Laukas `confirmation` gali būti `sent` arba `failed`.
5. Klientas atpažįsta HTTP 422, 429 ir 400 su `error: too_fast`.
6. Tinklo ar kitos nesėkmės atveju atidaromas `mailto:info@revision.lt` su paruoštu tekstu.

Serverio elgsena, laiškų pristatymas ir tai, ar serveris duomenis saugo, šioje saugykloje nepatikrinti. Privatumo puslapis teigia, kad siuntimą atlieka UAB Bacloud serveris ir kad svetainė bei serveris užklausų duomenų nesaugo. Tai publikavimo teksto teiginys. Serverio atžvilgiu `NOT VERIFIED`.

## Integracijos

| Integracija | Kur matoma | Būsena |
| --- | --- | --- |
| GitHub Pages | `deploy.yml`, Pages API | Konfigūracija patikrinta. Gyvas naršymas `NOT VERIFIED` |
| `forma.revision.lt/send.php` | `assets/form.js`, `privatumas.html` | Kliento sutartis patikrinta. Serveris `NOT VERIFIED` |
| `https://demo.revision.lt/` | Poraštės nuoroda | `NOT VERIFIED` |
| `https://revision.lt/` | `canonical`, Open Graph, `sitemap.xml` | URL įrašyti. Ar domenas aptarnauja šį turinį, `NOT VERIFIED` |
| LinkedIn, YouTube | Poraštė ir meniu | Viešos nuorodos. Profilių turinys `NOT VERIFIED` |
| `https://vdai.lrv.lt` | `privatumas.html` | Nuoroda į priežiūros instituciją |

Analitikos, žymų valdytojo ir slapukų įskiepių hostų HTML, CSS ir JS paieškoje nerasta. Poraštėje yra tekstas „Be slapukų ir sekimo įrankių“. Tai sutampa su atlikta hostų paieška. Pilnas pikselių lygio auditas neatliktas.

## Keliai

Turinio puslapiai naudoja santykinius URL (`paslaugos.html`, `assets/...`). Jie tinka GitHub Pages projekto keliui `/revision-web-preview/`.

`404.html` ir `privatumo-politika/index.html` naudoja absoliučius kelius `/revision-web-preview/...`. `privatumo-politika/index.html` yra `meta refresh` į tą kelią ir kanoninę nuorodą `https://revision.lt/privatumas.html`.

Kanoniniai ir Open Graph adresai rodo į `https://revision.lt/`, nors peržiūra draudžia indeksavimą. Sitemap `lastmod` yra 2026-10-25 arba 2026-10-29, o HEAD commit yra 2026-10-30.

## Ko architektūroje nėra

Nėra serverio šioje saugykloje, duomenų bazės, naudotojų sesijų, mokėjimų, turinio valdymo sistemos ir automatinio testų rinkinio. Inventorizacijos programa ir Android programėlė svetainėje aprašomos ir iliustruojamos ekranų vaizdais. Jų išeities kodas yra `UNKNOWN` vietoje, ne čia.

`revision-online.html` turi skyrių `id="kuriama"` su tekstu „Kuriama REVISION 2.0 programa (koncepcija)“. CSS komentaras `p71.css` skiria šią koncepciją nuo veikiančios REVISION ONLINE. 2.0 nėra aprašoma kaip išleista.
