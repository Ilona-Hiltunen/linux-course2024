# H3 Hello Web Server

Kolmannen viikon ensimmäinen tehtävä oli tiivistää artikkelit [Name-Based Virtual Host Support](https://httpd.apache.org/docs/2.4/vhosts/name-based.html) sekä [Name-Based Virtualhosts on Apache - Multiple Websites to Single IP Address](https://terokarvinen.com/2018/04/10/name-based-virtual-hosts-on-apache-multiple-websites-to-single-ip-address/). Sen jälkeen pääsinkin taas harjoittelemaan luomani virtuaalikoneen kanssa, ja tällä viikolla oli tehtävänä luoda weppipalvelin Apachella sekä analysoida sen toimintaa. (Karvinen 2024.)

## Tiivistelmät

### Name-based Virtual Host Support

- Nimipohjaisessa virtual hostingissa pystytään lisäämään useampi host saman IP-osoitteen alle, toisinkuin IP-pohjaisessa hostingissa jokainen host tarvitsee erillisen IP-osoitteen.
- Kun käyttäjältä tulee pyyntö yhdistää sivustoon, määrittelee Apache ensimmäiseksi yhdistettävän osoitteen IP-osoitteesta ja käytetystä portista. Mikäli kyseisessä osoitteessa on useampi host, Apache tarkentaa oikean osoitteen ServerNamesta ja ServerAliaksesta.
- Mikäli pyynnön kanssa yhteensopivaa ServerNamea tai ServerAliasta ei löydy, käytetään ensimmäiseksi listattua hostia.
- Kun virtual hostia luodaan, tulee sen sisältää vähintään ServerName (nimi, jolla host määritellään) ja DocumentRoot (polku, mistä hakemistosta näytettävä sisältö haetaan). Se voi myös sisältää ServerAliaksen (vaihtoehtoiset nimet, jolla pääsee samalle sivustolle).
- Hostin nimiä ei kuitenkaan voi keksiä miten sattuu, sillä ne täytyy olla määritelty DNS-palvelimelle niin, että ne on liitetty käytettyyn IP-osoitteeseen.

(The Apache Software Foundation s.a.)

### Name Based Virtual Hosts on Apache - Multiple Websites to Single IP Address

- Apachen voi asentaa käskyllä _$ sudo apt-get -y install apache2_.
- Uuden nimipohjaisen hostin voi luoda tekemällä uuden tiedoston kansioon _/etc/sites-available/_. Hostin nimen tulee päättyä _.conf_. Tiedoston luominen tulee tehdä pääkäyttäjänä. Esimerkkinä komennosta tiedoston luomiseen voisi olla _$ sudoedit /etc/sites-available/ilona.example.com.conf_.
- Sisällöksi host-tiedostoon tulisi lisätä portti, ServerName, DocumentRoot sekä halutessasi ServerAlias.
- Host tulee ottaa käyttöön komennolla _$ sudo a2ensite ilona.example.com_. Apache ei löydä uutta hostia ilman uudelleenkäynnistystä, joten se tulee tehdä komennolla _$ sudo systemctl restart apache2_.
- Sivustolle tulee myös luoda vähintään index html-tiedosto, jotta hostilla on jotain, mitä näyttää sivustolla. Tämä tiedosto tulee luoda siihen hakemistoon, joka on asetettu DocumentRoottiin. Tässä esimerkissä tiedosto voisi sijaita hakemistossa _/home/ilona/publicsites/ilona.example.com_.
- Sivustoa voi testata käskyllä _$ curl localhost_ tai selaimessa kirjoittamalla _http://localhost_ osoitekenttään.

(Karvinen 10.04.2018.)



## Lähteet

The Apache Software Foundation. s.a. Name-based Virtual Host Support. Luettavissa: [https://httpd.apache.org/docs/2.4/vhosts/name-based.html](https://httpd.apache.org/docs/2.4/vhosts/name-based.html). Luettu: 30.01.2024

Karvinen, T. 2024. Linux Palvelimet 2024 alkukevät. Tero Karvisen verkkosivusto. Luettavissa: [https://terokarvinen.com/2024/linux-palvelimet-2024-alkukevat/](https://terokarvinen.com/2024/linux-palvelimet-2024-alkukevat/). Luettu: 30.01.2024.

Karvinen, T. 10.04.2018. Name Based Virtual Hosts on Apache - Multiple Websites to Single IP Address. Luettavissa: [https://terokarvinen.com/2018/04/10/name-based-virtual-hosts-on-apache-multiple-websites-to-single-ip-address/](https://terokarvinen.com/2018/04/10/name-based-virtual-hosts-on-apache-multiple-websites-to-single-ip-address/). Luettu: 30.01.2024
