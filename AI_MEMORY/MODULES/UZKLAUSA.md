# Modulis `uzklausa`

## 1. Paskirtis

Surinkti paslaugos kryptį, poreikio atsakymus ir kontaktus bei perduoti užklausą REVISION LT. Atsakymą, pagal `uzklausa.html` aprašą, rengia žmogus.

## 2. Pagrindinės funkcijos

- Modalas visuose puslapiuose, kurie krauna `assets/p4.js`, pasirenka vieną kryptį.
- `uzklausa.html` ir `assets/form.js` veda keturių etapų vedlį: kryptis, poreikis, projektas ir kontaktai, patvirtinimas.
- Siuntimas į `https://forma.revision.lt/send.php`.
- Nepavykus tinklui – paruoštas laiškas `mailto:info@revision.lt`.

## 3. Naudotojo eiga

1. Pasirenka kryptį modale arba tiesioginėje nuorodoje `uzklausa.html?kryptis=`.
2. Atsako į krypties klausimus. Dalis klausimų nebūtini. Privalomi pažymėti `req`.
3. Užpildo įmonę, vardą ir bent el. paštą arba telefoną.
4. Peržiūri suvestinę ir siunčia.
5. Mato patvirtinimą arba prašymą išsiųsti laišką pačiam.

Kryptys kode: `konsultacija`, `auditas`, `inventorizacija`, `mokymai`, `iranga`, `programa`.

## 4. Įvestis ir išvestis

JSON kūnas, sudarytas `form.js` funkcijoje `finish`:

- `direction` – krypties pavadinimas
- `answers` – atsakymų tekstas
- `company`, `name`, `email`, `phone`, `comment`
- `marketing` – loginis naujienų sutikimas, neprivalomas
- `website` – paslėptas laukas, skirtas palikti tuščią
- `elapsed` – sekundės nuo skripto starto

Sėkmės požymis kliente: JSON `ok`. Papildomai skaitomas `confirmation` (`sent` arba `failed`) ir klaidoms `error === "too_fast"`.

## 5. Failai

- `uzklausa.html`
- `assets/form.js`
- `assets/p4.js` ir modalas, pakartotas puslapių HTML
- Stiliai: bendras P8.3 rinkinys ir papildomai `p1.css`, `pack.css`

## 6. API

Vienintelė išorinė sąsaja:

`POST https://forma.revision.lt/send.php`

`Content-Type: application/json`, `mode: cors`, `credentials: omit`, nutraukimas po 20 s.

Kliento reakcijos: `ok`, HTTP 422, HTTP 429, HTTP 400 su `too_fast`, kitu atveju `mailto`.

Serverio implementacija, CORS antraštės ir tikras laiško gavėjas šioje saugykloje nepatikrinti. `NOT VERIFIED`. Komentaras `form.js` ir `privatumas.html` sako, kad laiškas eina į info@revision.lt, o nurodžius el. paštą siunčiamas patvirtinimas klientui, per UAB Bacloud serverį.

## 7. Duomenų bazė

Šiame modulyje schemos nėra. Privatumo tekstas teigia, kad svetainė ir serveris užklausos duomenų nesaugo, o susirašinėjimas saugomas ne ilgiau kaip 3 metus nuo paskutinio kontakto. Serverio pusė `NOT VERIFIED`. Žr. [DATABASE_SCHEMA.md](../DATABASE_SCHEMA.md).

## 8. Priklausomybės

- `puslapiai` – karkasas ir modalas.
- Išorinis `forma.revision.lt`.
- Lankytojo pašto programa `mailto` atsargai.
- `privatumas.html` – nuoroda iš formos.

## 9. Teisės

Forma vieša. Rinkodaros varnelė neprivaloma. Privalomi įmonės pavadinimas ir vardas. El. paštas arba telefonas būtinas bent vienas. Jei bendravimo būdas yra pasiūlymas el. paštu, el. paštas tampa būtinas. Duomenų valdytojas nurodytas privatumo politikoje. Atskiro prisijungimo nėra.

## 10. Klaidos ir ribos

- Tuščia kryptis modale: tekstas „Pasirinkite vieną kryptį.“
- Neteisingas el. paštas, per trumpas vardas ar kiti laukai: klaidos prie laukų. Tikslus visų pranešimų sąrašas yra `form.js` `validate` dalyje.
- 422: prašoma patikrinti kontaktus.
- 429: per daug užklausų, rodomi tiesioginiai kontaktai.
- `too_fast`: prašoma palaukti.
- Tinklo klaida: laiškas paruošiamas, bet neišsiunčiamas, kol žmogus nepaspaudžia siuntimo pašto programoje.
- Būsena laikoma tik atmintyje. Perkrovus puslapį atsakymai dingsta.

## 11. Testavimo scenarijai

Automatinių testų nėra. Rankai: kiekviena kryptis, trūkstami privalomi laukai, sėkmingas POST, 422, 429, `too_fast`, tinklo klaida ir `mailto`. Šioje užduotyje forma nesiųsta ir serveris nekviestas.

## 12. Apribojimai

Serverio kodo, raktų ir žurnalų čia nėra. Jų dokumentacijoje kartoti negalima. Formos pakeitimas turi likti peržiūroje. Gyvo `revision.lt` formos šis modulis nevaldo, kol savininkas atskirai nepatvirtina perkėlimo.
