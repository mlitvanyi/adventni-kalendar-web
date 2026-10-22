# Úprava celej landing page (vetva `landing-vizual`)

Poznámka od Michala, 22. 10. 2026. Robí sa oddelene od nových vzhľadov kalendára.

## Čo chceme
- **Globálne štýly a layout:** prejsť celú stránku. Niečo zmazať, upraviť, preusporiadať alebo doplniť, prípadne vizuálne spraviť inak.
- **Logo PragueBest:** doplniť ho na stránku.
- **Preč s „AI slopom“:**
  - Odstrániť hairline/eyebrow titulky, teda `section-label` nad hlavnými nadpismi (napr. „02 - Vzhledy“, „08 - Kontakt“).
  - Hlavný nadpis má sám povedať, čo sekcia robí, a nemá odkazovať na číslo alebo názov sekcie.
- **Hlavička:** hneď musí byť jasné, že ide o kalendár. Namiesto stromčeka dať animovaný kalendár v kóde (pozri `docs/vzhledy/koncepty.md`, moodboard 01).

## Inšpirácia: givingli.com (Michalovi sa veľmi páči)
- **Hero:** veľký centrovaný popis, okolo neho rozhádzané obrázky v rôznej rotácii. U nás to budú screenshoty našich kalendárov, napríklad náhľady z `img/nahledy/` alebo väčšie výrezy scén.
- **Pod textom dve CTA:** jedna na demo ukážku (`#ukazka`), druhá na kontakt alebo ponuku.
- **Sekcie:** striedajú sa text a obrázok, je v nich jednoduchosť a krátke, jasné nadpisy a texty doplnené obrázkami.
- Navrhnúť, čo by sme do takých sekcií dali: vzhľady, ako to funguje, administrácia, výsledky a kontakt. Dnešný obsah zostáva, mení sa forma.

## Dizajn systém PragueBest (z neho vychádzať)
- **Dočasná stránka:** https://praguebest-cz-nklywilr6-praguebests-projects.vercel.app/produkty/weby
- **Lokálne repo:** `C:\_WWW\PRAGUEBEST\website` (Astro, čisté CSS custom properties, bez Tailwindu).
  - Tokeny: `src/styles/tokens/` (primitívy aj sémantické), globálne štýly v `src/styles/global.css`.
  - Popis: `docs/design-system.md`, zoznam toho, čo nerobiť: `docs/dont.md`.
  - Playground tokenov: `npm run dev` → `http://localhost:4321/tokens`.
  - Písmo Satoshi (self-hosted, `public/fonts/satoshi/`), Inter ako záloha.
- Givingli je tomuto dizajn systému veľmi podobné, takže smer sedí.

## Vianočný duch zostáva
- Stránka má aj po úprave pôsobiť vianočne a adventne, nie ako neutrálna produktová stránka.
- Ponechať padajúce prvky na pozadí (dnešný sneh, iskry) a spraviť ich prepracovanejšie. Napríklad viac vrstiev s rôznou rýchlosťou a veľkosťou, jemná paralaxa, aby to bolo bohatšie a krajšie.
- Vianočné akcenty (cezmína, stromček, darčeky, zlaté iskry) zachovať aj v novom layoute v štýle Givingli.
- Rešpektovať `prefers-reduced-motion`.

## Stav: interná verzia 2 (22. 10. 2026)
- **`index-v2.html`** vedľa pôvodného `index.html`, s rovnakým obsahom. Má `noindex`.
- **Interný prepínač** „Původní / Nová“ je vľavo dole na oboch stránkach a zachová kotvu (`#ukazka` ostane `#ukazka`). V kóde je označený ako `INTERNAL` a pred publikáciou sa zmaže: blok `.ver-switch` na konci `<body>` v oboch súboroch.
- **Hero podľa Givingli:**
  - nav s logom PragueBest, sekciami a tlačidlom „Chci kalendář“,
  - obrovský centrovaný nadpis s „Originálně.“ v červenej,
  - podtitul a dve CTA (Prohlédnout vzhledy, Chci kalendář na míru),
  - pod nimi trojica výhod,
  - okolo osem pootočených, jemne sa vznášajúcich náhľadov kalendárov s popiskami (`img/hero/*.webp`, 400×500),
  - zlaté iskry a cezmína.
  - Na mobile sa náhľady zložia do vejára nad nadpisom.
- **Dizajn systém PragueBest:** písmo Satoshi (`fonts/Satoshi-Variable.woff2` + licencia), papierové pozadie `#f2ece0`, atrament `#0a0a0a`, červená `#e30613`, väčšie zaoblenia a tiene z tokenov.
- **Bez popiskov nad nadpismi.** Všetkých 8 `section-label` je preč. Kontakt dostal nadpis „Další krok“ a dve CTA.
- **Striedanie sekcií:** sekcie majú celošírkové pásy (svetlý papier, krém) a záver je tmavý pás s kontaktom.
- **Sneh:** canvas v troch vrstvách (vzdialené drobné, stredné a blízke vločky aj zlaté hviezdičky), biela, zlatá a červená, s jemným kývaním. Pri skrytej záložke sa zastaví, pri `prefers-reduced-motion` je vypnutý.
- **Overené:** desktop 1280 aj mobil 375, bez horizontálneho posunu. Demo kalendára funguje vo všetkých 13 vzhľadoch, konzola je bez chýb.
- **Ďalej:** v stredných sekciách zatiaľ chýbajú obrázky po vzore Givingli (striedanie text/obrázok). Doplniť ich podľa spätnej väzby. Animovaný kalendár v hlavičke zatiaľ nahrádzajú náhľady.

## Čo platí ďalej
- Obsah a význam textov ostávajú. Meníme formu, poradie a vizuál, nie posolstvo.
- Zmeny landing page sa držia oddelene od vzhľadov kalendára, aby bolo vidno, čo sa zmenilo.
