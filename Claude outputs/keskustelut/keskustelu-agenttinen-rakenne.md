# Ohje: agenttirakenteen selvittäminen ja uudistaminen kategorioittain

> Tämä ohje etenee kahdessa vaiheessa. Kussakin vaiheessa annat Claudelle promptin ja näet, millainen vastaus todennäköisesti seuraa. Vastaukset ovat esimerkkejä. Tarkat tiedostot ja sanamuodot riippuvat kansion tilasta. Ohje perustuu 25.9.2026 käytyyn keskusteluun. Kansion nimi on `Tekoväläys Oy Ab/`.

---

## Vaihe 1: selvitä, mitä agentteja ja ohjeita on

### Tee tämä prompti

```
Etsi agenttiset ja subagenttiset ohjeet projektista.
```

### Todennäköinen vastaus

Claude etsii tiedostoja ja ryhmittelee ne. Se lukee yleensä vain tiedostolistan eikä yksittäisten tiedostojen sisältöä. Vastaus näyttää suunnilleen tältä:

- **Ensisijainen ohjelähde** on `CLAUDE.md`. Siinä on taito- ja agenttiluettelo, subagenttien luettelo, säännöt uuden taidon lisäämiseen ja integraatiot (Jira, kalenteri). `Claude outputs/CLAUDE.md` ohjaa vain tähän. Yläkansion `syntetisoitu-data.md` mainitsee myös agentteja.
- **Subagentit** ovat kansiossa `.claude/agents/`:
  - `fasilitoija.md` on pääagentti. Se käynnistetään komennolla `claude --agent fasilitoija` ja se delegoi vain kahdelle apulaiselle.
  - `taustatutkija.md` kokoaa havainnot ja lähdeviitteet. Se lukee vain.
  - `ohjelmasuunnittelija.md` ehdottaa ohjelmarungon. Se lukee vain.
- **Taidot** ovat kansiossa `Claude outputs/taidot/`:
  - `fasilitoija.md` ja sen alisteinen `fasilitoija/tyopajan-laaduntarkistaja.md`
  - `yhteisen-ajan-etsija.md`
  - `kalenterikutsujen-jarjestaja.md` (lähetys vain luvalla)
  - `ai-haastattelee-agentin-luomisen.md`
  - `projektisuunnittelija.md` ja sen muisti `projektisuunnittelija/pilkkomisohje.md`
- **Agenttimäärittelyt** ovat kansiossa `Claude outputs/agenttimaarittelyt/`, esimerkiksi `agenttimaarittely-projektisuunnittelija.md`.

Vastauksen lopussa Claude kertoo, että se luki vain tiedostolistan, ja tarjoutuu lukemaan tarkemmin tai tarkistamaan, että CLAUDE.md:n luettelo vastaa tiedostoja.

### Mitä tästä opitaan

Agenttiset ohjeet ovat nyt kahdessa paikassa: subagentit kansiossa `.claude/agents/` ja taidot kansiossa `Claude outputs/taidot/`. Tämä on lähtökohta seuraavalle vaiheelle.

---

## Vaihe 2: pyydä suunnitelma uudesta rakenteesta

### Tee seuraavaksi tämä prompti

```
Päivitä agenttinen rakenne noudattamaan tätä: CLAUDE.md .claude/   agents/     fasilitoija.md     kategoria/       uniikkinimi.md     kategoria/       uniikkinimi.md     kategoria/       uniikkinimi.md - tee suunnitelma hyväksymistä varten ja näytä miten järjestäisit ja muuttaisit nykyistä tilannetta.
```

### Todennäköinen vastaus

Claude ei aloita muutoksia vaan lukee ensin nykyiset agentti- ja taitotiedostot ja esittää suunnitelman hyväksyttäväksi. Suunnitelma sisältää tyypillisesti nämä osat:

1. **Tavoiterakenne puuna**, jossa juuressa on `fasilitoija.md` ja sen alla kategoriakansiot, esimerkiksi `fasilitointi/`, `aikataulutus/`, `projektinhallinta/` ja `agenttisuunnittelu/`. Jokaisessa kansiossa on uniikkinimisiä agenttitiedostoja.
2. **Siirtotaulukko**, jossa jokaiselle nykyiselle tiedostolle on uusi paikka ja tehtävä muutos (siirto, frontmatterin lisäys tai yhdistäminen). Esimerkiksi:
   - subagentit `taustatutkija` ja `ohjelmasuunnittelija` siirtyvät kansioon `fasilitointi/`
   - taidot muuttuvat agenttitiedostoiksi, kun niihin lisätään frontmatter (`name`, `description`, `tools`)
   - Fasilitoijan agentti ja taito yhdistetään yhdeksi tiedostoksi, jotta `name` ei esiinny kahdesti
3. **Työvaiheet**: siirrot `git mv`:llä, frontmatterit, Fasilitoijan `Agent(...)`-rajauksen päivitys, sisäisten linkkien korjaus, `CLAUDE.md`:n luettelon uudelleenkirjoitus ja lopuksi tarkistus rikkinäisten polkujen varalta.
4. **Riskit ja päätettävät asiat**, joihin sinun pitää vastata ennen toteutusta:
   - Mihin `pilkkomisohje.md` sijoitetaan, koska se on muistitiedosto eikä agentti. Suositus on erillinen kansio, esimerkiksi `.claude/muisti/`.
   - Mitkä agentit voi delegoida taustalle ja mitkä vaativat keskustelua käyttäjän kanssa. Subagentti ei voi keskustella käyttäjän kanssa, joten haastattelija, projektisuunnittelija ja kalenterikutsujen järjestäjä ajetaan pääagenttina.
   - Lukeeko Claude Code alikansiot rekursiivisesti. Se tarkistetaan siirron jälkeen.
   - Kategorioiden nimet, jotka on helppo vaihtaa ennen toteutusta.

Vastaus päättyy kysymykseen, hyväksytkö suunnitelman. Claude ei muuta tiedostoja ennen hyväksyntääsi.

### Mitä tästä opitaan

Kun pyydät suunnitelmaa hyväksymistä varten, Claude erottaa suunnittelun ja toteutuksen. Näet kaikki siirrot ja avoimet päätökset etukäteen, ja voit korjata ne ennen kuin mitään muuttuu.

