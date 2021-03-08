---
isChild: true
anchor:  password_hashing
title: Salasanojen hajautus
---

## Salasanojen tiivistäminen tai hajautus {#password_hashing_title}

Lopulta jokainen rakentaa PHP sovelluksen joka perustuu käyttäjän kirjautumiseen.
Käyttäjänimet ja salasanat ovat tallennetuna tietokannassa, joita käytetään
käyttäjän autentikointiin kirjautumisen yhteydessä.

On tärkeää että [_hajautat_][3] salasanat kunnolla ennen tallentamista. Hajauttaminen
ja salaaminen ovat [kaksi hyvin erilaista asiaa][7], jotka usein sekoitetaan
keskenään.

Hajauttaminen on peruuttamaton, yksisuuntainen funktio. Tämä tuottaa
samanpituisen merkkijonon, jota ei voida käytännössä palauttaa takaisin.
Tämä tarkoittaa, että voit verrata hajautusta toiseen selvittääksesi, ovatko ne
molemmat peräisin samasta alkuperäisestä merkkijonosta, mutta et voi päätellä
alkuperäistä merkkijonoa. Jos salasanat eivät ole hajautettu ja tietokantaasi
pääsee luvaton kolmas osapuoli, kaikki käyttäjätilit ovat nyt vaarantuneet.

Toisin kuin hajauttaminen, salaus on mahdollista purkaa (edellyttäen, että
sinulla on avain). Salaaminen on hyödyllistä muissa tapauksisa, mutta on heikko
strategia turvalliseen salasanan tallentamiseen.

Salasanojen tulisi olla myös erikseen [_suolattuja_][5] lisäämällä satunnainen
merkkijono jokaiseen salasanaan ennen hajautusta. Tämä estää
sanakirjahyökkäykset ja "sateenkaaritaulujen" (käänteinen luettelo tavallisten
salasanojen kryptografisista hajautuksista) käytön.

Hajautus ja suolaus ovat elintärkeitä, koska usein käyttäjät käyttävät samaa
salasanaa useissa palveluissa ja salasanan laatu voi olla huono.

Lisäksi, sinun tulisi käyttää [erikoistunutta _salasanan hajautusalgoritmia_][6] 
nopean yleiskäyttöisen kryptografisen tiivistefunktion sijaan (esim. SHA256).
Lyhyt lista hyväksytyistä salasanan hajautusalgoritmeista (kesäkuusta 2018
lähtien) ovat:

* Argon2 (saatavilla PHP versiossa 7.2 ja uudemmissa)
* Scrypt
* **Bcrypt** (PHP tarjoaa tämän sinulle; lue alta)
* PBKDF2 jossa HMAC-SHA256 tai HMAC-SHA512

Onneksi PHP tekee tämän nykyään helpoksi.

**Salasanojen hajauttaminen `password_hash` funktiolla**

PHP:n 5.5 versiossa julkaistiin `password_hash()`. Tällä hetkellä se käyttää
BCryptia, vahvinta algoritmia tällä hetkellä tuettuna PHP:ssa. Tulevaisuudessa
se päivitetään tukemaan tarvittaessa enemmän algoritmeja. `password_compat`
kirjasto luotiin tarjoamaan yhteensopivuus PHP:n versioille >= 5.3.7.

Alla me hajautamme taikka toisin sanottuna tiivistämme merkkijonoa. Sitten
vertaamme hajautusta toista merkkijonoa vastaan. Koska molemmat alkuperäiset
merkkijonot ovat erilaisia ('salainen-salasana' vs. 'huono-salasana'), tämä
kirjautuminen epäonnistuu.


{% highlight php %}
<?php
require 'password.php';

$passwordHash = password_hash('salainen-salasana', PASSWORD_DEFAULT);

if (password_verify('huono-salasana', $passwordHash)) {
    // Oikea salasana
} else {
    // Väärä salasana
}
{% endhighlight %}

`password_hash()` huolehtii salasanan suolauksesta puolestasi. Suola on
tallennettu yhdessä algoritmin "tehon" kanssa hajautuksessa.
`password_verify()` poimii tämän salasanan tarkistamiseksi, jotta sinun ei
tarvitse tehdä erillistä saraketta tietokantaan suolaa varten.

* [Lue lisää `password_hash()`] [1]
* [`password_compat` PHP:n versioille >= 5.3.7 && < 5.5] [2]
* [Lue lisää kryptografisesta hajautuksesta] [3]
* [Lue lisää suolaamisesta] [5]
* [PHP `password_hash()` RFC] [4]


[1]: https://secure.php.net/function.password-hash
[2]: https://github.com/ircmaxell/password_compat
[3]: https://wikipedia.org/wiki/Cryptographic_hash_function
[4]: https://wiki.php.net/rfc/password_hash
[5]: https://wikipedia.org/wiki/Salt_(cryptography)
[6]: https://paragonie.com/blog/2016/02/how-safely-store-password-in-2016
[7]: https://paragonie.com/blog/2015/08/you-wouldnt-base64-a-password-cryptography-decoded

