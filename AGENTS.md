# AGENTS.md

Instrukcijos agentams, dirbantiems su `grantaspazera-dot/revision-web-preview`.

Šis failas įtvirtina REVISION OS AI Development & Technical Memory Standard v1.0 (2026-11-08) darbo taisykles šiai saugyklai. Pilnas standarto tekstas į saugyklą neįkeltas. Techninė atmintis yra kataloge [`AI_MEMORY/`](AI_MEMORY/PROJECT_OVERVIEW.md). Prieš reikšmingą pakeitimą skaityk atmintį, tada patikrink realų kodą ar archyvą. Santrauka nėra kodo pakaitalas.

Patikros data: 2026-11-10. Bazinis commit: `53843f8` (`main`).

## Kas tai per saugykla

Tai UAB REVISION LT naujos svetainės peržiūra. Publikuojamas turinys yra statinis ir supakuotas faile `site.zip`. GitHub Actions workflow `.github/workflows/deploy.yml` išpakuoja archyvą ir perduoda jį GitHub Pages.

Viešas peržiūros adresas patikrintas GitHub Pages API: `https://grantaspazera-dot.github.io/revision-web-preview/`. Pasirinktinio domeno (`cname`) nėra.

Savininko teigimu gyva `revision.lt` svetainė yra atskira saugykla `grantaspazera-dot/revision-web`. Šioje darbo aplinkoje tos saugyklos turinys nebuvo tikrintas. 2026-11-10 GitHub API ta saugykla egzistuoja, jos aprašymas yra „REVISION LT svetainės DEMO (peržiūra)“. Ar `revision.lt` DNS rodo į ją, yra `NOT VERIFIED`. Žr. [AI_MEMORY/KNOWN_ISSUES.md](AI_MEMORY/KNOWN_ISSUES.md) KI-006.

## Privalomos savininko taisyklės

1. Prieš svetainės turinio keitimą palik grįžimo kelią: git šaka ir commit. Jei keičiamas `site.zip`, prieš tai turi būti atsekama ankstesnė archyvo versija git istorijoje.
2. Visi svetainės pakeitimai daromi šioje peržiūros saugykloje. Nekeisk `grantaspazera-dot/revision-web`, gyvos `revision.lt` svetainės ir DNS be atskiro savininko patvirtinimo.
3. `main` šakos push paleidžia peržiūros GitHub Pages publikavimą. Tai nėra gyvo `revision.lt` diegimas, bet tai viešas peržiūros atnaujinimas. Į `main` nejunk ir netrauk pakeitimų be aiškaus savininko leidimo.
4. Push į kitą šaką pagal dabartinį `.github/workflows/deploy.yml` diegimo nepaleidžia. Workflow failo nekeisk, jei užduotis nėra būtent publikavimo konfigūracija. `workflow_dispatch` šakų filtro neturi: rankinis paleidimas gali publikuoti pasirinktą šaką.
5. Dirbtinio intelekto sugeneruoti vaizdai negali būti pateikiami kaip tikri darbuotojai, tikri klientai ar tikri projektai. Katalogo `assets/img/ai/` vaizdai žymimi kaip iliustracijos. Naujiems tokiems vaizdams naudok aiškų „Iliustracija“ požymį ir nekurk melagingų atsiliepimų ar klientų istorijų.
6. Į dokumentaciją, commit žinutes ir atsakymus nekelk slaptažodžių, prieigos raktų, tokenų ir privačių prisijungimo duomenų. Vieši svetainės kontaktai, jau esantys HTML, nėra paslaptis.

## Ką skaityti prieš darbą

1. Šį failą.
2. [`AI_MEMORY/PROJECT_OVERVIEW.md`](AI_MEMORY/PROJECT_OVERVIEW.md)
3. [`AI_MEMORY/CURRENT_STATE.md`](AI_MEMORY/CURRENT_STATE.md)
4. Tik su užduotimi susijusį failą [`AI_MEMORY/MODULES/`](AI_MEMORY/MODULE_REGISTRY.md)
5. Tada realų susijusį turinį. Svetainės HTML, CSS ir JS yra `site.zip` viduje, ne išpakuoti šaknyje.

Jei atmintis nesutampa su archyvu ar konfigūracija, tikėk patikrintu failu, atnaujink atmintį ir nepatikrintus teiginius pažymėk `UNKNOWN` arba `NOT VERIFIED`.

## Darbo režimas

Laikykis standarto 4 skyriaus etapų. Režimą rinkis pagal riziką:

- FAST – izoliuotas, grįžtamas pakeitimas viename paviršiuje.
- STANDARD – vieno modulio elgsena, turinys ar sutartis.
- ARCHITECT – publikavimas, domenas, formos serveris, kelių modulių srautas, duomenų tvarkymas.

Nekeisk nesusijusių failų. Nedubliuok esamos dokumentacijos: [`README.md`](README.md) yra tik saugyklos pavadinimas, architektūra gyvena `AI_MEMORY/`. Planuojamos funkcijos neaprašyk kaip veikiančios.

Po reikšmingos užduoties atnaujink tik paveiktus atminties failus, pridėk įrašą [`AI_MEMORY/TASK_HISTORY/`](AI_MEMORY/TASK_HISTORY/) ir pabaigoje pateik standarto 10 skyriaus ataskaitą lietuvių kalba.

## Ko šioje saugykloje nėra

Čia nėra inventorizacijos programos, Android programėlės, duomenų bazės, ORM, migracijų ir naudotojų autentifikavimo kodo. Šabloninio standarto moduliai INVENTORY, LOCATIONS, PRODUCTS, REPORTS, USERS, WAREHOUSE ir AUDIT šiai svetainei nekuriami. Realūs moduliai išvardyti [`AI_MEMORY/MODULE_REGISTRY.md`](AI_MEMORY/MODULE_REGISTRY.md).

`AI_MEMORY/DEVELOPMENT_RULES.md` ir `AI_MEMORY/SECURITY_RULES.md` pirmojo etapo metu nekurti: atskirų tokių dokumentų saugykloje nebuvo, o privalomos taisyklės surašytos šiame faile ir privatumo puslapyje. Nekurk jų iš naujo, kol užduotis to aiškiai neprašo.

## Kalba ir žymos

Techninę atmintį rašyk lietuvių kalba. Failų, funkcijų, CSS klasių, URL ir commit identifikatorius palik tokius, kokie jie yra kode. Nepatikrintą faktą žymėk `UNKNOWN` arba `NOT VERIFIED`.
