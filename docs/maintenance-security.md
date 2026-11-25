# Hooldus, turvakinnitused ja üleandmine

## Õigused ja kinnitused
Määra nimelised vastutajad, vähimad vajalikud rollid ja ligipääsu lõpp. Kasuta MFA-d ja turvalist saladuste hoidlat. Ära avalda võtmeid GitHubis, kliendikoodis, logides ega ekraanipiltidel.

Täpsustatud luba peab kirjeldama sihtkeskkonda, toimingut, andmeid, riski ja taastamist. Seda vajavad muu hulgas tootmismigratsioon, kustutamine, õiguste laiendamine, koodi käivitamise lubamine, turvakaitse vähendamine ja uus tasuline teenus. Tõsisema toimingu puhul järgi ka keskkonna nõutavat kasutaja üleandmist; juhend ei tühista tööriista turvapoliitikat.

## Hoolduse baasplaan — kinnita sagedused
| Sagedus | Tegevus | Tõend |
|---|---|---|
| Pidev / kokkulepitud monitooring | Uptime, sertifikaat, vormi- ja saatmisvead, limiidid | Teavitus vastutajale, mitte avalik andmelogi |
| Iga nädal | WP/pluginad või rakendussõltuvused, turvateated, varukoopia õnnestumine | Muudatuste ja kontrollide kirje |
| Iga kuu | Vormitarne, katkised lingid, CMS, õigused, jõudlus, kulud | Hooldusraport |
| Iga kvartal | Taastamiskatse, andmete säilitamine/kustutamine, ligipääsud, litsentsimahud | Taastamisprotokoll ja audit |
| Enne tähtaega | Domeen, majutus, postkast, sertifikaat ja litsentside uuenemine | Omaniku otsus ning kululuba |

## Uuendamine
Loe versioonimuudatused, varunda, uuenda testkeskkonnas, kontrolli mõjutatud teekonnad ja avalda kokkulepitud hooldusloa ulatuses. Kiire turvauuendus vajab riskihinnangut ja vastutajat; ära lülita automaatselt välja kaitseid, et test roheliseks saada.

## Intsident
Peata kahjulik teekond vähima mõjuga lubatud meetodil, teavita omanikku, säilita tõendid turvaliselt, piira ligipääsu, tuvasta ulatus ja taasta puhas seis. Lekkinud saladuse korral koordineeri tühistamist/vahetust. Andmerikkumise võimalikud teavituskohustused las otsustab vastutaja kohaldatava õiguse põhjal. Ära varja intsidenti ega kustuta tõendeid.

## Üleandmine
Anna omanikule konto- ja teenuste inventuur ilma paroolide avaldamiseta, sisuhalduse juhend, lähtekood/eksport, kinnitatud kujunduse viited, litsentsi- ja kuluregister, varunduse/taastamise juhis, monitooringu kontaktid ja teadaolevad piirangud. Omanik teeb ühe sisumuudatuse ning hooldaja tõendab taastamisvõimet. Eemalda ajutised ligipääsud omaniku kokkuleppel.
