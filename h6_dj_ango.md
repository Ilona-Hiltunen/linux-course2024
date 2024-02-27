# H6 DJ Ango

Kurssin kuudennessa osiossa ensimmäiseksi tuli tehdä lyhyet tiivistelmät Tero Karvisen artikkeleista [Django 4 Instant Customer Database Tutorial](https://terokarvinen.com/2022/django-instant-crm-tutorial/) ja [Deploy Django 4 - Production Install](https://terokarvinen.com/2022/deploy-django/). Tämän jälkeen virtuaalikoneelle tuli tehdä yksinkertainen ohjelma Djangolla ja Djangon tuotantotyyppinen asennus. (Karvinen 2024.)

## Tiivistelmät

### Django 4 Instant Customer Database Tutorial

- Djangon viimeisimmän version asentamisessa tulee käyttää `pip`-komentoa ja se tulisi tehdä `virtualenv`-tilassa, jotta kaikki paketit tallentuvat samaan kansioon. `Pip`-komennon käytössä tulee olla varovainen oikeinkirjoituksessa, jotta ei vahingossa asenna väärää ohjelmaa.
- Django-projektin voi aloittaa komennolla `$ django-admin startproject projektinnimi` ja testiserverin voi käynnistää komennolla `$ ./manage.py runserver`.
- Tietokannat voi päivittää komennolla `$ ./manage.py makemigrations` ja sen jälkeen `$ ./manage.py migrate`. 
- Käyttäjän voi tehdä komennolla `$ ./manage.py createsuperuser`.
- Uuden ohjelman projektiin voi tehdä komennolla `$ ./manage.py startapp ohjelmannimi`. Tero Karvisen esimerkissä on tehty CRM-ohjelma. Ohjelma tulee lisätä `settings.py`-tiedostoon `INSTALLED_APPS`-kohtaan.
- Uusi luokka tehdään `models.py`-tiedostoon, josta Django osaa tehdä automaattisesti tietokannan. Tero Karvisen esimerkissä tiedostoon on tehty asiakas-luokka, jolla on attribuuttina asiakkaan nimi. Tämän jälkeen tietokannat tulee päivittää.
- Viimeisenä vielä luokka tulee rekisteröidä `admins.py`-tiedostoon. Sen voi tehdä muokkaamalla `admins.py`-tiedostoa lisäämällä siihen `admin.site.register(models.LuokanNimi)`.
- Nyt luodun tietokannan pitäisi näkyä osoitteessa  http://127.0.0.1:8000/admin/.

(Karvinen 2021. b.)

### Deploy Django 4 - Production Install

- Tuotantokäyttöiseen Djangoon tulee asentaa Apache-weppipalvelin. Sen voi asentaa komennolla `$ sudo apt-get -y install apache2.` Apachen toimintaa voi testata tekemällä `static`-kansion ja tekemällä sille `index.html`-tiedoston. Esimerkissä hakemistopolku tiedostolle on `publicwsgi/teroco/static/`. Virtualhost tulee laittaa osoittamaan tähän osoitteeseen, jotta sisältö näkyy.
- Djangon nimi olisi hyvä tehdä `requirements.txt`-tiedostoon, jotta se tulee varmasti kirjoitettua oikein ja oikea ohjelma tulee ladattua. Tämän jälkeen Djangon voi asentaa `virtualenv`-tilassa komennolla `$ pip install -r requirements.txt`. Uuden projektin voi tehdä komennolla `$ django-admin startproject projektinnimi`.
- Seuraavaksi Apache tulisi konfiguroida Python-ohjelmille sopivaksi. Tämän voi tehdä muokkaamalla Apachen conf-tiedostoa, joka Tero Karvisen esimerkissä tehdään komennolla `$ sudoedit /etc/apache2/sites-available/teroco.conf`. Jotta Apache ymmärtää tiedostoon tehtyjä WSGI-komentoja, tulee WSGI-moduuli asentaa komennolla `$ sudo apt-get -y install libapache2-mod-wsgi-py3`.
- Jotta sivusto olisi tietoturvallinen, tulee `DEBUG` ottaa pois käytöstä. Sen voi tehdä muokkaamalla projektikansion alla olevaa `settings.py`-tiedostoa. Samaan tiedostoon kirjoitetaan hostin nimi `ALLOWED_HOSTS`-kohtaan. Muutokset voi päivittää Apachelle komennolla `$ touch projektikansio/wsgi.py`.
- Tämän jälkeen sivuston tulisi toimia määritellystä host-osoitteesta.

(Karvinen 2021. a.)

## Käyttöympäristö

Tietokone: Virtualboxilla luotu virtuaalikone

Keskusmuisti: 4 GB

Massamuisti: 60 GB

Käyttöjärjestelmä: Debian 12 Bookworm (64-bit)

## Yksinkertainen esimerkkiohjelma Djangolla

Käytin tehtävässä apuna Tero Karvisen [Django 4 Instant Customer Database Tutorial](https://terokarvinen.com/2022/django-instant-crm-tutorial/) -artikkelia, ja päätin tehdä samanlaisen CRM-ohjelman. Aloitin tehtävien teon 22:00. Ensimmäiseksi tein django-nimisen kansion, johon aion laittaa projektin ja muut tiedostot komennolla `$ mkdir django`. Tämän jälkeen siirryin kyseiseen kansioon ja tein sinne env-kansion komennolla `$ $ virtualenv --system-site-packages -p python3 env/`. Tämän jälkeen laitoin virtualenv-tilan päälle komennolla `$ source env/bin/activate`.

![Alkukomennot](Kuvat/crm1.png)

Tämän jälkeen tein requirements.txt-tiedoston komennolla `$ micro requirements.txt`, jonka sisälloksi kirjoitin ladattavan Djangon. Päätin käyttää versiota 4, sillä sitä oli käytetty ohjeistuksessa. Tämän jälkeen aloitin Djangon latauksen komennolla `$ pip install -r requirements.txt`.

![Djangon lataus](Kuvat/crm2.png)

Nyt olin valmis luomaan projektin, ja tein sen komennolla `$ django-admin startproject kissala`. Testasin vielä sivuston toiminnan siirtymällä kissala-projektikansioon ja käynnistämällä projektin komennolla `$ ./manage.py runserver`. Menin terminaaliin palauttamaan http://127.0.0.1:8000/ -osoitteeseen ja sain näkyviin Djangon testisivun.

![Projektin luonti](Kuvat/crm3.png)

![Testaus](Kuvat/crm4.png)

Tämän jälkeen päivitin tietokannan komennoilla `$ ./manage.py makemigrations` ja sen jälkeen `./manage.py migrate`. 

![Tietokantojen päivitys](Kuvat/crm5.png)

Tämän jälkeen tein käyttäjän sivustolle komennolla `$ ./manage.py createsuperuser`, jonka nimeksi asetin ilona ja tein tietoturvallisen salasanan salasanageneraattorillani. Tämän jälkeen testasin kirjautua tekemilläni tunnuksilla osoitteeseen  http://127.0.0.1:8000/admin/, ja kirjautuminen onnistui.

![Käyttäjän teko ja kirjautuminen](Kuvat/crm6.png)

Tämän jälkeen aloin luomaan asiakas-tietokantaa. Loin kansion ohjelmalle komennolla `$ ./manage.py startapp crm`. Muokkasin `settings.py`-tiedostoa komennolla `$ micro kissala/settings.py`. Lisäsin sinne INSTALLED_APPS kohtaan crm-kansion kuvan mukaisesti.

![Ohjelman luominen](Kuvat/crm9.png)

![Settings-tiedoston muokkaus](Kuvat/crm7.png)

Seuraavaksi loin asiakas-luokan, jolla oli attribuuttina asiakkaan nimi. Tein luokan models.py-tiedostoon komennolla `$ micro crm/models.py`. Kirjoitin luokan sisällön kuvan mukaisesti, jossa luokan nimeksi annetaan Customer, attribuutiksi nimi ja alempana määritellään, että asiakas näkyy nimellänsä tietokannassa.

![Customer-luokan tekeminen](Kuvat/crm8.png)

Tämän jälkeen päivitin taas tietokannan komennoilla `$ ./manage.py makemigrations` ja sen jälkeen `./manage.py migrate`. Tämän jälkeen vielä rekisteröin luokan admin.py-tiedostoon komennolla `$ micro crm/admin.py`. Muokkasin tiedostoa kuvan mukaisella tavalla.

![Admin-tiedoston muokkaus](Kuvat/crm10.png)

Viimeiseksi käynnistin testiserverin komennolla `$ ./manage.py runserver`. Menin osoitteeseen http://127.0.0.1:8000/admin/ ja kokeilin lisätä ja poistaa asiakkaita. Tämä onnistui ja ohjelma oli valmis klo 22:50.

![Valmis CRM-ohjelma](Kuvat/crm11.png)



## Lähteet

Karvinen, T. 2021. a. Deploy Django 4 - Production Install. Tero Karvisen verkkosivusto. Luettavissa: [https://terokarvinen.com/2022/deploy-django/](https://terokarvinen.com/2022/deploy-django/). Luettu: 27.02.2024.

Karvinen, T. 2021. b. Django 4 Instant Customer Database Tutorial. Tero Karvisen verkkosivusto. Luettavissa: [https://terokarvinen.com/2022/django-instant-crm-tutorial/](https://terokarvinen.com/2022/django-instant-crm-tutorial/). Luettu: 27.02.2024.

Karvinen, T. 2024. Linux Palvelimet 2024 alkukevät. Tehtävänanto H6 AJ Ango. Tero Karvisen verkkosivusto. Luettavissa: [https://terokarvinen.com/2024/linux-palvelimet-2024-alkukevat/](https://terokarvinen.com/2024/linux-palvelimet-2024-alkukevat/). Luettu: 27.02.2024.
