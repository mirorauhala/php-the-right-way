---
title: Mac asennus
isChild: true
anchor:  mac_setup
---

## Mac asennus {#mac_setup_title}

macOS käyttöjärjestelmän mukana PHP tulee sisäänrakennettuna, mutta se on hieman
jäljessä uusimmasta vakaasta versiosta. On useita tapoja asentaa uusin versio
macOS:lle.

### Asenna PHP Homebrewilla

[Homebrew] on paketinhallintasovellus macOS:lle, jonka avulla voit helposti
asentaa PHP:n ja useita lisäosia. Homebrewin ydin repository tarjoaa "kaavoja"
PHP:n versioille 5.6, 7.0, 7.1, 7.2, 7.3, 7.4, sekä PHP 8.0. Asenna uusin versio
seuraavalla komennolla:

```
brew install php@8.0
```

Voit vaihtaa Homebrewin PHP versioiden välillä muuttamalla `PATH`
ympäristömuuttujaa. Vaihtoehtoisesti, voit käyttää
[brew-php-switcher][brew-php-switcher] PHP:n automaattiseen vaihtoon.

### Asenna PHP Macportsilla

[MacPorts] projekti on avoimen lähdekoodin yhteisöaloite, jonka tarkoituksena on
suunnitella helppokäyttöinen järjestelmä kääntämistä, asentamista ja
komentorivisovellusten, X11, tai Aqua pohjaisten avoimen-lähdekoodin
ohjelmistojen päivittämistä varten macOS käyttöjärjestelmässä.

MacPorts tukee valmiiksi käännettyjä binäärejä, jotta sinun ei tarvitse kääntää
jokaista riippuvuutta lähteistä, pelastaen elämäsi, jos sinulla ei ole mitään
paketteja asennettuna järjestelmässäsi.

Tällä hetkellä voit asentaa `php54`, `php55`, `php56`, `php70`, `php71`,
`php72`, `php73`, `php74` tai `php80` käyttämällä `port install` -komentoa,
esimerkiksi:

    sudo port install php74
    sudo port install php80

Voit myös suorittaa `select` -komennon vaihtaaksesi aktiivisen PHP:n, näin:

    sudo port select --set php php80

### Asenna PHP phpbrewillä

[phpbrew] on työkalu useiden eri PHP versioiden asentamista ja hallinnointia
varten. Tämä voi olla todella kätevää jos kaksi eri sovellusta/projektia
vaativat eri version PHP:sta, etkä käytä virtuaalikoneita.

### Asenna PHP Liip:in binäärillä

Toinen suosittu vaihtoehto on [php-osx.liip.ch], joka tarjoaa yhden koodirivin
asennuksen 5.3 versiosta 7.3 versioon saakka.
Se ei uudelleenkirjoita Applen asentamia PHP binäärejä, vaan asentaa kaiken
erilliseen hakemistoon (/usr/local/php5).

### Kasaa läheteestä

Toinen vaihtoehto, joka antaa sinun päättää minkä PHP version asennat on PHP:n
[asentaminen suoraan lähteestä][mac-compile].
Tässä tapauksessa varmista, että sinulla on asennettuna joko
[Xcode][xcode-gcc-substitution] tai Applen vastaava
["Command Line Tools for XCode"] ladattavissa Applen Mac Developer Centeristä.

### All-in-One asentajat

Ylhäällä listatut vaihtoehdot pääasiassa asentavat PHP:n itsessään eivätkä
tarjoa ohjelmia kuten [Apache][apache], [Nginx][nginx] tai SQL palvelinta.
"All-in-one" ratkaisut kuten [MAMP][mamp-downloads] tai [XAMPP][xampp] asentavat
nämä loput ohjelmistojen palaset puolestasi ja kasaavat ne yhteen, mutta
asennuksen helppous tulee joustavuuden kompromissina.

[Homebrew]: https://brew.sh/
[Homebrew PHP]: https://github.com/Homebrew/homebrew-php#installation
[MacPorts]: https://www.macports.org/install.php
[phpbrew]: https://github.com/phpbrew/phpbrew
[php-osx.liip.ch]: https://php-osx.liip.ch/
[mac-compile]: https://secure.php.net/install.macosx.compile
[xcode-gcc-substitution]: https://github.com/kennethreitz/osx-gcc-installer
["Command Line Tools for XCode"]: https://developer.apple.com/downloads
[apache]: https://httpd.apache.org/
[nginx]: https://www.nginx.com/
[mamp-downloads]: https://www.mamp.info/en/downloads/
[xampp]: https://www.apachefriends.org/index.html
[brew-php-switcher]: https://github.com/philcook/brew-php-switcher
