# H4 Maailma kuulee

Neljännen viikon tehtävänä oli tiivistää artikkelit [Teoriasta käytäntöön pilvipalvelimen avulla](https://susannalehto.fi/2022/teoriasta-kaytantoon-pilvipalvelimen-avulla-h4/) sekä [First Steps on a New Virtual Private Server – an Example on DigitalOcean and Ubuntu 16.04 LTS](https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/). Harjoituksina tuli vuokrata oma virtuaalipalvelin, tehdä sille alkutoimenpiteet ja vaihtaa Apachen testisivu omaan tuotokseen. Viimeisenä tuli vuokrata oma domain-nimi ja asettaa se osoittamaan juuri hankkimaamme virtuaalipalvelimeen. (Karvinen 2024.)

## Tiivistelmät

### Teoriasta käytäntöön pilvipalvelimen avulla

- Pilvipalvelimia voi vuokrata eri palveluntarjoajilta, esimerkiksi DigitalOcean tarjoaa palvelinten vuokrausta. Vuokrattava pilvipalvelimen tehokkuus tulee valita omien tarpeiden mukaan. On kuitenkin suositeltavaa aloittaa halvimmasta sopivasta vaihtoehdosta, sillä palvelimen tehoja saa helposti lisättyä jälkikäteenkin.
- Domain-nimiä voi myös vuokrata useilta eri palveluntarjoajilta, esimerkiksi Namecheap on tällainen. Vuokrattu nimi tulee osoittaa palvelimen IP-osoitteeseen, jotta domain-nimelle tuleva liikenne ohjautuu halutulle palvelimelle.
- Kun palvelimen laittaa käyttökuntoon, tulisi tehdä seuraavat toimenpiteet;
  - Suojata palvelin palomuurilla, sekä avata ainoastaan tarvittavat portit liikenteelle.
  - Tehdä oma pääkäyttäjä hyvällä salasanalla, ja sulkea root.
  - Päivittää ja asentaa palvelimen ohjelmat.



## Lähteet

Karvinen, T. 2024. Linux Palvelimet 2024 alkukevät. Tero Karvisen verkkosivusto. Luettavissa: [https://terokarvinen.com/2024/linux-palvelimet-2024-alkukevat/](https://terokarvinen.com/2024/linux-palvelimet-2024-alkukevat/). Luettu: 06.02.2024.

Karvinen, T. 19.09.2017. First Steps on a New Virtual Private Server – an Example on DigitalOcean and Ubuntu 16.04 LTS. Tero Karvisen verkkosivusto. Luettavissa: [https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/](https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/). Luettu: 06.02.2024.

Lehto, S. 14.02.2022. Teoriasta käytäntöön pilvipalvelimen avulla. Susanna Lehdon verkkosivusto. Luettavissa: [https://susannalehto.fi/2022/teoriasta-kaytantoon-pilvipalvelimen-avulla-h4/](https://susannalehto.fi/2022/teoriasta-kaytantoon-pilvipalvelimen-avulla-h4/). Luettu: 06.02.2024

