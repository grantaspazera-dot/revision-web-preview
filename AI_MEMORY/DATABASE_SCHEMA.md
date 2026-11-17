# Duomenų bazės schema

## Išvada

Šioje saugykloje duomenų bazės schemos nėra.

Patikra 2026-11-10, commit `53843f8`:

- Šaknyje nėra SQL, migracijų, ORM modelių, `prisma`, `sqlite`, `postgres` ar kitų schemos failų.
- Vieninteliai saugyklos failai iki šios atminties buvo `README.md`, `.github/workflows/deploy.yml` ir `site.zip`.
- `site.zip` tekstiniuose HTML, CSS, JS, `robots.txt` ir `sitemap.xml` nėra prisijungimo eilučių, SQL užklausų ir lentelių aprašų.
- Svetainė neturi naudotojų paskyrų ir serverio, kuris rašytų į duomenų bazę.

Lentelės, raktai, indeksai, apribojimai ir migracijos: nėra. Kurti jų iš standarto pavyzdžio negalima.

## Išorinis formos serveris

`assets/form.js` siunčia JSON į `https://forma.revision.lt/send.php`. To serverio saugykla, lentelės ir žurnalai šioje saugykloje neegzistuoja. Ar jis naudoja duomenų bazę, yra `NOT VERIFIED`.

`privatumas.html` (tekstas atnaujintas 2026-10-24) teigia, kad užklausos duomenys išsiunčiami el. paštu per UAB Bacloud serverį ir kad svetainė bei serveris tų duomenų nesaugo. Tai privatumo politikos sakinys, ne šioje saugykloje patikrinta serverio elgsena.

Kol formos serverio kodas nepatikrintas, jokia schema jam nepriskiriama.
