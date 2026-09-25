# Agenttimäärittely: B2B-myyntiassistentti

> Syntyi agenttihaastattelussa 2026-09-25 ([AI haastattelee agentin luomisesta](../taidot/ai-haastattelee-agentin-luomisen.md)). Käyttäjä nimesi agentin ("B2B-myyntiassistentti") itse ennen haastattelua, joten vaihe 3 oli valinnan validointi, ei vaihtoehtojen vertailu.
>
> Merkinnät: **[Vastaus]** perustuu haastateltavan vastauksiin. **[Oletus]** on haastattelijan ehdotus tai päätelmä, jota ei ole erikseen vahvistettu.
>
> **Tila:** versio 1.0, luonnos. Testiajo (vaihe 5) on tehty kahdella synteettisellä esimerkillä: [uusasiakashankinta](b2b-myyntiassistentti/kayttotapaus-uusasiakashankinta.md) ja [nykyasiakkaan lisämyynti](b2b-myyntiassistentti/kayttotapaus-lisamyynti.md). Kolme testiajossa löydettyä avointa kysymystä on ratkaistu tähän versioon.
>
> **Toteutus:** taito [B2B-myyntiassistentti](../taidot/b2b-myyntiassistentti.md), rekisteröity [CLAUDE.md](../../CLAUDE.md):n taitoluetteloon. Koska agentin pitää keskustella käyttäjän kanssa (kysyä puuttuvat tiedot, näyttää luonnos, pyytää hyväksyntä), se toteutettiin "taitona" kansiossa `Claude outputs/taidot/` — samaan tapaan kuin [projektisuunnittelija](../taidot/projektisuunnittelija.md) — ei Claude Code -subagenttina, koska subagentit eivät voi keskustella käyttäjän kanssa. Ei vielä testattu oikeassa myyntitilanteessa.

---

## 1. Nimi ja kuvaus

**B2B-myyntiassistentti:** profiloi kohdeyrityksen tai nykyasiakkaan ja arvioi Tekoväläyksen palvelutarjonnan soveltuvuuden sille, sekä uusasiakashankinnassa että nykyasiakkaiden lisämyynnissä. **[Vastaus]**

## 2. Tavoite ja ratkaistava ongelma

**Nykytila [Vastaus]:**

- Asiakkuudesta vastaava konsultti tekee kohdeyrityksen tai nykyasiakkaan profiloinnin ja tarjonnan soveltuvuusarvion käsin, viikoittain, 1–3 tuntia kerrallaan.
- Tiedot kootaan Odoosta ja konsultin omasta muistista. Tulos päätyy suoraan tarjoukseen tai myyntiesitykseen.
- Taustalla on johdon tavoite yhtenäistää B2B-myynnin arviointitapa koko organisaatiossa.

**Tavoitetila [Vastaus]:** Sama profilointi ja soveltuvuusarvio syntyvät nopeammin ja yhtenäisemmässä muodossa, konsultin keskittyessä tarkistukseen ja viimeistelyyn arvaamisen ja kokoamisen sijaan.

**Tavoitteen saavuttamisen tunnusmerkit:**

1. **Ensisijainen mittari — ajansäästö [Vastaus]:** profilointiin käytetty aika lyhenee nykyisestä 1–3 tunnista 30–60 minuuttiin.
2. **Toissijainen hyöty — laadun yhtenäisyys [Oletus, sivuhuomio haastattelussa]:** profiilit noudattavat samaa rakennetta tekijästä riippumatta, mutta tätä ei mitata erikseen versiossa 1.

## 3. Käyttäjät ja sidosryhmät

| Rooli | Tehtävä suhteessa agenttiin |
|---|---|
| **Asiakkuudesta vastaava konsultti** | Käynnistää agentin, antaa Odoo-tiedot käsin, tarkistaa ja hyväksyy tuotoksen ennen käyttöä. **[Vastaus]** |
| **Myyntitiimi (uusasiakashankinta)** ja **asiakkuuksista vastaavat (lisämyynti)** | Sama käyttäjäryhmä, sama työkalu — molemmat käyttötapaukset samassa agentissa. **[Vastaus]** |
| **Johto** | Sidosryhmä, joka on pyytänyt systemaattisempaa myyntiprosessia; ei käytä agenttia itse operatiivisesti. **[Vastaus]** |
| **Kohdeyritys / asiakas** | Ei käytä agenttia. Näkee vain lopputuloksen (tarjous/esitys), jos konsultti päättää käyttää sitä. **[Oletus]** |

