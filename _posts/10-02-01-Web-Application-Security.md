---
isChild: true
anchor:  web_application_security
title: Verkkosovellusten turvallisuus
---

## Verkkosovellusten turvallisuus {#web_application_security_title}

On todella tärkeää jokaisen PHP kehittäjän opetella
[verkkosovellusten tietoturvan perusteet][4], joka voidaan rikkoa kouralliseen
aiheisiin:

1. Koodin ja tiedon erotus.
   * Kun data suoritetaan koodina, saat SQL injektion, cross-site skriptin,
     paikallisen/ulkoisen tiedoston sisällytyksen, jne.
   * Kun koodi tulostetaan datana, saat informaatiovuotoja (lähdekoodivuotoja,
     tai C-ohjelmien tapauksessa, tarpeeksi informaatiota[ASLR][5]:n ohittamiseen).
2. Sovelluslogiikka.
   * Puuttuva autentikointi tai luvanvalvonta.
   * Syötteen validointi.
3. Toimintaympäristö.
   * PHP versiot.
   * Kolmannen osapuolen kirjastot.
   * Käyttöjärjestelmä.
4. Kryptografian heikkoudet.
   * [Heikot satunnaisluvut][6].
   * [Chosen-ciphertext hyökkäykset][7].
   * [Sivukanavan tietovuodot][8].

On pahoja ihmisiä, jotka ovat valmiita ja halukkaita hyökkäämään
verkkosovellukseesi. On tärkeää, että otat tarvittavat varotoimenpiteet
parantaaksesi verkkosovelluksesi tietoturvaa. Onneksi hienot ihmiset
[The Open Web Application Security Project][1] (OWASP) -projektissa ovat
koonneet kattavan luettelon tunnetuista turvallisuuskysymyksistä ja
menetelmistä suojautua niitä vastaan. Tämä on pakollinen luettava
tietoturvatietoiselle kehittäjälle. [Survive The Deep End: PHP Security][3] by
Padraic Brady on myös toinen hyvä verkkosovellusten tietoturvan ohje PHP:lle.

* [Lue OWASP Security Guide][2]


[1]: https://www.owasp.org/
[2]: https://www.owasp.org/index.php/Guide_Table_of_Contents
[3]: https://phpsecurity.readthedocs.io/en/latest/index.html
[4]: https://paragonie.com/blog/2015/08/gentle-introduction-application-security
[5]: http://searchsecurity.techtarget.com/definition/address-space-layout-randomization-ASLR
[6]: https://paragonie.com/blog/2016/01/on-design-and-implementation-stealth-backdoor-for-web-applications
[7]: https://paragonie.com/blog/2015/05/using-encryption-and-authentication-correctly
[8]: http://blog.ircmaxell.com/2014/11/its-all-about-time.html

