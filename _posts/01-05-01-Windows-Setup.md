---
title: Windows asennus
isChild: true
anchor:  windows_setup
---

## Windows asennus {#windows_setup_title}

Voit ladata binäärit osoitteesta [windows.php.net/download][php-downloads].
PHP:n purun jälkeen on suositeltua asettaa PHP kansio (missä php.exe sijaitsee)
[PATH][windows-path] ympäristömuuttujaan, jotta voit suorittaa PHP:n mistä vain.

Opiskeluun ja paikalliseen kehitykseen voit käyttää sisäänrakennettua
verkkopalvelinta PHP 5.4+ versiosta, joten ei tarvitse murehtia verkkopalvelimen
konfiguroinnista. Jos haluat "all-in-one" tyylisen ratkaisun, joka sisältää 
täysiverisen verkkopalvelimen ja MySQL -tietokantapalvelimen, niin työkalut kuten
[Web Platform Installer][wpi], [XAMPP][xampp],[EasyPHP][easyphp],
[OpenServer][openserver] ja [WAMP][wamp] auttavat Windows kehitysympäristön
pystyttämisessä. Kuitenkin, nämä työkalut ovat hieman erilaisia kuin
tuotantoympäristö, joten ole varovainen ympäristöjen eroista, mikäli
työskentelet Windowsilla ja tuotat Linuxilla.

Jos sinun pitää käyttää Windowsia tuotantoympäristönä, niin silloin IIS7 antaa
vakaimman ja parhaimman tehon. Voit käyttää [phpmanager][phpmanager]
(GUI lisäosa IIS7:lle) konfiguroinnin ja hallinnoinnin yksinkertaistamiseksi.
IIS7 tulee sisäänrakennettuna FastCGI:llä. Täytyy ainoastaan konfiguroida PHP
käsittelijäksi. Tukea ja muita lisäresursseja löytyy PHP:lle IIS alustalla 
osoitteesta [php.iis.net][php-iis]. 

Sovelluksen suorittaminen yleisesti eri ympäristöissä kehityksessä ja
tuotannossa voi aiheuttaa erikoisia bugeja kun on aika julkaista. Jos kehität
Windowsilla ja julkaiset Linuxilla (tai muu kuin Windows) niin harkitse 
[virtuaalikoneen](/#virtualization_title) käyttöä.

Chris Tankersley:llä on erittäin hyödyllinen blogijulkaisu työkaluista, joita
hän käyttää [PHP kehitykseen Windowsilla][windows-tools].

[easyphp]: http://www.easyphp.org/
[phpmanager]: http://phpmanager.codeplex.com/
[openserver]: http://open-server.ru/
[wamp]: http://www.wampserver.com/en/
[php-downloads]: http://windows.php.net/download/
[php-iis]: http://php.iis.net/
[windows-path]: http://www.windows-commandline.com/set-path-command-line/
[windows-tools]: http://ctankersley.com/2016/11/13/developing-on-windows-2016/
[wpi]: https://www.microsoft.com/web/downloads/platform.aspx
[xampp]: http://www.apachefriends.org/en/xampp.html
