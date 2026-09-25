# Käyttötapaus 2: Nykyasiakkaan lisämyynti (testiajo)

> Osa [B2B-myyntiassistentin](../agenttimaarittely-b2b-myyntiassistentti.md) agenttihaastattelun vaihetta 5 (testiajo). Kohdeasiakas on olemassa oleva synteettinen case **C02 Teräskajo Koneistus Oy** ([C02_teraskajo.md](../../../03_asiakascaset/C02_teraskajo.md)), joka on jo osa harjoitusaineistoa. Ei sisällä oikeaa asiakasdataa.

## Tilanne

Teräskajon toimeksiannosta vastaava asiakkuuskonsultti haluaa arvioida, kannattaako pilotin ("Varaosa valmiina") edetessä tarjota asiakkaalle lisää palvelua, ja millaista.

## Syöte (konsultti antaa käsin, Odoosta ja sisäisestä aineistosta poimittuna)

| Kenttä | Arvo |
|---|---|
| Yritys | Teräskajo Koneistus Oy |
| Käynnissä oleva toimeksianto | Elinkaaripalvelun konsepti, 72 000 €, 3.8.–27.11.2026 |
| Sopimushistoria (Odoo) | Tämä on ensimmäinen toimeksianto asiakkaalta (konsultin muistin mukaan) |
| Tunnettu riski | Palvelulupaus kasvattaa varastopääomaa (ks. [C02_teraskajo.md](../../../03_asiakascaset/C02_teraskajo.md)) |
| Taloustiedot | Ei tiedossa asiakkaan omalta puolelta |
| Käyttötapaus | Nykyasiakkaan lisämyynti |

## Agentin työnkulku (vaiheet 1–5 määrittelyn mukaan)

1. **Vastaanotto:** Koska kyseessä on nykyasiakas, agentti tunnistaa, että sisäistä tietoa on jo saatavilla olemassa olevasta toimeksiannosta ja aiemmasta [Myynti-profiilista](../../Myynti/C02-teraskajo/profiili.md). Agentti käyttää tätä pohjana sen sijaan, että pyytäisi kaiken uudelleen — kysyy vain, mikä on muuttunut edellisen profiloinnin jälkeen.
2. **Yritysprofiili:** Agentti päivittää profiilin lisäämällä uuden tiedon: pilotti on käynnissä, tulokset eivät vielä tiedossa.
3. **Toimialan kehitys:** Agentti käyttää samaa yleistä toimialakatsausta (metalliteollisuus / tarkkuuskoneistus) kuin aiemmassa profiilissa, ei toista tutkimusta turhaan — tämä on havainto pitkäkestoisen muistin tarpeesta (ks. alla).
4. **Tarjonnan soveltuvuus — lisämyynti:** Agentti tunnistaa aiemmin havaitun mahdollisuuden (kapasiteetin ja hinnoittelun mallinnus ennen laajempaa skaalausta, "Liiketoiminta ja strategia" -luokka) ja tarkentaa sitä pilotin tämänhetkisen vaiheen perusteella: koska pilotti on vielä kesken, agentti suosittelee odottamaan pilotin tuloksia ennen laajemman tarjouksen tekemistä, ei tarjoamaan heti.
5. **Kaksi tuotosversiota:**
   - **Sisäinen pitkä versio:** päivitetty profiili + perusteltu suositus ajoituksesta (odota pilotin tuloksia).
   - **Lyhyt asiakasversio:** ei tehdä vielä, koska agentin oma suositus on olla tarjoamatta lisää ennen pilotin tuloksia — agentti perustelee tämän konsultille sen sijaan, että tuottaisi asiakasmateriaalia turhaan.

## Odotettu lopputulos

- Agentti **ei toista** koko profilointia alusta, vaan tunnistaa ja käyttää aiempaa [Myynti-profiilia](../../Myynti/C02-teraskajo/profiili.md) lähtökohtana.
- Agentti tekee perustellun ajoitussuosituksen (odota pilotin tuloksia) sen sijaan, että tuottaisi asiakasversion mekaanisesti joka kerta — tämä osoittaa, että "tuota aina kaksi versiota" -sääntöä (vaihe 4) pitää tarkentaa: lyhyt asiakasversio tehdään vain, jos agentti (tai konsultti) arvioi, että lisämyyntiin on jo aihetta.

## Testiajossa löydetyt havainnot ja aukot

- **Aukko / avoin kysymys:** Pitäisikö agentilla olla pääsy aiempiin Myynti-profiileihin ja projektin muuhun aineistoon (`03_asiakascaset/`, `Claude outputs/Myynti/`) automaattisesti nykyasiakastapauksissa? Tässä testissä se osoittautui hyödylliseksi (vältti toistetun työn), mutta pitää päättää, onko tämä oletusarvoinen toimintatapa vai pitääkö konsultin erikseen viitata aiempaan profiiliin.
- **Aukko:** Määrittelyssä pitää tarkentaa sääntö "tuota aina lyhyt + pitkä versio" — tämä testiajo osoitti, että joskus oikea suositus on olla tekemättä asiakasversiota lainkaan, koska ajoitus ei ole vielä oikea. Ehdotus: lisätään päätössääntöihin (kohta 8), että agentti arvioi ensin, onko lisämyyntiin ajoituksellisesti aihetta, ja tuottaa asiakasversion vasta silloin.
- **Havainto — pitkäkestoinen muisti:** Koska sama toimialakatsaus jouduttiin tekemään uudelleen, agentille kannattaisi harkita samantyyppistä pitkäkestoista muistia kuin [projektisuunnittelijan pilkkomisohje](../../taidot/projektisuunnittelija/pilkkomisohje.md) — esimerkiksi kevyt "toimialakatsausten" muistitiedosto, ettei samaa yleistä toimialatietoa kirjoiteta joka kerta uudelleen tyhjästä. Tämä on ehdotus vaiheeseen 17 (jatkokehitysideat), ei vielä päätetty.
