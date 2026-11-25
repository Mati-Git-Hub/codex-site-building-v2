# PB101-põhise CSS-täppisjuhendi kinnitamise värav

**Staatus: BLOKEERITUD kinnitatud PB101 allikateksti ja kasutaja kinnituse puudumise tõttu.**
See dokument on täpne algupärane tehniline ettepanek ja kinnitamise protseduur. Seda ei tohi nimetada PB101 õpetuste kontrollitud kokkuvõtteks. Saidi arendust ei alustata selle ettepaneku alusel enne G2 läbimist.

## Kuidas valmis juhend kinnitada enne arendust
1. Tuvasta kasutaja mõeldud PB101 õpetuste komplekt ja ametlikud allikad. Salvesta iga reegli juurde tunni/jaotise/ajatempli viide ning lühike oma sõnadega põhjendus.
2. Võrdle allikaid alloleva otsustustabeli iga reegliga. Märgi eraldi allikast kontrollitud põhimõte ja projektipõhine otsus. Ära täida allikaviidet oletuse põhjal.
3. Täpsusta kõik allolevad otsused valitud platvormile; valideeri näited ja konfliktid. Koosta eraldi versioonitud kinnitatav dokument.
4. Esita kasutajale terviktekst, näited, erandid ja lahtised kohad. Salvesta selgesõnaline kinnitus koos versiooni/commit'i ja kuupäevaga.
5. Alles siis märgi G2 läbituks. Arendamise ajal rakenda juhendit; ära jäta põhiprintsiipide uurimist ehitamise ajaks.

## Tehniline ettepanek kinnitamiseks
| Vajadus | Lahendus | Piir |
|---|---|---|
| Korduv disainiväärtus | Semantiline CSS-muutuja | Ära loo igale elemendile uut tokenit |
| Korduv visuaalne roll | Globaalne klass | Üks tähendus, mitu kasutuskohta |
| Korduv struktuur ja käitumine | Komponent + klassid | Muutuva sisu jaoks andmeväljad |
| Komponendi sisemine väärtus | Komponendi skoobiga muutuja | Globaalne ainult päris jagatud vajadusel |
| Üksik erand | Dokumenteeritud kohalik reegel | Kordumisel tõsta süsteemi |
| JS-i sihtmärk | data-atribuut | Ära seo käitumist juhusliku stiiliklassiga |
| Unikaalne ankur või seos | ID | Ära kasuta korduvate stiilide aluseks |

### Nimed ja omand
Uues projektis kinnitamiseks: semantilised tokenid `--color-text`, `--color-surface`, `--space-m`, `--content-max`; komponendid `.service-card`, osad `.service-card__title`, variandid `.service-card--featured`. Olemasolevas projektis inventeeri esmalt nimed ja järgi kinnitatud konventsiooni; ära loo paralleelset süsteemi.

Tokeni näidis: `:root { --color-text: #17212b; --space-m: 1rem; }`. Komponendi näidis: `.service-card { color: var(--color-text); padding: var(--space-m); }`. Need väärtused on näited, mitte kinnitatud disainitokenid ega PB101 tsitaadid.

### Paigutus ja tüpograafia
- Määra konteineri max-width ja küljeruum tokenitega. Kasuta sisu jaoks Grid/Flex paigutust; ära joonda tühikute, tühjade elementide või juhuslike margin'itega.
- Määra tüpograafia rollid ja skaala; kasuta rem ühikuid tekstile. Fluid skaala puhul kinnita clamp'i miinimum, eelistatud väärtus ja maksimum ning testi vahepealseid laiusi.
- Määra spacing-skaala, sektsiooni vertikaalruum ja komponentide gap. Ära loo kinnitamata juhuväärtusi iga ploki jaoks.
- Breakpoint'id tulenevad sisu murdumisest; nimeta suund (mobile-first või desktop-first) ja väärtused kinnitatud juhendis. Testi ka breakpoint'ide vahet.
- Kinnita hover, focus-visible, active, disabled, invalid, loading ja success olekud. Värv üksi ei tohi kanda kogu tähendust.

### Kaskaad ja erandid
Määra baastiilide, tokenite, komponentide ja utiliitide laadimisjärjekord. Hoia selektorid lühikesed; ära seo stiili DOM-i juhusliku sügavusega. Väldi ID-selektoreid, inline-kordusi ja !important paranduste kuhjamist. Vajalik erand saab põhjuse, ulatuse ja eemaldamistingimuse.

Bricksis hoia korduvad stiilid globaalsetel klassidel, mitte igal elemendil eraldi. Astro puhul koordineeri lokaalsed stiilid globaalsete tokenitega. Kummalgi rajal kontrolli päris CSS-väljundit ja nimekonflikte.

## G2 kontrollnimekiri
- [ ] Iga normatiivne PB101 väide seostatud kontrollitud allikaga.
- [ ] Projektipõhised valikud eristatud allikapõhimõtetest.
- [ ] Tokeni, klassi, komponendi ja erandi otsustusreeglid ühesed.
- [ ] Nimed, skaala, paigutus, breakpoint'id, olekud ja kaskaad määratud.
- [ ] Näited ja vastunäited kontrollitud valitud platvormis.
- [ ] Kasutaja kinnitanud konkreetse tervikversiooni.
