# Projekto apžvalga

Patikra: 2026-11-10. Git HEAD, nuo kurio sudaryta atmintis: `53843f8` (2026-10-30, „P8.3 preview (noindex)“). Žr. [CURRENT_STATE.md](CURRENT_STATE.md).

## Paskirtis

Ši saugykla laiko naujos REVISION LT svetainės peržiūrą. Svetainė pristato UAB REVISION LT veiklą: inventorizacijos paslaugas, sandėlio valdymo konsultacijas ir auditą, procesų optimizavimą, mokymus, skenerių bei kitos įrangos nuomą, REVISION ONLINE programą ir Android programėlę.

Svetainė yra statinė. Publikavimą atlieka GitHub Pages. Programos, programėlės ir formos serverio išeities kodas šioje saugykloje nėra.

## Organizacija svetainės tekste

Iš `site.zip` HTML, patikrinta 2026-11-10:

- Pavadinimas svetainėje: REVISION LT, UAB. Juridinio asmens kodas puslapiuose nerastas. `UNKNOWN`.
- Adresas: R. Kalantos g. 119, Kaunas.
- Telefonas: +370 615 53311.
- El. paštas: info@revision.lt.
- Darbo laikas `kontaktai.html`: dirbama be išeiginių, išskyrus didžiąsias šventes ir kelias šventines dienas. Inventorizacijos laikas derinamas individualiai.
- Vieši profiliai poraštėje: Granto Pažėros LinkedIn ir REVISION LT YouTube kanalas.
- Portraukų `alt` tekstuose minimas direktorius Grantas Pažėra. Ar nuotraukos yra tikros, šioje patikroje pagal failo turinį nevertinta. `NOT VERIFIED`.

## Naudotojai

- Potencialus klientas skaito paslaugas ir pateikia užklausą.
- Grįžtantis lankytojas skambina arba rašo tiesiogiai.
- Savininkas ir agentai rengia peržiūrą šioje saugykloje, prieš bet kokį gyvos svetainės keitimą.

Prisijungimo, paskyrų ir administravimo sąsajos svetainėje nėra.

## Pagrindinės funkcijos

- Informaciniai puslapiai lietuvių kalba (`lang="lt"`).
- Bendras meniu, poraštė, skambinimo nuoroda ir užklausos langas.
- Daugiapakopė užklausos forma `uzklausa.html`, siunčiama į išorinį `https://forma.revision.lt/send.php`. Serverio kodas šioje saugykloje nėra. Pristatymas `NOT VERIFIED`.
- Peržiūros juosta „PERŽIŪRA. Ne gamybinė versija“. Daugelyje puslapių pridėta „P8.3“.
- Indeksavimo ribojimas: visuose patikrintuose HTML yra `noindex,nofollow`, `robots.txt` turi `Disallow: /`.

## Aukšto lygio struktūra

```text
README.md                          vienos eilutės pavadinimas ir nuorodos
AGENTS.md                          agentų taisyklės
AI_MEMORY/                         techninė atmintis
.github/workflows/deploy.yml       GitHub Pages publikavimas iš main
site.zip                           visas publikuojamas svetainės medis
```

`site.zip` šaknis, 196 failai, išpakuota patikrai 2026-11-10, į git darbo medį negrąžinta:

- 14 HTML puslapių, tarp jų `privatumo-politika/index.html`
- `assets/` stiliai, šriftai, skriptai, ženklas, nuotraukos ir iliustracijos
- `robots.txt`, `sitemap.xml`, `.nojekyll`

Moduliai: [MODULE_REGISTRY.md](MODULE_REGISTRY.md).

## Aplinkos

| Aplinka | Kas patikrinta | Kas ne |
| --- | --- | --- |
| Ši saugykla `revision-web-preview` | `main` = `53843f8`, švari darbo kopija patikros pradžioje | — |
| GitHub Pages peržiūra | API: workflow build, šaka `main`, URL `https://grantaspazera-dot.github.io/revision-web-preview/`, `cname` tuščias, HTTPS įjungtas | Ar šiuo metu naršyklėje rodomas būtent `53843f8`, `NOT VERIFIED` |
| Gyva `revision.lt` | Kanoniniai URL ir `sitemap.xml` rodo į `https://revision.lt/` | DNS ir gyvos svetainės turinys `NOT VERIFIED`. Savininko teigimu tai kita saugykla |
| `demo.revision.lt` | Nuoroda poraštėje „Išbandyti demo“ | Turinys `NOT VERIFIED` |
| `forma.revision.lt` | Naršyklės klientas `assets/form.js` | Serveris `NOT VERIFIED` |

## Kas jau buvo dokumentuota

Prieš šią atmintį saugykloje buvo tik [`README.md`](../README.md) su antrašte ir deploy workflow be atskiro architektūros aprašo. Turinio dokumentacija yra pačiuose HTML puslapiuose. Šis katalogas jų nekartoja: puslapių sąrašas ir elgsena aprašyti [MODULES/PUSLAPIAI.md](MODULES/PUSLAPIAI.md).

## Savininko ribos

Svetainės keitimai lieka peržiūroje. Gyva svetainė ir DNS neliečiami be atskiro patvirtinimo. Atsarginis kelias prieš turinio keitimą yra git istorija. Dirbtinio intelekto vaizdai neteikiami kaip tikri žmonės ar projektai. Plačiau: [`AGENTS.md`](../AGENTS.md).