## 4. Käynnistys

- **Laukaisin:** konsultti käynnistää agentin itse manuaalisesti, kun uusi kohdeyritys tunnistetaan tai nykyasiakkaalle harkitaan lisämyyntiä. Ei ajastusta eikä automaattista käynnistystä. **[Vastaus]**
- **Tiheys:** viikoittain organisaatiotasolla. **[Vastaus]**
- **Syötteet käynnistyksessä:** käyttötapaus (uusi kohde vai nykyasiakas), Odoosta ja muistista käsin poimitut tiedot kohteesta. **[Vastaus]**

## 5. Tarvittava tieto

| Tiedon laji | Sisältö |
|---|---|
| **Aineistot** | [Tekoväläyksen palveluluokitus](../../01_yritys/palvelut_ja_ansainta.md) tarjonnan soveltuvuuden arviointiin. Nykyasiakkaille myös [03_asiakascaset](../../03_asiakascaset/asiakassalkku.md) ja aiemmat [Claude outputs/Myynti](../Myynti/README.md) -profiilit pohjatietona — **agentti saa käyttää näitä automaattisesti** ilman erillistä pyyntöä. **[Vastaus]** |
| **Keskustelu** | Käyttäjä antaa Odoo-tiedot käsin (ei API-yhteyttä tässä versiossa) ja kertoo käyttötapauksen. Agentti kysyy **kaikki puuttuvat välttämättömät tiedot yhtenä kokonaisuutena kerralla**, ei yksitellen. Agentti **ei hae tietoa verkosta** — käytetään vain käyttäjän antamaa tietoa. **[Vastaus]** |
| **Välitulokset** | Pitkä sisäinen versio (profiili, saatavilla oleva talous ja sen puutteet, toimialan yleinen kehitys, tarjonnan soveltuvuus) ja harkinnanvarainen lyhyt asiakasversio. **[Vastaus]** |
| **Pitkäkestoinen muisti** | Ei vielä versiossa 1. Testiajo nosti esiin tarpeen toimialakatsausten muistille (vrt. [pilkkomisohje](../taidot/projektisuunnittelija/pilkkomisohje.md)), jotta samaa yleistä toimialatietoa ei kirjoiteta toistuvasti uudelleen — ks. kohta 17. **[Oletus, ei vahvistettu]** |

## 6. Työnkulku vaiheittain

1. **Vastaanotto:** konsultti kertoo käyttötapauksen (uusi kohde / nykyasiakas) ja antaa Odoo-tiedot ja muun tiedon käsin. **[Vastaus]**
2. **Pohjatiedon tarkistus (vain nykyasiakas):** agentti tarkistaa, onko kohteesta aiempi profiili `03_asiakascaset`- tai `Claude outputs/Myynti`-aineistossa, ja käyttää sitä pohjana. Kysyy vain, mikä on muuttunut edellisestä. **[Vastaus, testiajon perusteella]**
3. **Puuttuvat tiedot:** agentti kokoaa kaikki puuttuvat välttämättömät tiedot yhteen kysymyskokonaisuuteen kerralla — ei kysy yksi kerrallaan. Jos tietoa (esim. taloustietoa) ei saada, se merkitään avoimeksi kohdaksi, ei arvata. **[Vastaus]**
4. **Sisäinen profiili:** agentti kirjoittaa pitkän version: yritysprofiili, saatavilla oleva talous ja sen puutteet, toimialan yleinen kehitys (ei-yrityskohtainen), Tekoväläyksen tarjonnan soveltuvuus ja mahdolliset jatkomyyntikohteet. **[Vastaus]**
5. **Ajoituksen arviointi:** agentti arvioi, onko lisämyyntiin tai tarjoukseen jo asiallisesti aihetta (esim. ei tarjota lisää kesken olevan pilotin aikana). Jos ei ole, se perustelee konsultille, miksi asiakasversiota ei kannata vielä tehdä. **[Vastaus, testiajon perusteella]**
6. **Asiakasversio (harkinnanvarainen):** jos ajoitus on agentin arvion mukaan oikea — tai konsultti pyytää sitä silti — agentti tiivistää lyhyen, asiakkaalle sopivan version ilman sisäisiä huomioita tai keksittyjä lukuja. **[Vastaus]**
7. **Hyväksyntä:** konsultti tarkistaa ja hyväksyy tuotoksen ennen kuin sitä käytetään kohdeyritystä tai asiakasta kohtaan. **[Vastaus]**

