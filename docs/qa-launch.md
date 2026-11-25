# QA ja launch gate

## QA tõend
Iga test: ID, URL, keskkond, brauser/seade/viewport, versioon või commit, kuupäev, oodatud tulemus, tegelik tulemus, tõend, raskus, vastutaja, paranduse järeltest. „Testimata” ei ole „läbitud”.

## Kohustuslik kontroll
- Kujundus: võrdle kinnitatud Paperi artboard'idega ja kontrolli [PB101 v1.0 CSS-reeglite](pb101-css.md) rakendamist; kontrolli mobiili, tahvlit, desktopi ja vahepealseid laiusi, pika sisu ning 200% zoomiga.
- Ligipääsetavus: klaviatuur, nähtav fookus, skip-link, landmark'id, vormide nimed/vead, kontrast, alt-tekstid, reduced motion. Kombineeri automatiseeritud ja käsitsi kontroll; ära väida sertifitseeritud vastavust üksnes tööriista skoori põhjal.
- Funktsioonid: menüü, lingid, otsing/filter, CMS, 404, vormi serverivead, e-posti päris tarne, vajadusel ostuteekond ja nõusoleku kõik valikud.
- Brauserid: projekti publikule sobiv maatriks, vähemalt üks Chromium ja teine mootor võimaluse korral; puuduv seade või mootor märgi piiranguna.
- Jõudlus: testi esinduslehti kokkulepitud tingimustes. Eelarve ettepanek: LCP ≤2,5 s, INP ≤200 ms, CLS ≤0,1; kinnita projekti sihid ning erista labori- ja päriskasutuse andmeid. Ära esita üht laboriskoori välitulemusena.
- SEO/sisu: metaandmed, canonical, indeksireeglid, sitemap, suunamised, keeleversioonid, kontaktid, õigekiri ja päris pildid.
- Turvalisus: HTTPS, saladuste puudumine, rollid, admini kaitse, sisendi valideerimine, serveripoolsed piirangud, turvalised veateated ja varukoopia taastamine.
- Õigus ja kulud: tegelik andmekaart, nõusolek, omaniku kinnitatud tekstid, litsentsid ja kõigi teenuste kuluotsused. WordPressi puhul kontrolli inventuuri ja kontoõigusi. [v0.4 originaalinventuur](WordPressi-Pro-Pluginate-nimekiri-v0.4.txt).

## Blokeerijad
Ära avalda, kui puudub G1/G2/G3 kinnitus, vajalik litsents, õiguslik tekst, päris vormitarne, turvaline saladuste hoidmine, taastatav varukoopia või tootmisluba. Kriitiline turva-/andmekao-/makseviga ja katki põhiteekond on alati blokeerijad. Madala mõjuga teadaolev viga saab omaniku selgesõnalise aktsepteerimise ja tähtaja.

## Avaldamise sammud
1. Lukusta kinnitatud versioon ning kontrolli muudatuste ulatus ja sihtdomeen.
2. Salvesta failide/andmebaasi/CMS-i varukoopia, DNS-i hetkeseis ja taastamise juhis. Määra vastutaja ja tagasipöördumise käivitaja.
3. Esita kasutajale QA raport, lahtised vead, kuluotsused, avaldamise aeg ja tagasipöördumine. Salvesta konkreetne tootmisluba.
4. Avalda kokkulepitud meetodil; kontrolli DNS, HTTPS, suunamised ja indekseerimine.
5. Testi avalikul saidil väljalogituna peamised lehed, vormi päris tarne, nõusolek ja lubatud maksekatse.
6. Kui põhiteekond ebaõnnestub, peata edasine muutmine ja rakenda kinnitatud tagasipöördumine, säilitades uued andmed.
7. Salvesta avaldamisraport ja anna üle hooldus. Avaldamine on lõpetatud alles järelkontrolli järel.
