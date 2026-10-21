# Adventní kalendář na míru - prezentační web

Stránka pro klienty PragueBest: proč a jak si nechat postavit adventní (nebo jiný) kalendář dárků na míru. Živě na https://adventni-kalendar.pbst.app.

## Co je v repu

* `index.html` - stránka (7 vzhledů kalendáře, administrace, technologické okénko, nabídka vývoje a auditu, kontakt)
* `email/index.html` - online verze e‑mailu klientům (stejný obsah zkráceně, 4 náhledy, tlačítko na stránku)
* `fonts/` - self‑hosted Inter a JetBrains Mono (woff2, latin + latin‑ext)
* `img/` - ilustrace vzhledů; `img/mail/` - obrázky pro e‑mail (absolutní odkazy na živou adresu)
* `vercel.json` - statické nasazení bez buildu

Stránka je čisté HTML/CSS/JS, bez buildu a bez závislostí. Otevře se dvojklikem na `index.html`.

## Nasazení

Vercel projekt `adventni-kalendar-na-miru` (tým PragueBest) je napojený na toto repo. Push do `main` = nasazení na produkci.

## Související

* Samotná aplikace kalendáře (Next.js, databáze, recept): repo `praguebestcz/calendars`
* Text e‑mailu k vložení do pošty: `spec-workspace` → `projects/mastershop/outputs/ai-first-aplikace/email-klientum.md`
