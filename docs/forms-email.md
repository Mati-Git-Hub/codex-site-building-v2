# Kontaktivormid ja e-post

## Planeerimine ja andmed
Määra vormi eesmärk, minimaalsed väljad, kohustuslikkus, saaja, vastutaja, õiguslik alus, säilitusaeg ja kustutamine. Eralda päringule vastamine turundusnõusolekust; turunduse valikut ei märgita ette. Väldi tundlike andmete ja manuste kogumist ilma vajaduseta.

WordPressis vali Bricks vorm või põhjendatud Bit Form / JetFormBuilder kontrollitud litsentsi järgi. Astrol vali serveripoolne endpoint või eelnevalt kinnitatud tasuta teenus. Lisa päris label'id, autocomplete sobivusel, veateated, klaviatuurifookus, topeltsaatmise vältimine ja arusaadav eduolek.

## Serveripoolne kaitse
Valideeri väljad ja piirangud serveris, kodeeri väljund, piira päringute sagedust, kasuta sobivat robotikaitset ning päritolu/CSRF kaitset vastavalt teostusele. Manustel kontrolli tüüpi, suurust ja ligipääsu. Päisesse ei tohi pääseda kasutaja sisestatud reavahetused. Edu vastus peab tähendama tegelikult aktsepteeritud saatmist või järjekorda lisamist, mitte lihtsalt nupu vajutamist.

## E-posti tarne
- Määra domeeni kontrollitud saatja; kasutaja e-post läheb Reply-To väljale, mitte suvaliseks From aadressiks.
- WP puhul kasuta ühte FluentSMTP või Bit SMTP lahendust. SMTP teenus, postkast ja plugin on eri kuludega kihid.
- Salvesta teenuse võtmed turvaliselt. Kontrolli SPF, DKIM ja DMARC seadistust teenuse dokumentatsiooni ning domeeni tegelike DNS kirjete järgi; ära lisa konkureerivaid SPF kirjeid.
- Sea bounce'ide, vigade ja limiidi täitumise vastutaja ning vajadusel turvaline kordussaatmine. Logides hoia minimaalseid andmeid ja piiratud säilitusaega.

## Vastuvõtutest
- [ ] Õige sisend jõuab kokkulepitud päris postkasti; kontrollitud From, Reply-To ja vastamise teekond.
- [ ] Vähemalt kahe erineva postkasti tarne ja rämpspostikaust vaadatud.
- [ ] Puuduvad/valed väljad, serveri viga, teenuse katkestus ja kordusklõps testitud.
- [ ] Rämpsposti piirang ja ligipääsetavad veateated toimivad.
- [ ] Turundusnõusolek ei ole päringu saatmise eeltingimus, kui see pole vajalik.
- [ ] Testandmed eemaldatud kooskõlas säilitusplaaniga.

Tõendisse kirjuta aeg, keskkond, anonüümne test-ID, oodatud/täheldatud tulemus ja kontrollija. Ära avalda päris sõnumeid, aadresse ega e-posti päiseid GitHubis.
