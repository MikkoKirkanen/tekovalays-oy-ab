---
name: yhteisen-ajan-etsija
description: Etsii tapaamiselle, palaverille, ohjausryhmälle, työpajalle tai työvaiheelle ajankohdan, joka sopii kaikille pakollisille osallistujille ja mahtuu aikataulun riippuvuuksien väliin. Palauttaa 2–3 perusteltua aikavaihtoehtoa ja listan vahvistettavista asioista. Käytä, kun pyydetään esimerkiksi "etsi kaikille sopiva aika", "milloin X ja Y ehtivät" tai "ehdota aikoja palaverille". Fasilitoija-taito käyttää tätä työpajojen ajankohdan etsimiseen.
---

# Yhteisen ajan etsijä

> **Itsenäinen taito.** Käytä tätä suoraan, kun tarvitaan aika yksittäiselle tapaamiselle tai palaverille. Jos samalla suunnitellaan työpajan ohjelmaa tai usean työvaiheen aikataulua, käytä [fasilitoija-taitoa](fasilitoija.md). Se kutsuu tämän taidon, kun kesto ja osallistujat on rajattu.

## Tehtävä

Etsit ajankohdan, joka

1. sopii kaikille pakollisille osallistujille
2. mahtuu vahvistetun keston ja tarvittavien esi- ja jälkivarausten kanssa aikaikkunaan
3. sopii projektin riippuvuuksiin, kuten edeltävän vaiheen päättymiseen ja seuraavaan päätösporttiin
4. jättää riittävästi aikaa valmisteluun ja jälkitöihin.

Et päätä ajankohtaa. Ehdotat vaihtoehdot, ja ihminen tai asiakas vahvistaa valinnan. Et lähetä kutsuja, kyselyjä etkä tee varauksia. Ne kuuluvat [kalenterikutsujen järjestäjälle](kalenterikutsujen-jarjestaja.md), ja niihin tarvitaan käyttäjän lupa.

## Lähtötiedot

Selvitä nämä käyttäjältä tai aineistosta. Kun fasilitoija kutsuu taidon, se antaa tiedot valmiina.

| Syöte | Esimerkki (C01-TP01) | Jos puuttuu |
|---|---|---|
| Tapahtuman tunnus ja nimi | C01-TP01, nykytilan tulkintatyöpaja | Kysy käyttäjältä |
| Vahvistettu kesto ja sen lähde | 120 min taukoineen, toimeksianto 1.0 | Kysy. Jos lähteissä on ristiriitaisia kestoja, älä etsi aikaa ennen kuin ristiriita on ratkaistu. |
| Esi- ja jälkivaraus | Tila 30 min ennen ja 30 min jälkeen (8.00–11.00) | Oletus: 15 min ennen, 15 min jälkeen. Merkitse oletukseksi. |
| Aikaikkuna | Projektiviikko 6, 9.–13.11.2026 | Kysy. Älä laajenna ikkunaa itse. |
| Riippuvuudet | Haastattelut päättyvät 6.11. P02 on 13.11. | Etsi projektin aikataulusta ja riskeistä |
| Osallistujat ja roolit | Ks. osallistujaluokat alla | Kysy käyttäjältä |
| Toivottu vuorokaudenaika | Aamu ennen kenttätöitä, oletus | Ehdota perusteltu oletus |
| Tila ja välineet | Tila kahdelle ryhmälle | Merkitse avoimeksi |
| Aikavyöhyke | Europe/Helsinki | Oletus Europe/Helsinki |

### Osallistujaluokat

Luokittele jokainen osallistuja ennen saatavuuden tarkistamista:

- **Pakollinen:** ilman häntä tapahtumaa ei kannata pitää. Esimerkiksi fasilitaattorit H044 ja H009 sekä toimitusjohtaja Mira Rautaketo.
- **Rooli pakollinen, henkilö vaihdettavissa:** roolin on oltava edustettuna, mutta henkilö voidaan valita joukosta. Esimerkiksi kaksi työnjohtajaa henkilöistä HE07–HE09 ja kaksi asentajaa henkilöistä HE01–HE06.
- **Toivottu:** läsnäolo parantaa tulosta, mutta tapahtuma voidaan pitää ilman häntä.
- **Korvaava:** nimetty varahenkilö, jos pakollinen ei pääse (vrt. riski R01).

Jos luokka ei selviä aineistosta, kysy käyttäjältä. Älä päättele sitä tittelistä.

## Saatavuuden tietolähteet

Käytä lähteitä tässä järjestyksessä ja kirjaa, mistä kunkin henkilön saatavuustieto on peräisin.

1. **Kalenteriyhteys.** Jos istunnossa on Microsoft 365 / Outlook -yhteys, hae vapaa–varattu-tieto sen avulla (esim. kokousajan saatavuushaku tai vapaan ajan haku). Lue vain varattu- ja vapaa-tieto. Älä avaa, kopioi tai raportoi muiden kalenterimerkintöjen sisältöä.
2. **Aineisto.** Tarkista projektien päällekkäisyydet, allokaatiot, lomat ja riskit. Esimerkiksi H044 Ronja Silokallio on samaan aikaan C06-projektin projektipäällikkö (17.8.–11.12.2026, [asiakassalkku](../../03_asiakascaset/asiakassalkku.md)). Päällekkäinen projekti ei yksin tarkoita, että henkilö on varattu. Se tarkoittaa, että saatavuus on tarkistettava.
3. **Saatavuuskysely.** Kun tieto puuttuu, laadi osallistujille lyhyt kysely ehdokasajoista (ks. kohta Kyselyluonnos). Kyselyn lähettää ihminen tai kalenterikutsujen järjestäjä käyttäjän luvalla.

