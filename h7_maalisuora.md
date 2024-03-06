# H7 Maalisuora

Seitsemännessä tehtävässä tuli ensimmäisenä kääntää "Hei maailma" haluamalleen kielelle, ja sen jälkeen asentaa Linuxiin uusi komento niin, että kaikki käyttäjät voivat ajaa sitä. Tämän jälkeen tuli toistaa jokin edellisten kurssien laboratorioharjoituksista. Viimeisenä tuli luoda uusi tyhjä virtuaalikone seuraavan viikon lopputehtävää varten. (Karvinen 2024.)

## Käyttöympäristö 

Tietokone: Virtualboxilla luotu virtuaalikone

Keskusmuisti: 4 GB

Massamuisti: 60 GB

Käyttöjärjestelmä: Debian 12 Bookworm (64-bit)

## Kääntäminen ja uuden komennon tekeminen

### Hello World kääntäminen Pythonille

Käytin tässä tehtävässä apuna Tero Karvisen [Hello World Python3, Bash, C, C++, Go, Lua, Ruby, Java – Programming Languages on Ubuntu 18.04](https://terokarvinen.com/2018/hello-python3-bash-c-c-go-lua-ruby-java-programming-languages-on-ubuntu-18-04/?fromSearch=hello%20world) -artikkelia. Aloitin tehtävän teon 18:20. Siirryin haluamaani kansioon komennolla `$ cd Code/python/`. Loin uuden Python-tiedoston komennolla `$ micro hello.py`. Loin tiedoston sisällöksi kuvan `$ cat hello.py`-komennon alla näkyvän koodin. Testasin sen suorittamista komennolla `$ python3 hello.py`, ja se palautti kirjoittamani tekstin. Tehtävä valmistui 18:24.

![Ohjelman sisältö ja suoritus](Kuvat/hello1.png)

### Komennon tekeminen kaikille käyttäjille

Seuraavaksi vuorossa oli tehdä komento, jonka kaikki käyttäjät voi suorittaa. Käytin tehtävässä apuna Tero Karvisen [Shell Scripting](https://terokarvinen.com/2007/shell-scripting-4/#hello_world_-_lspwd) -artikkelia. Päätin tehdä komennon, joka luo automaattisesti index.html-tiedoston oikealla syntaksilla. Aloitin tehtävän teon 18:30. Siirryin haluamaani kansioon komennolla `$ cd Code/scripts/`. Tämän jälkeen loin uuden tiedoston komennolla `$ micro makeindex`. Kirjoitin tiedoston sisällön kuvan mukaisesti. Annoin kaikille käyttäjille suoritus- ja lukuoikeudet komennolla `$ chmod ugo+rx makeindex`. 

![Tiedoston luominen ja oikeuksien antaminen](Kuvat/hello2.png)

Tämän jälkeen kopioin tiedoston /usr/local/bin/-hakemistoon pääkäyttäjänä komennolla `$ sudo cp makeindex /usr/local/bin`. Siirryin kotihakemistooni komennolla `$ cd`, jotta voin testata ohjelman suoritusta niin, ettei se vahingossa lue Code/scripts/-hakemistooni luomaa tiedostoa. Nyt terminaaliin piti kirjoittaa komennoksi vain `$ makeindex`, ja kuten kuvasta näkyy hakemistoon ilmestyi validi index.html-tiedosto. Tehtävä oli valmis 19:00.

![Valmis komento](Kuvat/hello3.png)

## Laboratorioharjoitus

Päätin suorittaa Tero Karvisen opettaman [Linux palvelimet 2023](https://terokarvinen.com/2023/linux-palvelimet-2023-arvioitava-laboratorioharjoitus/)-kurssin loppuharjoituksen. Jätin loppuharjoituksesta a) ja b) -kohdat tekemättä, jotka liittyivät raportin kirjoittamiseen, sillä kirjoitan tehtävistä raportin tähän tiedostoon. Loin ensimmäiseksi uuden virtuaalikoneen, jotta voin toteuttaa tehtävän samoissa olosuhteissa, kuin tulevankin laboratorioharjoituksen. Virtuaalikone on käyttöympäristöltään täysin samanlainen, kuin raportin alussa kuvaamani virtuaalikone. 

### Tiedoston suojaaminen

Ensimmäinen tehtvä oli suojata tiedosto niin, että ainoastaan käyttäjäni voi katsoa sitä (Karvinen 2023). Aloitin tehtävän teon 16:19. Loin testitiedoston komennolla `$ nano testi.txt`. Tämän jälkeen tarkastelin tiedoston oikeuksia komennolla `$ ls -l testi.txt`, ja huomasin että ryhmä ja muut saavat lukea tiedostoa. Poistin ryhmältä ja muilta käyttäjiltä lukuoikeuden komennolla `$ chmod go-r testi.txt`. Nyt tarkastelin uudestaan tiedoston oikeuksia, ja ainoastaan käyttäjälläni oli oikeus lukea tiedosto. Tehtävä oli valmis 16:22.

![Tiedoston suojaus](Kuvat/suojaus.png)

### Komennon tekeminen

Seuraavaksi tuli tehdä "hey"-niminen komento, joka tulostaa jotain ajankohtaista tietoa (Karvinen 2023). Käytin tehtävässä apuna Tero Karvisen [Shell Scripting](https://terokarvinen.com/2007/shell-scripting-4/#hello_world_-_lspwd) -artikkelia. Aloitin tehtävän tekemisen 16:50. Tein uuden kansion komennolla `$ mkdir scripts`, ja siirryin siihen komennolla `$ cd scripts/`. Tein uuden tiedoston komennolla `$ nano hey`, ja kirjoitin sen sisällön kuvan mukaisesti.

![Hey-tiedoston sisältö](Kuvat/komento1.png)

Annoin kaikille oikeudet lukea ja suorittaa tiedostoa komennolla `$ chmod ugo+rx hey` Kopioin vielä tiedoston paikallisesta hakemistostani /usr/local/bin-hakemistoon komennolla `$ sudo cp hey /usr/local/bin`. Siirryin kotihakemistooni ja kokeilin kirjoittaa komennoksi `$ hey`. Terminaali palautti vastaukseksi päivämäärän ja virtuaalikoneen ip-osoitteen. Tehtävä oli valmis 17:00.

![Valmis komento](Kuvat/komento2.png)

### Micron asennus

Seuraavaksi tuli asentaa Micro-editori ja sille joku plugin (Karvinen 2023). Aloitin tehtävän 17:05. Ensimmäisenä päivitin pakettilistan komennolla `$ sudo apt-get update` ja sen jälkeen asensin Micron komennolla `$ sudo apt-get install micro`.

![Micron asennus](Kuvat/micro1.png)

Tämän jälkeen tutkin plugineja, ja päätin ottaa käyttöön Tero Karvisen [Micro-jump](https://github.com/terokarvinen/micro-jump)-pluginin, jossa voi hyppiä editorissa eri komentoihin. Käytin ohjeena ohjelman Github-sivua. Asensin pluginiin tarvittavat ohjelmat komennolla `$ sudo apt-get -y install fzf exuberant-ctags`. Tämän jälkeen asensin plugin komennolla `$ micro --plugin install jump`.

![Tarvittavat ohjelmat](Kuvat/micro2.png) ![Plugin-asennus](Kuvat/micro3.png)

Tein uuden testitiedoston komennolla `$ micro testi.py`. Laitoin muutaman funktion tiedostoon, ja tallensin tiedoston painamalla CTRL+S. Tämän jälkeen painoin F4, ja tästä avautui näkymä, jossa voin valita mihin funktioon haluan hypätä. Tehtävä oli valmis 17:25.

![Hyppiminen funktioihin](Kuvat/micro4.png)

### Apache

Tämän jälkeen tuli asentaa Apache-weppipalvelin, tehdä uusi Erkki-niminen käyttäjä ja tehdä Erkille kotisivu (Karvinen 2024). Käytin tehtävässä ohjeena Tero Karvisen [Name Based Virtual Hosts on Apache – Multiple Websites to Single IP Address](https://terokarvinen.com/2018/name-based-virtual-hosts-on-apache-multiple-websites-to-single-ip-address/?fromSearch=apache) -artikkelia. Aloitin tehtävän kello 18:50. Ensimmäisenä asensin Apachen komennolla `$ sudo apt-get -y install apache2`. Tämän jälkeen loin Erkille käyttäjän komennolla `$ sudo adduser erkki`.

![Apachen lataus](Kuvat/kotisivu1.png) ![Käyttäjän tekeminen](Kuvat/kotisivu2.png)

Seuraavaksi loin uuden tiedoston komennolla `$ sudoedit /etc/apache2/sites-available/homepage.example.com.conf`. Asetin sen sisällön kuvan mukaisesti.

![Erkki.example.com.conf](Kuvat/kotisivu3.png)

Otin sivun käyttöön komennolla `$ sudo a2ensite homepage.example.com`, ja otin oletussivun pois käytöstä `$ sudo a2dissite 000-default.conf`. Käynnistin Apachen uudelleen komennolla `$ sudo systemctl restart apache2`.

![Sivun käyttöönotto](Kuvat/kotisivu5.png)

Vaihdoin käyttäjälle erkki komennolla `$ su erkki`. Loin käyttäjälle public_html-kansion komennolla `$ mkdir public_html`. Tein sinne index.html-tiedoston komennolla `$ micro public_html/index.html`, ja kirjoitin sisällöksi lyhyen testin. Menin sivulle http://localhost/~erkki, ja sivustolle ei ollut lupaa mennä.

![Sivun näkymä](Kuvat/kotisivu6.png)

Selvittelin vikaa internetistä, ja löysin Apachen [Per-user web directories](https://httpd.apache.org/docs/2.4/howto/public_html.html)-manuaalista, että Userdir pitää ottaa käyttöön. Kirjauduin takaisin alkuperäiselle käyttäjälleni. Otin sen käyttöön komennolla `$ sudo a2enmod userdir`, ja käynnistin Apachen uudelleen `$ sudo systemctl restart apache2`. 

![Userdir](Kuvat/kotisivu7.png)

Huomasin vikaa selvitellessäni myös, ettei erkki-käyttäjän kotihakemistoon ole pääsyä muilla kuin erkillä. Korjasin tämän komennolla `$ sudo chmod go+rx erkki/`. 

![Oikeuksien muokkaus](Kuvat/kotisivu8.png)

Tämän jälkeen kokeilin mennä uudestaan osoitteeseen http://localhost/~erkki/, ja tällä kertaa se palauttikin erkki-käyttäjällä tekemäni kotisivun. Tehtävä valmistui 20:00.

![Erkin kotisivu](Kuvat/kotisivu9.png)

### SSH

Seuraavaksi tuli asentaa SSH-palvelin ja tehdä uusi testikäyttäjä. SSH-kirjautuminen tuli automatisoida avaimella ja lopuksi laittaa SSH-palvelin kuuntelemaan porttia 1337/tcp. (Tero Karvinen 2023.) Käytin tässä tehtävässä apuna Debianin [SSH-manuaalia](https://wiki.debian.org/SSH). Aloitin tehtävän tekemisen 20:20. Aloitin asentamalla SSH-palvelimen komennolla `$ sudo apt-get install openssh-server`. Tein myös testikäyttäjän komennolla `$ adduser testi`. 

![SSH-asennus](Kuvat/kirjautuminen1.png) ![Käyttäjän teko](Kuvat/kirjautuminen2.png)

Kokeilin kirjautumista testi-käyttäjälle komennolla `$ ssh testi@localhost`, ja salasanan syöttämisen jälkeen pääsin sisään. 

![SSH-yhteys testikäyttäjälle](Kuvat/kirjautuminen3.png)

Poistuin SSH-yhteydestä takaisin alkuperäiselle käyttäjälleni komennolla `$ exit`. Loin SSH-avaimen komennolla `$ ssh-keygen`. Asetin avaimen tallentumaan oletuskansioon ja en asettanut salasanaa tässä testissä. Tämän jälkeen kopioin avaimen testikäyttäjälle komennolla `$ ssh-copy-id testi@localhost`. 

![Avaimen generointi](Kuvat/kirjautuminen4.png) ![Avaimen kopiointi](Kuvat/kirjautuminen5.png)

Kokeilin nyt muodostaa SSH-yhteyden uudestaan komennolla `$ ssh testi@localhost`, ja pääsin kirjautumaan suoraan sisään.

![Onnistunut kirjautuminen](Kuvat/kirjautuminen6.png)

Seuraavaksi aloin vaihtamaan portin, jota SSH kuuntelee. Siirryin SSH-asetuskansioon komennolla `$ cd /etc/ssh/`. Muokkasin sshd_config-tiedostoa komennolla `$ sudoedit sshd_config`. Ja lisäsin siihen portin kuvan mukaisesti.

![Portti](Kuvat/kirjautuminen8.png)

Tämän jälkeen käynnistin SSH-palvelimen uudestaan komennolla `$ sudo systemctl restart ssh`. Tämän jälkeen katsoin mitkä ohjelmat käyttää porttia 1337 komennolla `sudo lsof -i -P -n | grep LISTEN | grep 1337`, ja terminaali palautti, että se on SSH:n käytössä. Tehtävä oli valmis 21:00. 

![SSH portissa 1337](Kuvat/kirjautuminen7.png)

### Django

Tässä tehtävässä tuli asentaa Django, ja tehdä sinne tietokanta, jossa on lahjoitettuja esineitä. Tietokantaan piti pystyä kirjautumaan salasanalla, tehdä Erkille oma käyttäjä ja tehdä taulu Donations- joka sisältää lahjoitukset. (Tero Karvinen 2023.)

### Tuotantotyyppinen Django

Viimeisenä tuli tehdä tuotantotyyppinen asennus Djangosta, ja asettaa siihen edellinen lahjatietokanta (Karvinen 2023).

# Lähteet

Apache Software Foundation. s.a. Per-user web directories. Apache Software Foundation. Luettavissa: [https://httpd.apache.org/docs/2.4/howto/public_html.html](https://httpd.apache.org/docs/2.4/howto/public_html.html). Luettu: 06.03.2024.

Debian Wiki. 09.11.2023. SSH. Debian Wiki. Luettavissa: [https://wiki.debian.org/SSH](https://wiki.debian.org/SSH). Luettu: 06.03.2024.

Karvinen, T. 2023. Final Lab for Linux Palvelimet 2023. Tero Karvisen verkkosivusto. Luettavissa: [https://terokarvinen.com/2023/linux-palvelimet-2023-arvioitava-laboratorioharjoitus/](https://terokarvinen.com/2023/linux-palvelimet-2023-arvioitava-laboratorioharjoitus/). Luettu: 05.03.2024.

Karvinen, T. 27.09.2018. Hello World Python3, Bash, C, C++, Go, Lua, Ruby, Java – Programming Languages on Ubuntu 18.04. Tero Karvisen verkkosivusto. Luettavissa: [https://terokarvinen.com/2018/hello-python3-bash-c-c-go-lua-ruby-java-programming-languages-on-ubuntu-18-04/?fromSearch=hello%20world](https://terokarvinen.com/2018/hello-python3-bash-c-c-go-lua-ruby-java-programming-languages-on-ubuntu-18-04/?fromSearch=hello%20world). Luettu: 05.03.2024.

Karvinen, T. 2024. Linux Palvelimet 2024 alkukevät. Tehtävänanto H7 Maalisuora. Tero Karvisen verkkosivusto. Luettavissa: [https://terokarvinen.com/2024/linux-palvelimet-2024-alkukevat/](https://terokarvinen.com/2024/linux-palvelimet-2024-alkukevat/). Luettu: 05.03.2024.

Karvinen, T. s.a. micro-jump - Jump to function. Github. Luettavissa: [https://github.com/terokarvinen/micro-jump](https://github.com/terokarvinen/micro-jump). Luettu: 06.03.2024.

Karvinen, T. 10.04.2018. Name Based Virtual Hosts on Apache – Multiple Websites to Single IP Address. Tero Karvisen verkkosivusto. Luettavissa: [https://terokarvinen.com/2018/name-based-virtual-hosts-on-apache-multiple-websites-to-single-ip-address/?fromSearch=apache](https://terokarvinen.com/2018/name-based-virtual-hosts-on-apache-multiple-websites-to-single-ip-address/?fromSearch=apache). Luettu: 06.03.2024.

Karvinen, T. 04.12.2007. Shell Scripting. Tero Karvisen verkkosivusto. Luettavissa: [https://terokarvinen.com/2007/shell-scripting-4/#see_also](https://terokarvinen.com/2007/shell-scripting-4/#see_also). Luettu: 05.03.2024.
