# TASK 2026-11-10-01 – Techninės atminties pirmas įdiegimas

- Data: 2026-11-10
- Būsena: atlikta dokumentacijos apimtyje
- Režimas: STANDARD

## Tikslas

Parengti REVISION OS AI Development & Technical Memory Standard v1.0 techninę atmintį šiai peržiūros saugyklai. Funkcinio kodo nekeisti.

## Pradinė problema

Saugykloje nebuvo `AGENTS.md` ir `AI_MEMORY/`. Vienintelis dokumentas buvo vienos eilutės `README.md`. Svetainės medis yra `site.zip`, todėl be atminties kitas agentas neturi patikrinto žemėlapio.

## Atlikti pakeitimai

Perskaityta saugyklos struktūra, workflow, git istorija, GitHub Pages API ir `site.zip` tekstiniai failai. Sukurta atmintis pagal rastą struktūrą. Duomenų bazės schemos nėra, tai įrašyta atskirai. `site.zip`, HTML, CSS, JS ir `deploy.yml` nekeisti.

## Pakeisti failai

- `AGENTS.md` (naujas)
- `README.md` (pridėtos nuorodos, antraštė palikta)
- `AI_MEMORY/PROJECT_OVERVIEW.md`
- `AI_MEMORY/SYSTEM_ARCHITECTURE.md`
- `AI_MEMORY/DATABASE_SCHEMA.md`
- `AI_MEMORY/MODULE_REGISTRY.md`
- `AI_MEMORY/CURRENT_STATE.md`
- `AI_MEMORY/CHANGELOG.md`
- `AI_MEMORY/KNOWN_ISSUES.md`
- `AI_MEMORY/MODULES/PUSLAPIAI.md`
- `AI_MEMORY/MODULES/UZKLAUSA.md`
- `AI_MEMORY/MODULES/VAIZDAI.md`
- `AI_MEMORY/MODULES/PUBLIKAVIMAS.md`
- `AI_MEMORY/TASK_HISTORY/2026-11-10-technine-atmintis.md`

## Paveikti moduliai

Dokumentuoti `puslapiai`, `uzklausa`, `vaizdai`, `publikavimas`. Jų elgsena nepakeista.

## API / duomenų bazės pakeitimai

Nėra.

## Atlikti testai ir rezultatai

- `unzip -t` ir tekstinių failų skaitymas iš `site.zip`: archyvas skaitomas, 196 failai.
- Workflow perskaitytas: `push` trigeris tik `main`.
- GitHub Pages API: peržiūros URL ir tuščias `cname`.
- Po dokumentų sukūrimo tikrinta, kad diff neliečia `site.zip` ir `.github/`.
- Naršyklės testai, formos siuntimas, Actions paleidimas ir DNS užklausos nevykdyti.

## Atnaujinta dokumentacija

Visa šios užduoties apimtis ir yra dokumentacija. `DEVELOPMENT_RULES.md` ir `SECURITY_RULES.md` nekurti.

## Likusios problemos

KI-001–KI-011 faile `AI_MEMORY/KNOWN_ISSUES.md`. Svarbiausi atviri klausimai: gyvos svetainės saugykla ir DNS `NOT VERIFIED`, formos serveris `NOT VERIFIED`, archyvo surinkimo būdas `UNKNOWN`.

## Kitas rekomenduojamas žingsnis

Savininkui peržiūrėti šią atmintį ir KI-006. Kito funkcionalaus svetainės keitimo nepradėti, kol jis nepatvirtintas. Į `main` nejungti be atskiro leidimo.
