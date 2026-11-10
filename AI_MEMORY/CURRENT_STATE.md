# Dabartinė būsena

Patikros data: 2026-11-10. Šaltinis: vietinė `main` kopija, sutampanti su `origin/main`.

## Versijos ir identifikatoriai

| Objektas | Reikšmė |
| --- | --- |
| Saugykla | `grantaspazera-dot/revision-web-preview` |
| Numatytoji šaka | `main` |
| HEAD | `53843f82851bd47e419f5e90edfb0e4463036fef` |
| HEAD žinutė | P8.3 preview (noindex) |
| HEAD data | 2026-10-30 20:59:39 +0200 |
| Darbo kopija prieš šią atmintį | švari |
| Svetainės žyma HTML juostoje | „PERŽIŪRA. Ne gamybinė versija · P8.3“ turinio puslapiuose |
| `404.html`, `privatumas.html`, `privatumo-politika/index.html` | juosta be „P8.3“ |
| Programos paketo versija | nėra. `package.json` nėra |
| Actions | `checkout@v4`, `configure-pages@v5`, `upload-pages-artifact@v3`, `deploy-pages@v4` |
| GitHub Pages | `build_type: workflow`, šaltinio šaka `main`, `cname: null`, HTTPS įjungtas |
| Peržiūros URL | `https://grantaspazera-dot.github.io/revision-web-preview/` |
| Privatumo teksto data | 2026-10-24, kaip parašyta `privatumas.html` |
| Sitemap `lastmod` | 2026-10-25 arba 2026-10-29 |

Nuo 2026-10-30 iki patikros dienos naujų commit šioje šakoje nebuvo. Ar GitHub Pages spėjo publikuoti `53843f8`, naršyklėje nežiūrėta. `NOT VERIFIED`.

## Veikiantys komponentai pagal kodą

- Statiniai puslapiai ir santykinės navigacijos nuorodos turinio puslapiuose.
- Meniu skriptas ir užklausos modalas.
- Užklausos kliento logika su išoriniu POST ir `mailto` atsarga.
- Peržiūros publikavimo workflow iš `main`.
- Indeksavimo draudimas `robots.txt` ir `noindex,nofollow`.

Šie punktai patikrinti skaitant failus. Automatiniai testai neegzistuoja. Naršyklės scenarijai šioje užduotyje nepaleisti.

## Apribojimai

- Publikuojamas medis yra vienas `site.zip`. Išpakuoto šaltinio git medyje nėra.
- Forma priklauso nuo išorinio serverio, kurio čia nėra.
- Kanoniniai adresai rodo į `revision.lt`, o peržiūra yra `github.io` kelyje `/revision-web-preview/`.
- `404.html` ir privatumo nukreipimas užkoduoti su `/revision-web-preview/`.
- Gyvos svetainės saugyklos turinys ir DNS šioje aplinkoje netikrinti.
- Juridinio asmens kodas svetainėje neįrašytas. `UNKNOWN`.

## Žinomos spragos

Pilnas sąrašas: [KNOWN_ISSUES.md](KNOWN_ISSUES.md).

## Šaltiniai

- Saugyklos failai `README.md`, `.github/workflows/deploy.yml`, `site.zip` (196 failai). Tekstiniai failai laikinai išpakuoti skaitymui ir į saugyklą neįrašyti.
- `git log` nuo `be08d32` iki `53843f8`.
- GitHub API: šios saugyklos metaduomenys ir Pages objektas.
- GitHub API: `grantaspazera-dot/revision-web` tik pavadinimas, numatytoji šaka `main` ir aprašymas „REVISION LT svetainės DEMO (peržiūra)“. Turinys neskaitytas.
- Savininko 2026-11-10 nurodymas: peržiūra, gyva svetainė kitoje saugykloje, atsarginė kopija, DNS tik su atskiru leidimu, AI vaizdai nėra tikri darbuotojai ar projektai. DNS ir kitos saugyklos turinys pagal šį nurodymą neperrašyti kaip patikrinti faktai ten, kur API ar failai jų nepatvirtina.
