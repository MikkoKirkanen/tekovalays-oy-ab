# CLAUDE.md — Tekoväläys Oy Ab

Ohjeet tekoälyagenteille, jotka työskentelevät tämän kansion aineiston parissa.

Tämä on **ensisijainen ja ainoa ohjeistiedosto** tälle kansiolle. CLAUDE.md pidetään ajan tasalla: sitä päivitetään aina, kun uusi ohjeistustarve tunnistetaan.

## Työskentely tässä kansiossa

- **Työkansio on `Tekoväläys Oy Ab/`.** Istunnot avataan tähän kansioon, ja kaikki polut kirjoitetaan suhteessa siihen.
- **Tämän tiedoston polku on `Tekoväläys Oy Ab/CLAUDE.md`.** Tiedosto on tämän kansion ja projektin ohjeiden ensisijainen lähde. Lue se ja noudata sitä ennen muita ohjeita.
- Kansio on itsenäinen kokonaisuus: kaikki ohjeet, agentit, taidot ja aineisto ovat sen sisällä, eikä ylempiin kansioihin viitata. Tämä on ainoa CLAUDE.md, joka ladataan automaattisesti. Lue tarvittaessa:
  - [`README.md`](README.md): aineiston sisällysluettelo ja yleiskuva yrityksestä, organisaatiosta, asiakascaseista ja C01-projektista.
  - [`05_aineiston_ohjeet/aineiston_kaytto_ja_oletukset.md`](05_aineiston_ohjeet/aineiston_kaytto_ja_oletukset.md): aineiston tunnisteet, ensisijaiset lähteet ja oletukset. Lue tämä ennen kuin tuotat tai muutat aineistoa.
