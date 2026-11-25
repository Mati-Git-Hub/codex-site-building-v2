# Astro + Cloudflare töövoog

Eeltingimus: G0–G3 läbitud. Enne paigaldamist kontrolli Astro ja Cloudflare ametlikust dokumentatsioonist parajasti toetatud versioonid, adapter, runtime ja avaldamisviis. Siin ei fikseerita kontrollimata tänaseid API-sid.

1. Määra staatilised lehed ja serverit vajavad funktsioonid. Valik Pages/Workers ning adapter peab tuginema tegelikule vajadusele ja praegusele toele; ära eelda Node'i võimalusi edge-keskkonnas.
2. Loo uus projektikaust, kinnita õige Git remote, paketihaldur ja lukufail. Salvesta runtime'i versioon ning dokumenteeri projekti install/build/preview kontrollkäsud.
3. Tõsta kinnitatud disainitokenid globaalsesse stiilikihti ja korduvad struktuurid komponentideks. Kasuta sisule semantilist HTML-i. Lisa kliendi JavaScript vaid vajadusel.
4. Vali CMS docs/platform.md järgi. Määra skeemid, mustandid, eelvaade, autoriseerimine, meedia ja varukoopia. Testi toimetaja muudatust avaldamiseni.
5. Rakenda piltide mõõdud, formaadid, laadimine, fontide kasutusõigus ja lokaalne/õiguspärane laadimine. Väldi layout shift'i.
6. Kontaktivorm vajab päris serveripoolset endpoint'i või heakskiidetud teenust. Ära pane SMTP/API saladusi frontend'i keskkonnamuutujasse ega bundle'isse.
7. Loo preview keskkond. Seo test- ja tootmissaladused eraldi, kontrolli build'i logisid ilma andmeid lekkimata, testi endpoint'e avaldatud runtime'is.
8. Sea domeen, HTTPS ja ümbersuunamised kontrollitud plaani järgi. DNS muudatusel salvesta senised kirjed ja tagasipöördumise sammud; ära riku MX, SPF ega DKIM kirjeid.
9. Testi 404, canonical, sitemap, robots, keeleversioonid, vormid ja deploy tagasipööramine. Build'i läbimine ei tõenda teenuste töötamist.
10. Salvesta kulud/limiidid, taastatav build, CMS eksport, Cloudflare seadistuse viited ja hooldaja. Avalda alles G5 loaga.

Ametlikud kontrollpunktid: https://docs.astro.build/ ja https://developers.cloudflare.com/ . Need on tulevase kontrolli lähtekohad, mitte väide, et konkreetne versioon on juba kontrollitud.
