# Žinomos problemos ir atviri klausimai

Įrašai iš 2026-11-10 patikros. Funkcinis kodas dėl jų nekeistas. Būsena „patvirtinta faile“ reiškia, kad tai matoma šaltinyje. Naršyklėje nepertikrinta.

## KI-001. Absoliutus peržiūros kelias dalyje puslapių

- Būsena: patvirtinta faile.
- `404.html` stiliai, skriptai ir beveik visos nuorodos naudoja `/revision-web-preview/...`.
- `privatumo-politika/index.html` nukreipia į `/revision-web-preview/privatumas.html`.
- Kiti puslapiai naudoja santykinius kelius.
- Dabartiniame GitHub Pages projekto URL šis prefiksas sutampa su svetainės keliu.
- Jei tas pats medis būtų patiektas domeno šaknyje, šie du puslapiai rodytų į neegzistuojantį kelią. Toks patiekimas dabar nesukonfigūruotas.

## KI-002. Kanoniniai adresai rodo į revision.lt, peržiūra yra github.io

- Būsena: patvirtinta faile.
- `canonical`, Open Graph ir `sitemap.xml` naudoja `https://revision.lt/`.
- Tie patys puslapiai turi `noindex,nofollow`, o `robots.txt` draudžia visą svetainę.
- Peržiūrai indeksavimas uždarytas. Perkeliant turinį į gyvą svetainę šiuos signalus reikia peržiūrėti atskira užduotimi. Gyvas DNS šioje patikroje nejudintas.

## KI-003. 404 ir privatumo puslapiai ant senesnio stilių rinkinio

- Būsena: patvirtinta faile.
- Turinio puslapiai krauna `p5.css`–`p72.css` ir rodo žymą „P8.3“.
- `404.html` ir `privatumas.html` to rinkinio nekrauna ir žymos „P8.3“ neturi.
- Ar tai sąmoningas palikimas, `UNKNOWN`. Vizualus skirtumas naršyklėje `NOT VERIFIED`.

## KI-004. Svetainės šaltinis yra vienas archyvas

- Būsena: patvirtinta saugyklos medyje.
- Nėra išpakuoto HTML medžio ir nėra generatoriaus konfigūracijos.
- Pakeitimo diff git istorijoje slepiasi `site.zip` viduje.
- Kaip archyvas surenkamas, `UNKNOWN`.

## KI-005. Užklausos serveris ne šioje saugykloje

- Būsena: klientas patvirtintas, serveris `NOT VERIFIED`.
- `assets/form.js` siunčia į `https://forma.revision.lt/send.php`.
- Pristatymas, CORS gamyboje, ribojimai ir duomenų saugojimas nepatikrinti.
- Privatumo tekstas teigia, kad serveris duomenų nesaugo. Tai ne serverio kodo patikra.

## KI-006. Gyvos svetainės saugyklos aprašas nesutampa su savininko sakiniu

- Būsena: atviras klausimas.
- Savininkas: gyva `revision.lt` yra `grantaspazera-dot/revision-web`, jos ir DNS neliesti be atskiro leidimo.
- GitHub API 2026-11-10: ta saugykla vieša, numatytoji šaka `main`, aprašymas „REVISION LT svetainės DEMO (peržiūra)“, `homepageUrl` tuščias.
- Saugyklos turinys ir DNS įrašai neskaityti. Kas iš tikrųjų aptarnauja `revision.lt`, yra `NOT VERIFIED`.
- Ši atmintis tos saugyklos nekeičia.

## KI-007. Nėra automatinių testų

- Būsena: patvirtinta. Testų katalogo ir testų komandų nėra.
- Regresija galima tik rankiniu peržiūros tikrinimu arba vėliau pridėjus testus.

## KI-008. Sitemap datos senesnės už HEAD

- Būsena: patvirtinta faile.
- `sitemap.xml` `lastmod` yra 2026-10-25 ir 2026-10-29. HEAD yra 2026-10-30.
- Ar po tų datų keitėsi į sitemap įtrauktų puslapių turinys, eilutė po eilutės `NOT VERIFIED`.

## KI-009. Juridinio asmens kodas nepaskelbtas

- Būsena: svetainės tekste nerasta. Reikšmė `UNKNOWN`.
- Tai nėra defektas, kol savininkas neprašo jo rodyti. Privatumo politikoje valdytojas nurodytas pavadinimu ir adresu.

## KI-010. Klientų ženklų naudojimo teisės

- Būsena: `NOT VERIFIED`.
- Poraštės ir logotipų failai rodo Barbora, Pigu.lt, Varlė, Ivabaltė, Kotryna Group, Esamda, Lietuvos oro uostai, Vilniaus viešasis transportas, Varžtų pasaulis, DS Smith.
- Ar yra leidimai juos rodyti, šioje saugykloje dokumentų nėra.

## KI-011. Nuotraukų ir AI vaizdų pilnas atitikimas taisyklei

- Būsena: dalinai patikrinta.
- Visi rasti `assets/img/ai/` `alt` tekstai prasideda žodžiu „Iliustracija“. Unikalių tokių `alt` reikšmių 5. Poraštėje yra „Dalis vaizdų – iliustracijos“.
- `assets/img/foto/` `alt` tekstai aprašo direktorių, mokymus ir etiketes. Ar failai yra tikros nuotraukos, pikselių lygmeniu nežiūrėta. `NOT VERIFIED`.
- `assets/img/koncepcija/` žymimi kaip koncepcija. Ekranų failų `assets/img/` šaknyje kilmė `NOT VERIFIED`.
- Taisyklė ateičiai: AI vaizdas negali būti pateiktas kaip tikras darbuotojas, klientas ar projektas. Žr. [MODULES/VAIZDAI.md](MODULES/VAIZDAI.md).