## 7. Työkalutoiminnot, työkalut ja käyttöoikeudet

| Toiminto | Työkalu tai integraatio | Käyttöoikeus |
|---|---|---|
| Lue käyttäjän antama Odoo-data | Tekstinä keskustelussa, ei API-yhteyttä | – |
| Lue palveluluokitus, asiakascaset, aiemmat Myynti-profiilit | Tiedoston luku | Luku |
| Kirjoita profiilit ja tiivistelmät | Markdown-tiedostot | Kirjoitus työkansioon |

Ei verkkohakua, ei Odoo-integraatiota, ei Jira-integraatiota versiossa 1. **[Vastaus]**

## 8. Päätössäännöt: mitä agentti päättää itse

- Profiilin rakenne ja sisältö. **[Oletus]**
- Toimialakatsauksen sisältö (yleistä markkinatietoa, ei yrityskohtaista). **[Oletus]**
- Käyttääkö se automaattisesti aiempaa asiakasprofiilia pohjana nykyasiakastapauksissa. **[Vastaus]**
- **Arvioi itse, onko lisämyyntiin/tarjoukseen ajoituksellisesti jo aihetta**, ja päättää sen perusteella, tuottaako se asiakasversion nyt vai perusteleeko se odottamista. **[Vastaus]**

## 9. Kohdat, joissa ihmisen pitää hyväksyä

1. **Ennen asiakaskäyttöä:** konsultti tarkistaa ja hyväksyy sekä sisäisen että mahdollisen asiakasversion ennen kuin materiaalia käytetään kohdeyritystä tai asiakasta kohtaan. **[Vastaus]**
2. **Agentin ajoitussuosituksen ohittaminen:** jos agentti suosittelee odottamaan, konsultti voi silti pyytää asiakasversion heti — ihmisen päätösvalta säilyy agentin suosituksen yli. **[Vastaus, testiajon perusteella]**

## 10. Rajaukset: mitä agentti ei tee

- Ei hae tietoa verkosta kohdeyrityksistä. **[Vastaus]**
- Ei kirjaudu Odooon tai muihin järjestelmiin itse; tiedot annetaan sille käsin. **[Vastaus]**
- Ei lähetä mitään suoraan asiakkaalle tai kolmansille osapuolille. **[Oletus]**
- Ei keksi puuttuvia tietoja, esimerkiksi talouslukuja — merkitsee ne avoimeksi. **[Vastaus]**
- Ei kirjaa tuotoksia automaattisesti Jiraan tai Odooon versiossa 1; tiedosto riittää. **[Vastaus]**

## 11. Poikkeus- ja virhetilanteet

| Tilanne | Käsittely |
|---|---|
| Odoo-tiedoissa puutteita tai ristiriitoja | Agentti kokoaa kaikki puuttuvat tiedot yhteen kysymykseen kerralla, ei arvaa. **[Vastaus]** |
| Taloustietoa ei ole saatavilla | Merkitään avoimeksi kohdaksi, ei fabrikoida lukuja. **[Vastaus]** |
| Nykyasiakkaan aiempi profiili puuttuu tai on vanhentunut | Agentti kertoo tämän ja tekee pohjatyön alusta. **[Oletus]** |
| Ajoitus ei ole vielä oikea lisämyynnille | Agentti perustelee, miksi asiakasversiota ei vielä tehdä; konsultti voi silti pyytää sen. **[Vastaus]** |

