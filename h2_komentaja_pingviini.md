# H2 Komentaja pingviini

Toisen viikon tehtävänä on opiskella komentorivin käyttöä Linuxissa. Harjoittelu aloitetaan tiivistämällä Command line basics revisited -artikkeli ja sen jälkeen opittuja komentoja harjoitellaan käytännössä aiemmin kurssilla tekemämme virtuaalikoneen terminaaliohjelmassa. (Karvinen 2024.)

## Command line basics revisited

- Komentoriviä on käytetty tietokoneissa jo ennen Internetin keksimistä, ja sen käyttö on yhä yleistä Linuxissa.
- Komentorivi kohdistuu aina tietokoneessa olevaan johonkin hakemistoon, ja käytössä olevaa hakemistoa kutsutaan työhakemistoksi. Hakemistoja voi tarkastella (_$ pwd_) ja niiden välillä voi liikkua (_$ cd_). Uuden hakemiston luominen hoituu komennolla _$ mkdir_. 
- Komentorivillä voi myös muokata ja luoda tiedostoja (_esim. nano-teksinkäsittelyohjelmalla käskyllä $ nano_). Tiedostoja voi tarkastella komennolla _$ less_.
- Komennoilla voi myös siirtää (_$ mv_), kopioida (_$ cp_) ja poistaa (_$ rm_) tiedostoja ja hakemistoja.
- Komentoriviltä voidaan myös käyttää toista tietokonetta turvallisesti ottamalla etäyhteyden SSH:lla.
- Komentojen manuaalit löytyy laittamalla _$ man_ ennen tarkasteltavaa komentoa.
- Linuxin juurihakemiston (_merkataan /_) alta löytyvät kaikki muut hakemistot, ja sen alta voi löytää esimerkiksi käyttäjien kotihakemistot (_/home/käyttäjä/_), asetukset (_/etc/_) sekä lokitiedostot (_/var/log/_).
- Järjestelmän toimintaan vaikuttavat komennot vaativat pääkäyttäjän oikeuksia, joten nämä komennot täytyy suorittaa pääkäyttäjänä (_$ sudo ennen haluttua komentoa_).

(Karvinen 2020)

## Komentorivi-harjoitukset

## Lähteet

Karvinen, T. 2024. Linux Palvelimet 2024 alkukevät. Tero Karvisen verkkosivusto. Luettavissa: [https://terokarvinen.com/2024/linux-palvelimet-2024-alkukevat/](https://terokarvinen.com/2024/linux-palvelimet-2024-alkukevat/). Luettu: 25.01.2024.

Karvinen, T. 2020. Command Line Basics Revisited. Tero Karvisen verkkosivusto. Luettavissa: [https://terokarvinen.com/2020/command-line-basics-revisited/?fromSearch=command%20line%20basics%20revisited](https://terokarvinen.com/2020/command-line-basics-revisited/?fromSearch=command%20line%20basics%20revisited). Luettu: 25.01.2024.
