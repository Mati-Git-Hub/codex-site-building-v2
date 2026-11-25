# WordPress + Bricks töövoog

Eeltingimus: G0–G3 läbitud. Lähtu kinnitatud Paperi kujundusest ja [PB101 CSS-täppisjuhendist v1.0](pb101-css.md).

1. Kontrolli test- ja tootmiskeskkonna aadressi, rolli ning töö ulatust. Salvesta WP/Bricks/PHP versioonid, aktiivsed pluginad, teema, olemasolevad klassid/tokenid ja mallide tingimused.
2. Tee failide ja andmebaasi varukoopia. Tõenda taastamist testkeskkonnas. Enne olemasoleva saidi muutmist säilita mõjutatud lehe/malli eksport või revisjon.
3. Vali üks sisumudeli omanik: WP tuumik või põhjendatud ACPT/JetEngine vms. Määra sisutüübid, väljad, taksonoomiad, õigused, URL-id ja ekspordivõimalus. Ära dubleeri samu välju mitmes pluginas.
4. Kaardista kinnitatud tokenid Bricks muutujateks ja korduvad rollid globaalseteks klassideks. Inventuuri järel kasuta olemasolevat nimesüsteemi. Väldi paralleelset Core Frameworki ja käsitsi loodud samatähenduslike tokenite kogumit.
5. Loo päise/jaluse ja sisu mallid ning selged rakendumistingimused. Korduvad plokid tee komponentideks. Kontrolli tegelikke elementide skeeme enne andmete kirjutamist.
6. Seo dünaamiline sisu, päringud, tühjad tulemused ja lehekülgedeks jaotus. Kontrolli ühe ning paljude kirjete, puuduva pildi ja pika pealkirjaga.
7. Lisa ainult põhjendatud pluginad [v0.4 originaalinventuuri](WordPressi-Pro-Pluginate-nimekiri-v0.4.txt) ja kontrollitud kontoõiguste alusel. Vali üks SMTP lahendus ja üks SEO vastutaja. Crocoblock top Lifetime ei tähenda kõigi JetPluginate paigaldamist.
8. Lisa vormid, e-post, õiguslikud lehed, SEO ning vajaduse korral WooCommerce erijuhendite järgi.
9. Loe salvestatud tulemus tagasi ja kontrolli frontend'i väljalogituna. Vaata mallide tingimusi, mobiilmenüüd, päringuid ning genereeritud CSS-i. Taasta või paranda avastatud viga enne järgmisi kirjutusi.
10. Läbi QA ja launch gate. Tootmisse vii ainult kinnitatud ulatus; andmebaasi ülekanne ei tohi kirjutada üle vahepeal lisandunud tellimusi/vormikirjeid.

Custom code puhul eelista väikest versioonihallatud child theme'i või pluginat. Ära muuda WP, Bricks ega väliste pluginate tuumikfaile. Ära lülita koodi käivitamist või turvapiiranguid sisse varjatult. Kontrolli väljundi escape'imist, sisendi valideerimist, õigusi ja noncesid vastavalt kasutuskohale.