- Jos ohjeet ovat ristiriidassa, tämä tiedosto on määräävä tässä kansiossa.
- **Tuotokset tallennetaan kansioon `Claude outputs/`** kategorioittain Markdown-tiedostoina. Luo alikansio, kun samaan kokonaisuuteen syntyy useita tiedostoja. Lähdeaineistoa (`01_`–`05_`) muutetaan vain, kun käyttäjä pyytää aineiston päivittämistä. Vakiintuneet alikansiot:
  - `.claude/agents/`: Claude Coden tämän projektin subagenttien määrittelyt YAML-etutunnisteineen ja ohjeineen. Pääagentti `fasilitoija.md` on juuressa, apulaiset kategoriakansioissa (nyt `fasilitointi/`).
  - `Claude outputs/taidot/`: tämän kansion taidot ja agentit, myös fasilitoinnin taito (ks. [Taidot ja agentit](#taidot-ja-agentit))
  - `Claude outputs/agenttimaarittelyt/`: agenttihaastatteluista syntyneet agenttimäärittelyt
  - `Claude outputs/projektisuunnitelmat/<tunnus>-<asiakas>/`: projektisuunnittelijan suunnitelmat versioineen ja Jira-vientilokit
- Kansiossa `Claude outputs/` oleva CLAUDE.md vain ohjaa tähän tiedostoon. Älä ylläpidä siellä erillistä kopiota.
- **Kutsu ominaisuuksia niiden oikeilla nimillä.** Claude Code -aliagentit (subagentit) ovat kansiossa `.claude/agents/`. Taidot ja työohjeet ovat Markdown-tiedostoja kansiossa `Claude outputs/taidot/`. Ne eivät ole Claude Coden automaattisesti lataamia `SKILL.md`-taitoja: pääagentti avaa ja noudattaa niitä. Kun kerrot työstä, sano lyhyesti, mitä teit ja mitä sait aikaan, ja mainitse agentti tai ohje vain, jos sillä on merkitystä tuloksen luotettavuudelle. Älä väitä käyttäneesi agenttia tai ohjetta, jota et käyttänyt.

## Taidot ja agentit

Tämä luettelo kertoo, mitkä taidot ja agentit ovat käytössä tässä kansiossa ja milloin niitä käytetään. Lue kyseinen tiedosto ja noudata sitä, kun tehtävä vastaa käyttötilannetta.

| Taito tai agentti | Tiedosto | Käytä, kun | Alisteiset taidot |
|---|---|---|---|
| Fasilitoija | [Pääagentti](.claude/agents/fasilitoija.md) ja [fasilitoinnin menettelyohje](Claude%20outputs/taidot/fasilitoija.md) | suunnitellaan työpajoja, yhteistä työskentelyä tai tehtävien, tapaamisten ja työvaiheiden aikataulua. Pääagentti tarkistaa tästä tiedostosta käytössä olevat taidot ja subagentit, delegoi sopivat tehtävät ja kokoaa vastauksen. Agentti on käynnistyspiste ja ohje sen menettely; ne täydentävät toisiaan eivätkä ole päällekkäisiä. Pelkkä ajan etsiminen tai kutsu yksittäiseen tapaamiseen hoidetaan suoraan kahdella seuraavalla taidolla. | – |
| Yhteisen ajan etsijä | [`Claude outputs/taidot/yhteisen-ajan-etsija.md`](Claude%20outputs/taidot/yhteisen-ajan-etsija.md) | etsitään kaikille sopivaa aikaa tapaamiselle, palaverille tai työvaiheelle. Fasilitoija käyttää tätä työpajojen ajankohtiin. | – |
| Kalenterikutsujen järjestäjä | [`Claude outputs/taidot/kalenterikutsujen-jarjestaja.md`](Claude%20outputs/taidot/kalenterikutsujen-jarjestaja.md) | laaditaan, lähetetään, siirretään tai perutaan kalenterikutsuja. Lähetys vain käyttäjän luvalla. Fasilitoija käyttää tätä työpajojen kutsuihin. | – |
| AI haastattelee agentin luomisesta | [`Claude outputs/taidot/ai-haastattelee-agentin-luomisen.md`](Claude%20outputs/taidot/ai-haastattelee-agentin-luomisen.md) | ideoidaan, valitaan tai määritellään agenttia, esimerkiksi "mikä agentti meidän kannattaisi tehdä" tai "haastattele meitä agentista" | – |
| Projektisuunnittelija | [`Claude outputs/taidot/projektisuunnittelija.md`](Claude%20outputs/taidot/projektisuunnittelija.md) | tarjous on hyväksytty ja siitä tehdään projektisuunnitelma, joka viedään Jiraan (TOA), esimerkiksi "tee projektisuunnitelma tarjouksesta" tai "vie projekti Jiraan". Taito lukee ja päivittää [pilkkomisohjetta](Claude%20outputs/taidot/projektisuunnittelija/pilkkomisohje.md). Tiketit luodaan vain käyttäjän luvalla. | – |
| B2B-myyntiassistentti | [`Claude outputs/taidot/b2b-myyntiassistentti.md`](Claude%20outputs/taidot/b2b-myyntiassistentti.md) | profiloidaan kohdeyritys tai nykyasiakas ja arvioidaan Tekoväläyksen tarjonnan soveltuvuus, esimerkiksi "profiloi tämä kohdeyritys" tai "onko tälle asiakkaalle lisämyyntimahdollisuutta". Tiedot annetaan taidolle käsin (esim. Odoosta); taito ei hae tietoa verkosta eikä kirjaudu järjestelmiin. Syntyi [agenttihaastattelusta](Claude%20outputs/agenttimaarittelyt/agenttimaarittely-b2b-myyntiassistentti.md). Tarkoitettu oikean asiakasdatan käsittelyyn organisaation omassa valtuutetussa ympäristössä, ei tähän harjoituskansioon. | – |

### Fasilitoijan subagentit

Claude Code tunnistaa projektin subagentit kansiosta `.claude/agents/` alikansioineen. Kategoriakansio (esim. `fasilitointi/`) vain järjestää tiedostoja: agentin tunniste tulee `name`-kentästä, eikä kansio luo hierarkiaa. Fasilitoija käynnistetään ensisijaisena agenttina komennolla `claude --agent fasilitoija`; se voi delegoida vain tässä luetelluille apulaisille.

| Subagentti | Määrittely | Tehtävä ja raja |
|---|---|---|
| Taustatutkija | [taustatutkija.md](.claude/agents/fasilitointi/taustatutkija.md) | Kokoaa rajatuista lähteistä havainnot, ristiriidat ja lähdeviitteet. Vain luku. |
| Ohjelmasuunnittelija | [ohjelmasuunnittelija.md](.claude/agents/fasilitointi/ohjelmasuunnittelija.md) | Ehdottaa ohjelmarungon vahvistettujen tavoitteiden ja rajoitteiden pohjalta. Vain luku. |
| Työpajan laaduntarkistaja | [tyopajan-laaduntarkistaja.md](.claude/agents/fasilitointi/tyopajan-laaduntarkistaja.md) | Tarkistaa ohjelmaluonnoksen tavoitetta, lähteitä ja aikarajoja vasten erillisessä kontekstissa. Ei hyväksy ohjelmaa. Vain luku. |

### Uuden taidon tai agentin lisääminen

- **Dokumentoi uusi taito tai agentti automaattisesti samassa työssä, jossa luot sen.** Päivitä tämän tiedoston luettelo ja vastaavan päätiedoston taitokartta heti, kun uusi tiedosto on luotu. Älä jätä dokumentointia myöhempään tehtävään tai pyydä erillistä lupaa pelkän luettelon ylläpitämiseen.
- Fasilitoija käyttää tätä taulukkoa ajantasaisena taitokarttana. Lisää vain tiedostot, jotka ovat olemassa; tarkista polut, käyttötilanne ja työnjako ennen muutoksen tallentamista.
- Kun luot, poistat tai siirrät subagentin `.claude/agents/`-kansiossa, päivitä samalla yllä oleva subagenttiluettelo ja Fasilitoijan sallittujen delegointien lista. Lisää tai poista `Agent(nimi)`-rajaus Fasilitoijan etutunnisteesta vastaamaan todellisia tiedostoja.
- **Jokainen uusi itsenäinen taito tai agentti lisätään yllä olevaan taulukkoon heti luomisen yhteydessä.** Alisteinen taito liitetään päätaidon omalle riville eikä lisätä itsenäiseksi riviksi.
- **Alisteinen taito** on taito, jota käytetään vain toisen taidon osana, esimerkiksi fasilitoijan kutsuma aikataulutus- tai tarkistusohje, joka ei ole subagentti. Alisteista taitoa ei lisätä taulukkoon omaksi rivikseen. Sen sijaan:
  1. Merkitse se pääriville sarakkeeseen "Alisteiset taidot" linkkinä.
  2. Kuvaa pääyksikön tiedostossa, missä vaiheessa ja millä syötteillä alisteinen taito kutsutaan ja mitä se palauttaa.
  3. Kirjoita alisteisen taidon tiedoston alkuun, minkä taidon alainen se on ja ettei sitä käytetä itsenäisesti.
- **Ketjutus:** Kun käytät taitoa, jolla on alisteisia taitoja, käytä ne pääyksikön tiedoston ohjeen mukaisessa kohdassa. Älä käynnistä alisteista taitoa suoraan käyttäjän pyynnöstä ohi pääyksikön, ellei käyttäjä nimenomaisesti pyydä sitä.
- Jos taito myöhemmin muuttuu itsenäiseksi tai alisteiseksi, siirrä se taulukossa oikeaan paikkaan ja päivitä molemmat tiedostot.
- Tallenna uudet taidot kansioon `Claude outputs/taidot/`. Alisteiset taidot voi koota pääyksikön nimiseen alikansioon, esimerkiksi `Claude outputs/taidot/fasilitoija/`.
- Jos taito poistetaan tai siirretään, päivitä samalla päätaidon linkit ja tämä taulukko, jotta fasilitoija ei tarjoa vanhentunutta taitoa.

## Integraatiot

- **Jira / Atlassian**: Projektin Jira-instanssi on `vaelion.atlassian.net` (Atlassian-projekti "Tekoväläys Oy Ab", avain `TOA`). Käytä tehtävien, tikettien ja backlogin hallintaan **Atlassian MCP** -yhteyttä (ei erillistä web-hakua tai manuaalista kopiointia), kun se on saatavilla istunnossa.
- **Kalenteri / Microsoft 365**: Saatavuuden tarkistamiseen ja kalenterikutsuihin käytetään istunnon Microsoft 365 / Outlook -yhteyttä, kun se on saatavilla (ks. taidot Yhteisen ajan etsijä ja Kalenterikutsujen järjestäjä). Kalentereista luetaan vain vapaa- ja varattu-tieto. Kutsut lähetetään vain käyttäjän nimenomaisella luvalla. Aineiston kuvitteellisille henkilöille ja `.example`-osoitteisiin ei lähetetä mitään.
- Käytä yleisesti olemassa olevia työkaluja ja integraatioita mahdollisuuksien mukaan ennen kuin turvaudut muihin tapoihin (esim. selainautomaatioon).

## Aineisto

Tämä kansio sisältää synteettistä harjoitusaineistoa Tekoväläys Oy Ab -nimisestä kuvitteellisesta yrityksestä (ks. [README.md](README.md)). Kaikki henkilöt, asiakasyritykset ja luvut ovat kuvitteellisia.

## Ylläpito

- CLAUDE.md on ensisijainen lähde tälle kansiolle annettaville agenttiohjeille ja käytössä olevien taitojen luettelolle.
- Kun uusi tarve, integraatio tai käytäntö tunnistetaan työskentelyn yhteydessä, päivitä se tähän tiedostoon, ei kopioihin.
- Kun uusi taito tai agentti luodaan, päivitä kohta [Taidot ja agentit](#taidot-ja-agentit), subagenttien luettelo tarvittaessa ja sen päätaidon ohje samalla kertaa. Tämä dokumentointipäivitys on osa taidon tai agentin luomista.

_Päivitetty: 2026-09-25 (lisätty B2B-myyntiassistentti-taito agenttihaastattelun pohjalta)_
