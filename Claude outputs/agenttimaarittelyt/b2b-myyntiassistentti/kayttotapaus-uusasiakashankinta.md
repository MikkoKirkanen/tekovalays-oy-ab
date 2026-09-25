# Käyttötapaus 1: Uusasiakashankinta (testiajo)

> Osa [B2B-myyntiassistentin](../agenttimaarittely-b2b-myyntiassistentti.md) agenttihaastattelun vaihetta 5 (testiajo). Kohdeyritys **Louhikaari Kaivospalvelut Oy** on tätä testiä varten keksitty synteettinen esimerkki — se ei ole osa [03_asiakascaset](../../../03_asiakascaset/asiakassalkku.md)-aineistoa eikä oikea yritys. Ei sisällä oikeaa asiakas- tai kohdeyritysdataa: tämä harjoitusympäristö ei salli sellaisen syöttämistä.

## Tilanne

Asiakkuudesta vastaava konsultti on saanut ensikontaktin messuilta kaivosalan laitehuoltoyritykseen ja haluaa arvioida nopeasti, kannattaako kohdetta lähestyä tarjouksella ja millä palvelulla.

## Syöte (konsultti antaa käsin, Odoosta ja muistista poimittuna)

| Kenttä | Arvo |
|---|---|
| Yritys | Louhikaari Kaivospalvelut Oy (synteettinen) |
| Toimiala | Kaivosteollisuuden laitehuolto |
| Henkilöstö | n. 70 (konsultin arvio, ei varmistettu) |
| Kontaktin alkuperä | Messutapaaminen 9/2026, ei vielä tarjousta |
| Yhteyshenkilö | Tuotantojohtaja (nimi ja sähköposti eivät tiedossa vielä) |
| Tunnettu tarve | Huoltosopimusten hajanaisuus, samankaltainen tilanne kuin C01 Kaarisillalla |
| Taloustiedot | Ei tiedossa |
| Käyttötapaus | Uusasiakashankinta |

## Agentin työnkulku (vaiheet 1–5 määrittelyn mukaan)

1. **Vastaanotto:** Agentti pyytää konsultilta puuttuvat välttämättömät tiedot ennen aloitusta: tarkempi henkilöstömäärä tai sen puuttuessa merkintä oletukseksi, käyttötapaus (uusi vs. nykyasiakas) ja se, onko taloustietoa saatavilla. Koska taloustietoa ei ole, agentti **ei hae sitä verkosta** (kielletty tässä versiossa) vaan merkitsee sen avoimeksi kohdaksi.
2. **Yritysprofiili:** Agentti kokoaa annetuista tiedoista lyhyen profiilin: toimiala, koko, lähtötilanne, kontaktin vaihe.
3. **Toimialan kehitys:** Agentti tuottaa yleisen, ei-yrityskohtaisen kehitysarvion toimialalle (kaivosteollisuuden laitehuolto: kunnossapidon ennakoivuus, palveluliiketoimintaan siirtyminen, sääntely ja turvallisuusvaatimukset) samaan tapaan kuin [Myynti-profiileissa](../../Myynti/README.md) tehtiin, merkiten sen yleiseksi markkinakontekstiksi.
4. **Tarjonnan soveltuvuus:** Agentti vertaa tunnettua tarvetta (hajanaiset huoltosopimukset) [palvelut_ja_ansainta.md](../../../01_yritys/palvelut_ja_ansainta.md)-luokitukseen ja tunnistaa lähimmäksi vastaavaksi luokaksi "Asiakas- ja toimintaymmärrys" tai "Palvelumuotoilu ja konseptointi" — huomauttaen, että C01 Kaarisillan tapaus on samankaltainen ja voisi toimia myyntikeskustelun vertailukohtana (ei kopioitavana pohjana).
5. **Kaksi tuotosversiota:**
   - **Sisäinen pitkä versio:** täysi profiili avoimine kohtineen (puuttuva henkilöstöluku, puuttuva taloustieto, puuttuva yhteyshenkilön nimi).
   - **Lyhyt asiakasversio:** 3–5 lauseen tiivistelmä, joka sopisi ensikontaktin jälkeiseen sähköpostiin — **ilman** avoimia sisäisiä huomioita ja ilman keksittyjä lukuja.

## Odotettu lopputulos

- Sisäinen versio nimeää selvästi kolme puutetta: henkilöstömäärä (arvio, ei varmistettu), taloustiedot (puuttuu kokonaan), yhteyshenkilön tiedot (puuttuu).
- Agentti **ei** arvaa tai keksi näitä, vaan listaa ne kohtaan "Puuttuvat tiedot" ja ehdottaa, mitä konsultin kannattaisi selvittää seuraavaksi (esim. yhteyshenkilön nimi ennen tarjouskeskustelua).
- Lyhyt asiakasversio ei sisällä mitään, mitä konsultti ei ole antanut tai mitä ei ole yleistä toimialatietoa.

## Testiajossa löydetyt havainnot ja aukot

- **Aukko:** Määrittelyssä ei ole vielä sovittu, pyytääkö agentti puuttuvat tiedot kaikki kerralla vai yksi kerrallaan. Suositus: yksi looginen kokonaisuus kerrallaan, samaan tapaan kuin muissakin tämän projektin taidoissa (ks. esim. [fasilitoija](../../taidot/fasilitoija.md) -taidon ristiriitojen selvittämisen menettely).
- **Aukko:** Ei ole määritelty, mitä agentti tekee, jos konsultti ei osaa sanoa henkilöstömäärää edes arviona — pitäisikö agentti silloin kieltäytyä profiilin teosta vai jatkaa merkittävällä oletuksella?
- **Havainto:** C01 Kaarisillan käyttö vertailukohtana toimi hyvin, koska aineisto on jo tuttua — tämä puoltaa sitä, että agentti saisi käyttää `03_asiakascaset`-aineistoa ja aiempia Myynti-profiileja referenssinä myös uusasiakastapauksissa, kunhan ei esitä niitä kohdeyrityksen omina tietoina.
