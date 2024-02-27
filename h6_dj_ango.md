# H& DJ Ango

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

### Deploy Django 4 - Production Install

## Lähteet

Karvinen, T. 2021. a. Deploy Django 4 - Production Install. Tero Karvisen verkkosivusto. Luettavissa: [https://terokarvinen.com/2022/deploy-django/](https://terokarvinen.com/2022/deploy-django/). Luettu: 27.02.2024.

Karvinen, T. 2021. b. Django 4 Instant Customer Database Tutorial. Tero Karvisen verkkosivusto. Luettavissa: [https://terokarvinen.com/2022/django-instant-crm-tutorial/](https://terokarvinen.com/2022/django-instant-crm-tutorial/). Luettu: 27.02.2024.

Karvinen, T. 2024. Linux Palvelimet 2024 alkukevät. Tehtävänanto H6 AJ Ango. Tero Karvisen verkkosivusto. Luettavissa: [https://terokarvinen.com/2024/linux-palvelimet-2024-alkukevat/](https://terokarvinen.com/2024/linux-palvelimet-2024-alkukevat/). Luettu: 27.02.2024.
