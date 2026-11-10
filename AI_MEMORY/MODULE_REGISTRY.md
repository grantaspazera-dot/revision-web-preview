# Modulių registras

Patikra: 2026-11-10, commit `53843f8`. Moduliai atitinka šios svetainės peržiūros sandarą. Inventorizacijos programos modulių čia nėra ir jie nekuriami.

| Modulis | Paskirtis | Pagrindiniai failai `site.zip` viduje | Priklausomybės | Dokumentas |
| --- | --- | --- | --- | --- |
| `puslapiai` | Statiniai informaciniai puslapiai, bendras meniu, poraštė, peržiūros juosta | HTML puslapiai, `assets/main.js`, `assets/p4.js`, `assets/style.css`, `assets/p0.css`, `assets/p4.css`–`p72.css`, dalyje puslapių `p1.css`, `p2.css`, `p3.css`, `pack.css` | `vaizdai`, `publikavimas` | [MODULES/PUSLAPIAI.md](MODULES/PUSLAPIAI.md) |
| `uzklausa` | Krypties pasirinkimas ir užklausos išsiuntimas | `uzklausa.html`, `assets/form.js`, modalas `assets/p4.js` | `puslapiai`, išorinis `forma.revision.lt` | [MODULES/UZKLAUSA.md](MODULES/UZKLAUSA.md) |
| `vaizdai` | Logotipas, nuotraukos, iliustracijos, ekranų koncepcijos, klientų ženklai, OG paveikslas | `assets/brand/`, `assets/img/`, `assets/og-image.png` | `puslapiai` | [MODULES/VAIZDAI.md](MODULES/VAIZDAI.md) |
| `publikavimas` | Archyvo išpakavimas ir GitHub Pages | `site.zip`, `.github/workflows/deploy.yml`, archyvo `.nojekyll`, `robots.txt`, `sitemap.xml` | GitHub Actions, GitHub Pages | [MODULES/PUBLIKAVIMAS.md](MODULES/PUBLIKAVIMAS.md) |

## Sąsajos tarp modulių

- `puslapiai` įterpia `vaizdai` failus ir atidaro `uzklausa` per nuorodas bei `p4.js` modalą.
- `uzklausa` naudoja tą patį karkasą kaip `puslapiai` ir tą pačią peržiūros publikaciją.
- `publikavimas` išleidžia visą `site.zip` turinį vienu artefaktu. Atskiro modulio diegimo nėra.

## Sąmoningai nekurti įrašai

Standarto pavyzdyje minimi INVENTORY, LOCATIONS, PRODUCTS, REPORTS, USERS, WAREHOUSE ir AUDIT. Jie neegzistuoja šioje saugykloje. Paslaugų aprašai yra HTML puslapiai, ne atskiri programos moduliai.

`DEVELOPMENT_RULES.md` ir `SECURITY_RULES.md` nekurti. Taisyklės yra [`AGENTS.md`](../AGENTS.md). Privatumo elgsenos aprašas lieka `privatumas.html` ir [MODULES/UZKLAUSA.md](MODULES/UZKLAUSA.md).
