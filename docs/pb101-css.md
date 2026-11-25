# PB101 CSS-klasside ja muutujate täppisjuhend v1.0

**Staatus:** kasutaja kinnitatud sõnadega „Kinnitan PB101 juhendi v1.0.”  
**Kasutusala:** Codexi veebiarenduse juhend. Kehtib Bricksis ja Astros.

## 1. PB101-st kontrollitud põhimõtted

| Õppetund | Mida see juhendis toetab |
|---|---|
| Varasema kursuse L07 | Hoia korduv disainiväärtus CSS-muutujas. Sama väärtust kasutavad stiilireeglid saavad viidata ühele definitsioonile. [L07 – CSS Variables & DRY Development Principles](https://www.youtube.com/watch?v=pqguxVBa18o&t=612s) |
| Varasema kursuse L08 | Kasuta üldiste vaikestiilide jaoks elementide stiile ning valikuliselt rakenduvate stiilide jaoks klasse. Õppetund käsitleb BEM-i ja utiliitklasse ning selgitab, miks elemendi ID järgi stiilimine on enamasti ebasoovitav. [L08 – DRY Development With Classes & Global Styling](https://www.youtube.com/watch?v=TMDwPYnJC0g) |
| Geary täiendav BEM-õpetus | Nimeta korduv plokk, selle osad ja variandid eraldi. Autor näitab ploki struktuuri, klasside lisamist ja variandi loomist. [BEM 101 – struktuur 23:34](https://geary.co/youtube-videos/bem-101-how-to-make-web-design-organized-scalable/) |
| Era 4, sissejuhatus | Määra esmalt struktuur ja HTML-i tähendus. Seejärel vali selektorid ning korralda stiilid nimetatud ja omavahel seotud väärtustena. [PB101 Era 4](https://geary.co/pb101/) |
| Era 4, S3:11 ja S3:17 | Tee fookus nähtavaks. Rühmitatud selektorite puhul arvesta, et `:is()` ja `:where()` käituvad spetsiifilisuse mõttes erinevalt. [S3:11 – Focus](https://geary.co/youtube-videos/pb101-era-4-s311-focus-focus-visible-focus-within/), [S3:17 – Is ja Where](https://geary.co/youtube-videos/pb101-era-4-s317-grouping-selectors-with-is-and-where/) |

Allpool toodud nimed, kaskaadi järjestus ja platvormipõhised valikud on **Codexi juhendi kinnitatud rakendusreeglid**. PB101 Era 4 kasutab näidetes Automatic.css-i. Siinse juhendi rakendamiseks piisab tavalisest CSS-ist ja valitud platvormi võimalustest. [PB101 Era 4 – kursuse KKK](https://geary.co/pb101/)

L07 ja L08 puhul kontrolliti autori avalikke õppetundide kirjeldusi ja saadaolevaid peatükiviiteid. Täielikud transkriptsioonid polnud kättesaadavad.

## 2. Otsusta, kuhu stiil kuulub

| Vajadus | Kasuta | Näide |
|---|---|---|
| Jagatud väärtus, mis peaks muutuma ühes kohas | CSS-muutuja ehk token | `--color-surface`, `--space-m` |
| Vaikestiil kogu saidi HTML-elemendile | Madala spetsiifilisusega elementide stiil | Pealkirjade baastüpograafia, linkide vaikestiil |
| Nimetatav visuaalne roll, mida rakendatakse valikuliselt | Korduskasutatav klass | `.button`, `.service-card` |
| Komponendi kindel osa | BEM-elemendiklass | `.service-card__title` |
| Sama komponendi valitav kujundusvariant | Baasklass koos modifikaatoriga | `class="service-card service-card--featured"` |
| Üks üldotstarbeline võte, mida vajavad eri tüüpi elemendid | Väike utiliitklass | `.u-text-center` |
| Korduv HTML-struktuur või käitumine koos muutuva sisuga | Platvormi komponent | Bricks Component või `ServiceCard.astro` |
| Üks piiratud erand | Kohalik reegel lähima omaniku juures | Ühe malli eripaigutus koos põhjendusega |

**Otsustusreegel.** Kui kaks omadust juhtuvad täna olema sama väärtusega, tee neist ühine token ainult siis, kui need peaksid ka edaspidi koos muutuma. Kui mitmel kaardil kordub sama HTML, tee komponent. Kui eri elementidel kordub üksnes sama välimus, piisab klassist. Kui erineb ainult üks väärtus, kaalu enne uue stiilireegli lisamist komponendi kohalikku muutujat.

## 3. Muutujad ja nimed

1. **Üks definitsioon iga jagatud väärtuse kohta.** Seo kinnitatud Paperi disainisüsteemi rollid CSS-nimedega. Kirjuta tokeni registrisse nimi, väärtus, roll, lubatud kasutuskoht ja definitsiooni asukoht. Kasuta kujunduses jagatud väärtust kujul `var(--nimi)`.
2. **Anna jagatud tokenile rolli kirjeldav nimi.** Kasuta näiteks `--color-text`, `--color-surface`, `--color-accent`, `--space-m`, `--font-size-body` ja `--content-max`. Kui mitu rolli lähtuvad samast paletivärvist, võivad nad viidata ühisele alusväärtusele. Eri rollid saavad seega vajadusel eraldi muutuda.
3. **Hoia komponendi kohalikud muutujad komponendi juurel.** Näiteks `--service-card-bg` kuulub `.service-card` juurde. Määra vaikimisi väärtus igal komponendi eksemplaril juurreegliga, et ümbritseva kaardi variant ei kanduks pesastatud kaardile.
4. **Jäta tehnilised konstandid kohale.** `0`, `100%` või paigutuseks vajalik ühekordne mõõt ei vaja automaatselt tokenit. Kohustuslikul tokenil paranda katkine viide selle definitsioonis. `var(--nimi, var(--vaikimisi))` sobib siis, kui muutuja on teadlikult valikuline.
5. **Kasuta üht nimekonventsiooni.** Uue projekti vaikimisi vorm on `.plokk`, `.plokk__osa`, `.plokk--variant` ja `.u-tegevus`. Olemasoleval saidil järgi kasutusel olevat ühtset konventsiooni ja kaardista olemasolevad klassid enne uute loomist. Nimi kirjeldab ülesannet või rolli, näiteks `.service-card__title`.

## 4. Kaskaad, olekud ja responsiivsus

- Määra üldised vaikestiilid keskelt. Hoia komponendi selektor tavaliselt ühe klassi pikkune. Kasuta `:where()` seal, kus üldine vaikereegel peab jääma kergesti ülekirjutatavaks. Kontrolli vastuolu korral brauseris võitvat deklaratsiooni, selle päritolu ja spetsiifilisust. Elemendi ID sobib ankruks või HTML-i seoseks. Tavaline kujundus kuulub klassile. [PB101 L08](https://www.youtube.com/watch?v=TMDwPYnJC0g), [PB101 Era 4 S3:17](https://geary.co/youtube-videos/pb101-era-4-s317-grouping-selectors-with-is-and-where/)
- Projekti enda CSS-i järjestus on **tokenid → baasstiilid → paigutus → komponendid → utiliidid**. Variandi puhul käsitle baasklassi ja modifikaatorit ühe komponendi osana. Kui platvormi või kolmanda osapoole CSS muutub, kontrolli tegelikku väljundit. HTML-i `class` atribuudi nimede järjekord ei otsusta, kumb CSS-reegel võidab.
- Kasuta kasutajaliidese olekuks sobivat selektorit, näiteks `:focus-visible` või `:disabled`. Säilita nähtav fookus. Püsiv kujundusvariant saab modifikaatori. Dünaamilist olekut võib väljendada tegeliku olekuga seotud atribuudiga, näiteks `[aria-expanded="true"]`. [PB101 Era 4 S3:11](https://geary.co/youtube-videos/pb101-era-4-s311-focus-focus-visible-focus-within/), [PB101 Era 4 S3:05](https://geary.co/youtube-videos/pb101-era-4-s305-attribute-selectors/)
- Paiguta ühine lehelaius, küljeruum ja vahed süsteemi tokenitesse. Kasuta paigutuses Grid’i või Flexboxi. Lisa meediapäring, kui lehe paigutus vajab muudatust vaateakna laiuse järgi. Kasuta konteineripäringut, kui sama komponent peab kohanema talle eri paigutustes antud ruumiga. Määra piirid sisu põhjal. Fluidse skaala puhul kirjuta üles `clamp()`-i miinimum, kasvav osa ja maksimum ning kontrolli neid nii äärmistes kui ka vahepealsetes laiustes. [PB101 Era 4 S4:07 – Container Queries](https://geary.co/video-topic/page-building-101-era-4-new/)

## 5. Rakendus Bricksis ja Astros

**Bricks.** Kasuta Bricksis hallatavate saidiüleste tokenite jaoks Style Manageri Variables-vaadet, üldiste stiilide jaoks Theme Styles’i ja korduvate klasside jaoks Classes-vaadet. Klassi stiili muutes kontrolli, et aktiivne selektor on klass. Elemendi ID valimine rakendab seadistuse konkreetsele elemendile. Korduva struktuuri puhul kasuta Bricks Componenti. Kui sait juba laadib vajaliku tokeni või utiliidi oma raamistikust, kasuta olemasolevat definitsiooni. Kontrolli klassi muutust nii ehitaja eelvaates kui ka vähemalt kahel seda kasutaval renderdatud lehel või mallil. [Bricks Style Manager](https://academy.bricksbuilder.io/builder/features/style-manager/), [Bricks Global CSS Classes](https://academy.bricksbuilder.io/builder/styling/global-css-classes/), [Bricks Components](https://academy.bricksbuilder.io/builder/features/components/)

**Astro.** Impordi tokenite ja baasstiilide ühine stiilileht loogilisest juurpaigutusest. Hoia komponendi sees kasutatavad BEM-reeglid `.astro` faili `<style>` plokis, mille Astro vaikimisi komponendi ulatusega seob. Saidiülesed utiliidid jäävad globaalsesse stiililehte. Edasta komponendile variant omadusena ja lisa modifikaator komponendi juurelemendile, näiteks `class:list` abil. Kontrolli ehitatud väljundis, et kõiki kasutatud paigutusi katab ühine stiilileht ning komponent pärib õiged tokenid. [Astro Styles and CSS](https://docs.astro.build/en/guides/styling/)

## 6. Näide

Originaalnäide. Väärtused on näitlikud. Päris saidi väärtused tulevad kinnitatud Paperi disainist.

```html
<article class="service-card service-card--featured">
  <h2 class="service-card__title">Veebilehe hooldus</h2>
  <p>Uuendused, varukoopiad ja taastamiskontroll.</p>
</article>
```

```css
:root {
  --color-surface: #fff;
  --color-surface-accent: #e7f2ef;
  --color-text: #17212b;
  --space-s: 0.75rem;
  --space-m: 1.25rem;
}

.service-card {
  --service-card-bg: var(--color-surface);
  display: grid;
  gap: var(--space-s);
  padding: var(--space-m);
  color: var(--color-text);
  background-color: var(--service-card-bg);
}

.service-card--featured {
  --service-card-bg: var(--color-surface-accent);
}

.service-card__title {
  margin-block: 0;
}
```

Tavakaart saab ainult klassi `service-card`. Esiletõstetud kaart saab lisaks variandi. Mõlemad kasutavad sama paigutust ning taustavärvi määrab üks kohalik muutuja. Kui kaardi struktuur kordub, vii näite HTML platvormi komponenti ja anna pealkiri, kirjeldus ning variant sisendina.

## 7. Kontroll enne arendust ja teostuse vastuvõtul

- [ ] Enne arendust on kinnitatud Paperi rollide ja CSS-tokenite vastavus, nimekonventsioon ning tokenite ja klasside halduskoht.
- [ ] Tavavariant, erivariant ja pesastatud komponent saavad õige arvutatud stiili. Ühe jagatud tokeni muutmine jõuab kõigi ette nähtud kasutuskohtadeni.
- [ ] Pealkirjad, vormiväljad ja muud baaselemendid säilitavad vaikestiilid ka väljaspool komponenti. Klaviatuurifookus on nähtav.
- [ ] Kontrollitud on kitsas ja lai paigutus, vahepealsed laiused ning pikk eestikeelne sisu.
- [ ] Brauseris on kontrollitud tokenite väärtused ja võitvad deklaratsioonid. Puuduvad tahtmatud ID-põhised ülekirjutused, duplikaadid ja lahendamata kohustuslikud tokenid.
- [ ] Eranditel on teada põhjus ja ulatus. Juhendi kinnitatud versioon on projekti otsusteregistris.