## 12. Tietosuoja ja riskit

**Tietosuoja — kriittinen huomio [Vastaus, nostettu haastattelussa]:**

Tämä agentti on suunniteltu käsittelemään **oikeita kohdeyritys- ja asiakastietoja** (Odoosta poimittuja yhteystietoja, sopimushistoriaa, mahdollisia talouslukuja). Tämän harjoituskansion Claude Code -pääsy on annettu vain koulutuskurssin harjoituksia varten, eikä siihen saa syöttää oikeita henkilö- tai kolmannen osapuolen tietoja — vain synteettistä tai julkisesti saatavilla olevaa esimerkkidataa. Tästä syystä:

- Tämän määrittelyn testiajo (vaihe 5) tehtiin kahdella synteettisellä esimerkillä, ei oikealla Odoo-datalla.
- Agentin **tuotantokäyttö oikealla asiakas- ja kohdeyritysdatalla pitää tapahtua organisaation omassa, asianmukaisesti valtuutetussa ympäristössä** — ei tässä kurssipääsyssä.

**Riskit ja niiden hallinta:**

| Riski | Hallinta |
|---|---|
| Virheellinen tai keksitty tieto päätyy oikealle asiakkaalle asti tarjouksen kautta | Agentti ei keksi puuttuvia lukuja, ja ihmisen hyväksyntä on pakollinen ennen asiakaskäyttöä. **[Vastaus/Oletus]** |
| Versio 1:n laajuus (uusasiakashankinta + lisämyynti samassa agentissa) kasvattaa monimutkaisuutta ja virheriskiä verrattuna rajatumpaan ensimmäiseen versioon | Tietoisesti hyväksytty käyttäjän toimesta laajemman hyödyn ja yhtenäisen työkalun vuoksi. **[Vastaus]** |

## 13. Tarkistettava lopputulos ja onnistumisen mittarit

| Lopputulos | Muoto | Arvioija | Arviointiperusteet |
|---|---|---|---|
| **Sisäinen profiili** | Markdown: yritysprofiili, talous ja puutteet, toimialakatsaus, tarjonnan soveltuvuus | Konsultti itse | Onko rakenne selkeä, ovatko puutteet merkitty oikein? **[Oletus]** |
| **Asiakasversio (harkinnanvarainen)** | Lyhyt, asiakkaalle sopiva teksti | Konsultti itse | Sopiiko suoraan tarjoukseen/esitykseen ilman jatkomuokkausta? **[Oletus]** |

**Onnistumisen mittari [Vastaus]:** profilointiin käytetty aika lyhenee 1–3 tunnista 30–60 minuuttiin.

## 14. Esimerkkitapaukset testiajosta

- [Käyttötapaus 1: Uusasiakashankinta](b2b-myyntiassistentti/kayttotapaus-uusasiakashankinta.md) — synteettinen kohdeyritys "Louhikaari Kaivospalvelut Oy".
- [Käyttötapaus 2: Nykyasiakkaan lisämyynti](b2b-myyntiassistentti/kayttotapaus-lisamyynti.md) — C02 Teräskajo Koneistus Oy, hyödyntäen aiempaa Myynti-profiilia.

Molemmat paljastivat aukkoja, jotka on ratkaistu tähän versioon (kohdat 6 ja 8): puuttuvat tiedot kysytään kerralla, aiempaa profiilia saa käyttää pohjana, ja asiakasversio tehdään vain ajoituksen ollessa oikea.

## 15. Luonnos agentin järjestelmäpromptiksi

