# H4 Maailma kuulee

Neljännen viikon tehtävänä oli tiivistää artikkelit [Teoriasta käytäntöön pilvipalvelimen avulla](https://susannalehto.fi/2022/teoriasta-kaytantoon-pilvipalvelimen-avulla-h4/) sekä [First Steps on a New Virtual Private Server – an Example on DigitalOcean and Ubuntu 16.04 LTS](https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/). Harjoituksina tuli vuokrata oma virtuaalipalvelin, tehdä sille alkutoimenpiteet ja vaihtaa Apachen testisivu omaan tuotokseen. Viimeisenä tuli vuokrata oma domain-nimi ja asettaa se osoittamaan juuri hankkimaamme virtuaalipalvelimeen. (Karvinen 2024.)

## Tiivistelmät

### Teoriasta käytäntöön pilvipalvelimen avulla

- Pilvipalvelimia voi vuokrata eri palveluntarjoajilta, esimerkiksi DigitalOcean tarjoaa palvelinten vuokrausta. Vuokrattava pilvipalvelimen tehokkuus tulee valita omien tarpeiden mukaan. On kuitenkin suositeltavaa aloittaa halvimmasta sopivasta vaihtoehdosta, sillä palvelimen tehoja saa helposti lisättyä jälkikäteenkin.
- Domain-nimiä voi myös vuokrata useilta eri palveluntarjoajilta, esimerkiksi Namecheap on tällainen. Vuokrattu nimi tulee osoittaa palvelimen IP-osoitteeseen, jotta domain-nimelle tuleva liikenne ohjautuu halutulle palvelimelle.
- Virtuaalipalvelinta voi käyttää halutulla tietokoneella SSH-yhteyden avulla.
- Kun palvelimen ottaa käyttöön, tulisi tehdä seuraavat toimenpiteet;
  - Suojata palvelin palomuurilla, sekä avata ainoastaan tarvittavat portit liikenteelle.
  - Tehdä oma pääkäyttäjä hyvällä salasanalla, ja sen jälkeen sulkea root.
  - Päivittää ja asentaa palvelimen ohjelmat.
- Näiden toimenpiteiden jälkeen palvelinta voi käyttää haluamaansa tarkoitukseen, esim. omille kotisivuille kuten artikkelin kirjoittaja oli tehnyt.
- Virtuaalipalvelimen lokeja voi tarkastella hakemistosta `/var/log/auth.log`, ja sieltä voi tunnistaa vaikkapa murtautumisyrityksiä.

(Lehto 14.02.2022.)

### First Steps on a New Virtual Private Server – an Example on DigitalOcean and Ubuntu 16.04 LTS

- Virtuaalipalvelimen fyysinen sijainti kannattaa valita loppukäyttäjien sijainnin mukaan, eli suomalaisille pidettävän sivuston palvelimen olisi hyvä sijaita Euroopassa.
- Kun virtuaalipalvelin on luotu, generoituu sille IP-osoite. Palvelinta voi käyttää SSH-yhteydellä komennolla `$ ssh root@palvelimen IP-osoite`.
- Ennen palomuurin käyttöönottoa, tulee palomuurin asetuksista sallia SSH-yhteys komennolla `$ sudo ufw allow 22/tcp`.
- Palvelimelle voi lisätä käyttäjän komennolla `$ sudo adduser kayttaja`. Samalla komennolla `$ sudo adduser kayttaja sudo` voi asettaa käyttäjän pääkäyttäjäksi.
- Palvelimen ohjelmistot kannattaa myös päivittää, sillä niiden vanhoissa versioissa on usein tietoturvauhkia.
- Kun palvelimelle asentaa julkisen weppipalvelimen tulee sen käyttämä portti avata palomuurin asetuksista komennolla `$ sudo ufw allow 80/tcp`.
- Kun koneelle on asennettu weppipalvelin, verkkosivustolle voi päästä palvelimen IP-osoitteella. Mikäli sivuston haluaa toimivan nimellä, tulee domain-nimi vuokrata palveluntarjoajalta ja yhdistää se palvelimen IP-osoitteeseen.

(Karvinen 19.09.2017)

## Virtuaalipalvelimen hankinta ja käyttöönotto

Aloitin tehtävien tekemisen klo 17:00 pohtimalla mitä palveluntarjoajaa käytän tehtävässä. Päädyin käyttämään [DigitalOceania](https://www.digitalocean.com/) virtuaalipalvelimen vuokraamiseen, sillä sain sinne ilmaiseksi 200$ edestä käyttövaroja GitHubin Education-paketin myötä. Käytin tehtävässä ohjeena artikkeleita [Teoriasta käytäntöön pilvipalvelimen avulla](https://susannalehto.fi/2022/teoriasta-kaytantoon-pilvipalvelimen-avulla-h4/) sekä [First Steps on a New Virtual Private Server – an Example on DigitalOcean and Ubuntu 16.04 LTS](https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/).

### Käyttöympäristö 


## Domain-nimen hankinta ja käyttöönotto



## Lähteet

Karvinen, T. 2024. Linux Palvelimet 2024 alkukevät. Tero Karvisen verkkosivusto. Luettavissa: [https://terokarvinen.com/2024/linux-palvelimet-2024-alkukevat/](https://terokarvinen.com/2024/linux-palvelimet-2024-alkukevat/). Luettu: 06.02.2024.

Karvinen, T. 19.09.2017. First Steps on a New Virtual Private Server – an Example on DigitalOcean and Ubuntu 16.04 LTS. Tero Karvisen verkkosivusto. Luettavissa: [https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/](https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/). Luettu: 06.02.2024.

Lehto, S. 14.02.2022. Teoriasta käytäntöön pilvipalvelimen avulla. Susanna Lehdon verkkosivusto. Luettavissa: [https://susannalehto.fi/2022/teoriasta-kaytantoon-pilvipalvelimen-avulla-h4/](https://susannalehto.fi/2022/teoriasta-kaytantoon-pilvipalvelimen-avulla-h4/). Luettu: 06.02.2024

