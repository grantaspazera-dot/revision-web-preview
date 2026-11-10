# Modulis `publikavimas`

## 1. Paskirtis

Išleisti `site.zip` turinį kaip viešą REVISION LT svetainės peržiūrą per GitHub Pages. Šis modulis nevaldo gyvo `revision.lt` domeno.

## 2. Pagrindinės funkcijos

- Išpakuoti archyvą į `_site`.
- Įkelti Pages artefaktą.
- Publikuoti aplinkoje `github-pages`.
- Palikti `.nojekyll`, kad Pages nevykdytų Jekyll.
- `robots.txt` uždrausti visiems robotams visą medį.

## 3. Naudotojo eiga

Savininkas arba agentas pakeičia peržiūrą atskiroje šakoje ir atidaro pull request. Publikacija įvyksta tik po įtraukimo į `main` ir workflow paleidimo. Iki savininko leidimo į `main` nejungiama.

Push į šaką, kurios vardas nėra `main`, failo `.github/workflows/deploy.yml` trigerio `push.branches` neatitinka.

## 4. Įvestis ir išvestis

Įvestis: `site.zip` saugyklos šaknyje ir workflow failas.

Išvestis: GitHub Pages svetainė `https://grantaspazera-dot.github.io/revision-web-preview/`. API 2026-11-10: `build_type` yra `workflow`, šaltinio šaka `main`, `cname` yra `null`, HTTPS įjungtas.

`sitemap.xml` yra archyvo viduje ir vardija `https://revision.lt/` URL. Jis nėra šio modulių diegimo žemėlapis github.io adresu.

## 5. Failai

- `.github/workflows/deploy.yml`
- `site.zip`
- Archyvo viduje: `.nojekyll`, `robots.txt`, `sitemap.xml`, visas HTML ir `assets/`

Workflow žingsniai: `actions/checkout@v4`, `unzip` į `_site`, `actions/configure-pages@v5`, `actions/upload-pages-artifact@v3`, `actions/deploy-pages@v4`.

## 6. API

GitHub Actions ir GitHub Pages API. Kitų diegimo tiekėjų konfigūracijos nėra.

## 7. Duomenų bazė

Nėra.

## 8. Priklausomybės

- GitHub saugykla `grantaspazera-dot/revision-web-preview`
- Pages aplinka `github-pages`
- `site.zip` vientisumas

Gyva svetainė `grantaspazera-dot/revision-web` ir DNS nėra šio modulio dalis.

## 9. Teisės

Workflow turi `contents: read`, `pages: write`, `id-token: write`. Slaptažodžių ir raktų faile nėra.

`workflow_dispatch` leidžia rankinį paleidimą ir neturi `branches` filtro. Toks paleidimas iš ne `main` šakos gali publikuoti tos šakos medį. Įprastas šakos push to nedaro.

## 10. Klaidos ir ribos

- Sugadintas `site.zip` nutrauktų `unzip` žingsnį. Dabartinis archyvas 2026-11-10 išsiskleidžia, 196 failai.
- Nėra atskiro staging aplinkos vardo. Vienintelė Pages svetainė ir yra peržiūra.
- Kanoniniai URL vis tiek rodo į `revision.lt`. Žr. KI-002.
- 404 ir privatumo nukreipimas priklauso nuo kelio `/revision-web-preview/`. Žr. KI-001.

## 11. Testavimo scenarijai

- Patikrinti, kad `push` trigeris turi tik `main`.
- Patikrinti, kad dokumentacijos šaka nekeičia `deploy.yml`.
- Po sąmoningo `main` įtraukimo, atskira užduotimi, peržiūrėti Actions paleidimą ir peržiūros URL.

Šioje užduotyje workflow nekeistas, Actions ranka nepaleistas, `main` neatnaujintas.

## 12. Apribojimai

Diegimo konfigūracijos nekeisti dokumentacijos ar turinio užduotyse. DNS, pasirinktinis domenas ir kitos saugyklos keitimas reikalauja atskiro savininko patvirtinimo. Prieš `site.zip` turinio keitimą grįžimo taškas yra ankstesnis git commit.