**Synteettinen aineisto:** tämän kansion henkilöt ja `.example`-osoitteet ovat kuvitteellisia. Älä hae niillä oikeista kalentereista äläkä lähetä niihin mitään. Merkitse heidän saatavuutensa tilaan *tuntematon* tai käytä aineistosta pääteltyä tietoa lähteineen.

## Menettely

1. **Rajaa ikkuna.** Poista ikkunasta päivät, jotka rikkovat riippuvuuksia. Kirjaa jokaiselle poistolle syy. Esimerkki: ma 9.11 jättäisi haastattelujen (päättyvät 6.11) analyysille vain viikonlopun.
2. **Muodosta ehdokasajat.** Laadi jokaiselle jäljelle jäävälle päivälle 1–3 aikaa toivotun vuorokaudenajan mukaan. Varaa ajalle kesto sekä esi- ja jälkivaraus.
3. **Tarkista saatavuus.** Merkitse jokaiselle osallistujalle ja ehdokasajalle tila: *vapaa*, *alustava*, *varattu* tai *tuntematon*, sekä lähde.
4. **Arvioi ehdokkaat** tässä järjestyksessä:
   1. Kaikki pakolliset ovat vapaita. Jos joku on varattu, ehdokas hylätään.
   2. Jokainen pakollinen rooli voidaan täyttää vapaalla henkilöllä.
   3. Riippuvuuksiin jää riittävästi aikaa ennen ja jälkeen.
   4. Toivottujen osallistujien määrä.
   5. Tuntemattomien tilojen määrä. Mitä vähemmän, sitä parempi.
5. **Valitse 2–3 vaihtoehtoa** ja suositus. Kirjaa jokaiselle peruste ja heikkous.
6. **Listaa vahvistettavat asiat.** Kuka vahvistaa ajan, mitkä saatavuudet ovat tuntemattomia ja mihin mennessä vahvistus tarvitaan.

## Kun kaikille sopivaa aikaa ei löydy

Älä valitse aikaa, jolloin pakollinen osallistuja on varattu. Älä myöskään lyhennä vahvistettua kestoa tai laajenna aikaikkunaa omin päin. Esitä käyttäjälle vaihtoehdot ja niiden vaikutukset:

- Korvaava henkilö pakolliseen rooliin (esim. R01:n mukainen korvaava työnjohtaja).
- Aikaikkunan laajentaminen ja vaikutus riippuvuuksiin (esim. P02:n valmisteluaika lyhenee).
- Toivotun osallistujan jättäminen pois ja tapa, jolla hänen näkemyksensä kerätään muuten.
- Keston muuttaminen, joka vaatii toimeksiannon vahvistajan päätöksen.

## Kyselyluonnos

Kun saatavuus on tuntematon, laadi kysely valmiiksi, mutta älä lähetä sitä:

> **Aihe:** Sopiiko jokin näistä ajoista: [tapahtuman nimi]?
>
> Hei, etsimme aikaa [kesto] mittaiselle [tapahtumalle]. Merkitse jokaisen ajan kohdalle *sopii*, *sopii tarvittaessa* tai *ei sovi*:
>
> 1. [päivä ja kellonaika]
> 2. [päivä ja kellonaika]
> 3. [päivä ja kellonaika]
>
> Vastaathan [päivämäärä] mennessä. Varsinainen kutsu lähetetään, kun aika on vahvistettu.

## Lopputulos

1. **Suositus ja vaihtoehdot**

   | Vaihtoehto | Ajankohta (tapahtuma / varaus) | Peruste | Heikkous |
   |---|---|---|---|

2. **Saatavuusmatriisi:** osallistujat riveillä, ehdokasajat sarakkeissa, soluissa tila ja lähde.
3. **Hylätyt päivät ja syyt.**
4. **Oletukset**, kuten vuorokaudenaika ja esi- ja jälkivaraukset.
5. **Vahvistettavat asiat:** kuka vahvistaa, mitä ja mihin mennessä. Mukana kyselyluonnos, jos saatavuus on tuntematon.

## Esimerkki: C01-TP01

Pohjana on [C01-TP01:n aikataulu ja ohjelma](../C01_tyopajat/C01-TP01_aikataulu_ja_ohjelma.md).

| Vaihtoehto | Ajankohta | Peruste | Heikkous |
|---|---|---|---|
| **A, suositus** | Ti 10.11.2026 klo 8.30–10.30, tila 8.00–11.00 | Koonnille jää maanantai. Muistio ja P02-esitys ehditään ke–to. | Ennakkoaineisto jaetaan vasta ma 9.11 |
| B | Ke 11.11.2026 klo 8.30–10.30 | Enemmän aikaa analyysille, ennakkoaineisto pe 6.11 | P02:n valmisteluun jää vain torstai |
| Hylätty | Ma 9.11 | – | Haastattelut päättyvät pe 6.11, joten analyysi ei valmistu |
| Hylätty | Pe 13.11 | – | P02-kokous samana päivänä, tuotokset eivät ehdi syötteeksi |

Saatavuusmatriisin tila on aineiston perusteella *tuntematon* kaikille Kaarisillan osallistujille. H044:n saatavuus on tarkistettava C06-projektin vuoksi. Vahvistettavat asiat: Janne Kivisilta vahvistaa ajan, nimetyt työnjohtajat ja asentajat sekä korvaavat henkilöt viimeistään P01:ssä 16.10.2026.
