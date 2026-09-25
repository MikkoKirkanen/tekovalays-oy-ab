# Myynti — asiakasprofiilit ja tarjonnan soveltuvuus

Tähän kansioon on koottu myynnin lopputuotokset: jokaisesta hyväksytystä (sopimuksen tehneestä) asiakkaasta oma alikansio ja profiili. Kaikki asiakkaat ja luvut ovat kuvitteellisia (ks. [05_aineiston_ohjeet](../../05_aineiston_ohjeet/aineiston_kaytto_ja_oletukset.md)). Laadittu 2026-09-25.

**Rajaus ja tulkinta:** "Hyväksytty asiakas" = [asiakassalkun](../../03_asiakascaset/asiakassalkku.md) seitsemän casea (C01–C07). Kaikilla on allekirjoitettu toimeksianto ja sopimusarvo, joten kaikki on tulkittu hyväksytyiksi asiakkaiksi riippumatta toimeksiannon tilasta (sovittu/käynnissä/toimitettu). Jos tarkoitit tällä jotain rajatumpaa asiakasjoukkoa, kerro niin.

**Kansiorakenne:** tämä kansio on projektin vakiintuneen tavan mukaisesti kansiossa `Claude outputs/Myynti/`. Jos tarkoitit projektin juureen tulevaa erillistä `Myynti/`-kansiota, siirrän sen sinne pyynnöstä.

## Asiakkaat ja profiilit

| Asiakas | Päätoimiala | Nykyinen toimeksianto | Sopimusarvo | Tila | Profiili |
|---|---|---|---:|---|---|
| C01 Kaarisilta Teollisuuspalvelut Oy | Teollisuuden kunnossapito | Kokonaisvaltainen liiketoiminnan kehitys | 180 000 € | Sovittu, ei alkanut | [profiili.md](C01-kaarisilta/profiili.md) |
| C02 Teräskajo Koneistus Oy | Metalliteollisuus | Elinkaaripalvelun konsepti | 72 000 € | Käynnissä | [profiili.md](C02-teraskajo/profiili.md) |
| C03 Viljakaari Elintarvikkeet Oy | Elintarviketeollisuus | Ammattikeittiöiden brändi ja lanseeraus | 88 000 € | Käynnissä | [profiili.md](C03-viljakaari/profiili.md) |
| C04 Leporanta Majoituspalvelut Oy | Matkailu ja majoitus | Sesongin ulkopuolinen palvelukonsepti | 54 000 € | Käynnissä | [profiili.md](C04-leporanta/profiili.md) |
| C05 Sujuvaura Talouspalvelut Oy | Taloushallinnon palvelut | Asiakkuuden aloituksen uudistus | 46 000 € | Toimitettu, seuranta käynnissä | [profiili.md](C05-sujuvaura/profiili.md) |
| C06 Kiertokajo Materiaalit Oy | Materiaalien kierrätys ja jalostus | Palautuspalvelu ja aktivointikampanja | 68 000 € | Käynnissä | [profiili.md](C06-kiertokajo/profiili.md) |
| C07 Oppiluoto Yritysvalmennus Oy | Koulutus- ja valmennuspalvelut | Strategia ja tuotteistettu palveluvalikoima | 62 000 € | Sovittu, ei alkanut | [profiili.md](C07-oppiluoto/profiili.md) |

Jokainen profiili sisältää: yritysprofiilin, käytettävissä olevat taloustiedot (ja niiden puutteet), päätoimialan yleisen kehitysanalyysin sekä Tekoväläyksen palvelutarjonnan ([palvelut_ja_ansainta.md](../../01_yritys/palvelut_ja_ansainta.md)) soveltuvuuden ja jatkomyyntimahdollisuudet kyseiselle asiakkaalle.

## Läpileikkaava havainto: taloustiedon puute

**Yhdessäkään** seitsemästä asiakascasesta ei ole asiakasyrityksen omaa taloustietoa (liikevaihto, tulos, tase). Lähdeaineisto (`03_asiakascaset/`) sisältää vain:

- Tekoväläyksen oman sopimusarvon kyseisestä toimeksiannosta,
- toimeksiannon operatiiviset tavoitemittarit (esim. käyttökate-%-tavoite, huonekäyttöaste, läpimenoaika) — nämä ovat asiakkaan itselleen asettamia skenaariotavoitteita, eivät toteutunutta tilinpäätöstietoa,
- joissain tapauksissa asiakkaan erillisen kampanjabudjetin (esim. mediavaraus).

Tämä on merkitty jokaiseen profiiliin avoimeksi kohdaksi sen sijaan, että lukuja olisi arvattu tai keksitty. Jos taloustietoja (esim. luottokelpoisuus, ostovoima laajemmalle myynnille) tarvitaan jatkossa, ne on pyydettävä asiakkaalta erikseen tai haettava julkisista rekistereistä — kumpaakaan ei ole tehty tässä työssä.

## Läpileikkaava havainto: toimialojen kehitysanalyysi on yleistä markkinatietoa

Jokaisen profiilin kohta 3 (päätoimialan kehitys) perustuu laatijan yleistietoon toimialan pitkän aikavälin ilmiöistä (esim. palveluliiketoimintaan siirtyminen, sääntelyn kiristyminen, digitalisaatio), ei ajantasaiseen tilastohakuun tai reaaliaikaiseen markkinadataan. Analyysit koskevat toimialaa yleisesti, eivät kyseistä kuvitteellista yritystä. Jos tarvitset tuoreempaa tai tarkempaa toimialadataa, se vaatii erillisen tiedonhaun.

## Yhteenveto myyntimahdollisuuksista

| Asiakas | Suurin yksittäinen jatkomyyntiavaus |
|---|---|
| C01 Kaarisilta | Jatkuva kuukausipalvelu sopimuskannan ylläpitoon ja laajentamiseen pilotin jälkeen |
| C02 Teräskajo | Kapasiteetin/hinnoittelun mallinnus ennen elinkaaripalvelun laajempaa skaalausta |
| C03 Viljakaari | Jatkotutkimus uusintatilausten esteistä (60→15 tavoitteen iso pudotus) |
| C04 Leporanta | Pakettikohtaisen katteen mittaaminen ennen kampanjan skaalausta |
| C05 Sujuvaura | Lyhyt jatkojakso tavoitteen ja toteuman erotuksen syiden selvittämiseksi |
| C06 Kiertokajo | Ympäristövaikutuksen mittausmenetelmän ja vertailutason määrittely (asiakas on jo tunnistanut tarpeen) |
| C07 Oppiluoto | Brändi- ja myyntimallityö tarjousajan lyhenemistavoitteen (30.6.2027) toteuduttua |

## Avoimet kysymykset käyttäjälle

1. Onko "hyväksytty asiakas" tulkittu oikein (kaikki seitsemän asiakassalkun casea) vai tarkoititko rajatumpaa joukkoa, esimerkiksi vain tiettyä tilaa?
2. Onko `Claude outputs/Myynti/` oikea sijainti, vai halusitko kansion suoraan projektin juureen?
3. Tarvitaanko toimialan kehitysanalyysiin ajantasaista tiedonhakua (esim. verkkohaku) yleistiedon sijaan?