```markdown
# B2B-myyntiassistentti

## Rooli
Olet Tekoväläys Oy Ab:n B2B-myyntiassistentti. Profiloit kohdeyrityksen tai
nykyasiakkaan ja arvioit Tekoväläyksen palvelutarjonnan soveltuvuuden sille,
sekä uusasiakashankinnassa että nykyasiakkaiden lisämyynnissä.

## Tietolähteet ja rajaukset
- Käyttäjä antaa Odoo-tiedot ja muun taustatiedon käsin keskustelussa. Sinulla
  ei ole API-yhteyttä Odooon.
- Et hae tietoa verkosta. Käytä vain käyttäjän antamaa tietoa ja projektin
  sisäistä aineistoa (palveluluokitus, asiakascaset, aiemmat Myynti-profiilit).
- Et keksi puuttuvia tietoja, kuten talouslukuja. Merkitse puutteet avoimiksi.
- Et kirjaudu Odooon, Jiraan tai muihin järjestelmiin. Et lähetä mitään
  suoraan asiakkaalle.

## Työnkulku
1. Selvitä käyttötapaus (uusi kohde vai nykyasiakas) ja ota vastaan
   käyttäjän antamat tiedot.
2. Nykyasiakkaalle: tarkista, onko aiempi profiili olemassa
   (`03_asiakascaset/`, `Claude outputs/Myynti/`), ja käytä sitä pohjana.
   Kysy vain, mikä on muuttunut.
3. Kokoa kaikki puuttuvat välttämättömät tiedot yhteen kysymykseen kerralla.
   Älä kysy yksi kerrallaan.
4. Kirjoita sisäinen profiili: yritysprofiili, saatavilla oleva talous ja sen
   puutteet, toimialan yleinen kehitys (ei-yrityskohtainen), tarjonnan
   soveltuvuus ja jatkomyyntimahdollisuudet.
5. Arvioi, onko lisämyyntiin tai tarjoukseen jo ajoituksellisesti aihetta.
   Jos ei, perustele käyttäjälle, miksi asiakasversiota ei kannata vielä
   tehdä. Käyttäjä voi silti pyytää sen.
6. Jos ajoitus on oikea (tai käyttäjä pyytää), tiivistä lyhyt, asiakkaalle
   sopiva versio ilman sisäisiä huomioita tai keksittyjä lukuja.
7. Pyydä käyttäjää tarkistamaan ja hyväksymään tuotos ennen kuin sitä
   käytetään kohdeyritystä tai asiakasta kohtaan.

## Tietosuoja
Tämä agentti on tarkoitettu käytettäväksi organisaation omassa,
asianmukaisesti valtuutetussa ympäristössä oikealla asiakasdatalla.
Harjoitusympäristöissä käytä vain synteettistä tai julkista esimerkkidataa.
```

## 16. Avoimet kysymykset ja oletukset

| # | Kysymys | Tila |
|---|---|---|
| 1 | Tarvitaanko pitkäkestoinen toimialakatsausten muisti, ettei samaa yleistietoa kirjoiteta joka kerta uudelleen? | Avoin, ks. kohta 17 |
| 2 | Onko 30–60 minuutin aikatavoite oikea, kun agenttia on käytetty oikeasti? | Avoin, tarkentuu käytössä |
| 3 | Miten agentti tunnistaa käytännössä "milloin ajoitus on oikea" lisämyynnille — päätössääntö (kohta 8) on vielä yleisluontoinen | Avoin |
| 4 | Onko Odoo-integraatio (API-yhteys) tarpeen myöhemmin, jotta tietoja ei tarvitse antaa käsin? | Avoin, ks. kohta 17 |
| 5 | ~~Toteutetaanko tämä taitona (`Claude outputs/taidot/`) projektisuunnittelijan tapaan?~~ | Kyllä, taitona — toteutettu 2026-09-25 |

## 17. Jatkokehitysideat (versio 2)

- **Odoo-integraatio:** API-yhteys, jotta tietoja ei tarvitse antaa käsin.
- **Rajattu, luotettu verkkohaku** uusille kohdeyrityksille (esim. tilinpäätösrekisteri) täysin kielletyn haun sijaan, kunhan lähteet ja luotettavuus on ratkaistu.
- **Toimialakatsausten pitkäkestoinen muisti**, jotta samaa yleistä toimialatietoa ei tuoteta toistuvasti uudelleen samoille toimialoille.
- **Automaattinen kirjaus Jiraan tai Odooon**, kun profiili valmistuu.
- **Uusasiakashankinnan ja lisämyynnin eriyttäminen** omiksi kevyemmiksi agenteiksi, jos version 1 laajuus (molemmat käyttötapaukset samassa agentissa) osoittautuu käytössä liian isoksi.
