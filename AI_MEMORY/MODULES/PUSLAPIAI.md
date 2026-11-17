# Modulis `puslapiai`

## 1. Paskirtis

Statiniai lietuviški REVISION LT svetainės puslapiai ir juos jungiantis karkasas: antraštė, meniu, poraštė, peržiūros juosta, stiliai ir `main.js` bei `p4.js`.

## 2. Pagrindinės funkcijos

- Parodyti paslaugas, programą, įmonės informaciją ir kontaktus.
- Leisti pereiti tarp puslapių ir paskambinti.
- Atidaryti užklausos modalą. Siuntimas priklauso moduliui `uzklausa`.
- Pažymėti medį kaip peržiūrą ir uždrausti indeksavimą.

## 3. Naudotojo eiga

Lankytojas atidaro pradžią, renkasi paslaugą iš meniu arba turinio, skaito skyrius ir eina į užklausą, kontaktus arba `tel:` nuorodą. Tiesioginio paskyros kūrimo nėra.

## 4. Įvestis ir išvestis

Įvestis yra URL. Išvestis yra HTML. Formos duomenų šis modulis nesaugo.

## 5. Failai

Visi keliai yra `site.zip` viduje.

| Failas | Antraštė | Peržiūros žyma |
| --- | --- | --- |
| `index.html` | Sandėlio valdymas ir inventorizacija | P8.3 |
| `paslaugos.html` | Sandėlio valdymo ir inventorizacijos paslaugos | P8.3 |
| `konsultacijos-ir-auditas.html` | Sandėlio valdymo konsultacijos ir auditas | P8.3 |
| `procesu-optimizavimas.html` | Sandėlio procesų optimizavimas | P8.3 |
| `inventorizacija.html` | Prekių, atsargų ir turto inventorizacija | P8.3 |
| `mokymai-ir-iranga.html` | Inventorizacijos mokymai ir įrangos nuoma | P8.3 |
| `revision-online.html` | REVISION ONLINE – inventorizacijos programa | P8.3 |
| `apie-mus.html` | Apie mus – inventorizacijos ekspertai | P8.3 |
| `kontaktai.html` | Kontaktai – susisiekime | P8.3 |
| `izvalgos.html` | Įžvalgos apie inventorizaciją ir sandėlį | P8.3 |
| `privatumas.html` | Privatumo politika | be P8.3 |
| `404.html` | Puslapis nerastas | be P8.3, absoliutūs keliai |
| `privatumo-politika/index.html` | Nukreipimas į privatumo politiką | be P8.3, absoliutus kelias |

`uzklausa.html` priklauso moduliui `uzklausa`, bet naudoja tą patį karkasą.

Meniu punktų, patikrintų `index.html`: Paslaugos, Konsultacijos ir auditas, Optimizavimas, Inventorizacija, Mokymai ir įranga, REVISION ONLINE, Kontaktai, skambutis, „Aptarti poreikį“.

Poraštėje papildomai yra `apie-mus.html`, `izvalgos.html`, `uzklausa.html`, `privatumas.html`, `https://demo.revision.lt/`, LinkedIn ir YouTube.

`izvalgos.html` aprašas sako, kad temos ruošiamos. Puslapis nėra tinklaraščio variklis.

`revision-online.html` skyrius `id="kuriama"` pavadintas „Kuriama REVISION 2.0 programa (koncepcija)“. Tai koncepcijos skyrius, ne atskira veikianti programa šioje saugykloje.

## 6. API

Savo API nėra. `main.js` tinklo užklausų nedaro.

## 7. Duomenų bazė

Nėra. Žr. [DATABASE_SCHEMA.md](../DATABASE_SCHEMA.md).

## 8. Priklausomybės

- `vaizdai` – logotipas, hero ir kortelių paveikslai.
- `publikavimas` – kad failai pasiektų peržiūros URL.
- `uzklausa` – modalas ir formos puslapis.

## 9. Teisės

Vieši puslapiai be autentifikavimo. Privatumo valdytojas pagal `privatumas.html`: REVISION LT, UAB, R. Kalantos g. 119, Kaunas, info@revision.lt, +370 615 53311. Politika atnaujinta 2026-10-24.

## 10. Klaidos ir ribos

- Nerastam keliui skirtas `404.html`. Jo nuorodos užkoduotos su `/revision-web-preview/`. Žr. KI-001.
- `privatumo-politika/index.html` yra tik nukreipimas, ne antras politikos tekstas.
- 404 ir privatumo stilių rinkinys skiriasi nuo P8.3 puslapių. Žr. KI-003.
- Kanoniniai URL rodo į `revision.lt`. Žr. KI-002.

## 11. Testavimo scenarijai

Automatinių testų nėra. Rankinei peržiūrai: atidaryti pradžią projekto kelyje, pereiti meniu, atidaryti modalą, atidaryti neegzistuojantį kelią, atidaryti `privatumo-politika/`. Šioje užduotyje naršyklėje nevykdyta.

## 12. Apribojimai

Turinys redaguojamas tik per `site.zip`. Šablonų variklio nėra, todėl karkasas pakartotas kiekviename HTML. Vieno karkaso pakeitimas reiškia visų puslapių atnaujinimą archyve.
