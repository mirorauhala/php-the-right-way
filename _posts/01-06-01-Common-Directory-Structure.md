---
title: Yleinen hakemistorakenne
isChild: true
anchor:  common_directory_structure
---

## Yleinen hakemistorakenne {#common_directory_structure_title}

Yleinen kysymys aloittavien web-kehittäjien kesken on "minne laitan kaikki jutut?"
Vuosien aikana vastaus kysymykseen on ollut "missä sun `DocumentRoot` on."
Vaikka vastaus ei ole täydellinen, se on hyvä paikka aloittaa.

Tietoturvan vuoksi konfigurointitiedostojen ei kuuluisi olla saatavilla sivuston
vierailijoille; joten julkiset koodiskriptit ovat julkisessa hakemistossa ja 
yksityiset konfiguraatiot ja muut tiedot ovat sen hakemiston ulkopuolella.

Jokaisella tiimillä, CMS:llä ja kehyksellä on oma yleinen hakemistorakenne.
Kuitenkin jos joku on aloittamassa projektia yksin niin on vaikea tietää mitä
hakemistorakennetta käyttää.

[Paul M. Jones] on tehnyt hienoa tutkimustyötä yleisiin tapohin kymmenien 
tuhansien GitHub projektien  yleisistä käytännöistä PHP-alueella. Hän on koonnut
tutkimuksen pohjalta vakion tiedosto- ja hakemistorakenteen nimeltään
[The Standard PHP Package Skeleton]. Tässä hakemistorakenteessa `DocumentRoot`:n
kuuluisi osoittaa `public/` hakemistoon, yksikkötestien kuuluisi olla `tests/`
hakemistossa, ja kolmannen osapuolien kirjastot, kuten ne [composer]:n asentamat,
kuuluvat `vendor/` hakemistoon. Muut tiedostot ja hakemistot noudattaen 
[Standard PHP Package Skeleton]:ia on järkevintä projektin osallistujille.

[Paul M. Jones]: http://paul-m-jones.com/
[Standard PHP Package Skeleton]: https://github.com/php-pds/skeleton
[Composer]: /#composer_and_packagist
