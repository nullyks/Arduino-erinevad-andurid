# Iseseisvad ülesanded

Need ülesanded on mõeldud eelnevates peatükkides käsitletud andurite ühendamise, kalibreerimise ja programmeerimise harjutamiseks. Püüa ülesanne enne näidislahenduse vaatamist iseseisvalt lahendada.

Kui ülesandes pole teisiti öeldud, peab lahendus sisaldama:

* kasutatud komponentide nimekirja;
* komponentide ühendusjoonist;
* kommenteeritud programmikoodi;
* mõõtetulemuse või seadme töö kontrollimist.

Tinkercadi näidised kasutavad Arduino UNO R3 plaati. Ülesannetes kasutatavad viigud ja Arduino funktsioonid sobivad ka UNO R4 WiFi plaadile. Kui Tinkercadi skeemil on LED-iga 220 Ω takisti, kasuta füüsilises vooluahelas 470 Ω takistit.

**Ohutus:** koosta või muuda vooluahelat ainult siis, kui Arduino on USB-kaablist ja muudest toiteallikatest lahutatud. Enne toite ühendamist kontrolli komponentide viikude järjestust ning veendu, et 5 V ja GND poleks omavahel otse ühendatud.

## Temperatuuriindikaator

Ehita TMP36 anduriga seade, mis näitab temperatuuri kolme LED-i abil:

* temperatuuril alla 25 °C põleb roheline LED;
* temperatuuril 25 °C kuni alla 50 °C põleb kollane LED;
* temperatuuril 50 °C või rohkem põleb punane LED.

Nõuded lahendusele:

* vali vajalikud komponendid;
* koosta komponentide ühendusjoonis;
* kasuta iga LED-iga 470 Ω voolupiiravat takistit;
* teisenda TMP36 analoognäit Celsiuse kraadideks;
* taga, et korraga põleks ainult üks LED;
* väljasta mõõdetud temperatuur ka Serial Monitori;
* esita kommenteeritud programmikood.

Kui mõõdad eseme pinnatemperatuuri, peab TMP36 korpus olema mõõdetava pinnaga heas soojuslikus kontaktis. Vajaduse korral tuleb andur elektriliselt isoleerida.

[Lahendus Tinkercadis](https://www.tinkercad.com/things/cQjUggPqq6G-kraadiklaas?sharecode=kRSq5cS8ZoXwZzuZ3Bnfg2t21wFiMCHmo1ixd-FUU_o)

## Nurgamõõtja

Ehita paindeanduriga seade, mis hindab ukse avanemisnurka vahemikus 0–90°:

* 0° tähistab suletud ust;
* 90° tähistab täielikult avatud ust;
* vahepealsetes asendites kuvatakse hinnanguline avanemisnurk.

Nõuded lahendusele:

* vali vajalikud komponendid ja koosta ühendusjoonis;
* mõõda paindeanduri toornäit suletud ukse asendis ja salvesta see 0° kalibreerimisväärtusena;
* mõõda toornäit täielikult avatud ukse asendis ja salvesta see 90° kalibreerimisväärtusena;
* teisenda kalibreeritud näitude vahemik funktsiooniga `map()` vahemikuks 0–90°;
* piira tulemus funktsiooniga `constrain()` vahemikku 0–90°;
* kuva Serial Monitoris „Uks on suletud”, kui arvutatud nurk on 0–2°;
* kuva „Uks on täielikult avatud”, kui arvutatud nurk on 88–90°;
* muudel juhtudel kuva arvutatud avanemisnurk;
* esita kommenteeritud programmikood.

Piirväärtuste ümber kasutatakse väikest tolerantsi, sest analooganduri näit võib ka muutumatu asendi korral veidi kõikuda. Paindeandur võimaldab hinnata avanemisnurka, kuid ilma täpsema kalibreerimiseta ei ole tegemist täppismõõtmisega.

[Lahendus Tinkercadis](https://www.tinkercad.com/things/3V9UcvTzIj1-nurgamootja?sharecode=WAsKOISfquhTc_rPQmFXddn0cb7u2M9CKWqLd5H3Xsc)

## Parkimisandur

Ehita HC-SR04 kaugusanduri ja LED-iga seade, mis muudab LED-i eredust vastavalt mõõdetud kaugusele:

* kaugusel 100 cm või rohkem on LED välja lülitatud;
* kaugusel 10 cm või vähem töötab LED 100% täiteteguriga;
* kaugustel 10–100 cm suureneb LED-i täitetegur takistusele lähenemisel sujuvalt.

Nõuded lahendusele:

* vali vajalikud komponendid ja koosta ühendusjoonis;
* ühenda LED PWM-võimekusega digitaalviiguga;
* kasuta LED-iga 470 Ω voolupiiravat takistit;
* kasuta HC-SR04 mõõtmisel puuduva kaja jaoks ajalimiiti;
* kui kaja ei tuvastata, lülita LED välja ja kuva Serial Monitoris vastav teade;
* teisenda kaugus funktsiooniga `map()` väärtuseks 0–255;
* piira tulemus funktsiooniga `constrain()` lubatud vahemikku;
* juhi LED-i funktsiooniga `analogWrite()`;
* kuva mõõdetud kaugus ka Serial Monitoris;
* esita kommenteeritud programmikood.

PWM-i täitetegur ja inimese tajutav LED-i eredus ei ole täpselt võrdelised. Selles ülesandes piisab ligikaudu sujuvast ereduse muutumisest.

[Lahendus Tinkercadis](https://www.tinkercad.com/things/cKNpBYrm39Y-parkimisandur?sharecode=diUC6Rv2m9zUBQwQIQBHixdFfO-qHHevzsPHAZhokpM)

## Tajutav temperatuur

Kõrge õhutemperatuuri korral mõjutab suhteline õhuniiskus seda, kui kuumana inimene keskkonda tajub. Kuumaindeks ehk *Heat Index* ühendab õhutemperatuuri ja suhtelise õhuniiskuse üheks hinnanguliseks tajutava temperatuuri väärtuseks.

Ehita DHT22 anduriga seade, mis arvutab ja kuvab kuumaindeksi Celsiuse kraadides.

Nõuded lahendusele:

* vali vajalikud komponendid ja koosta ühendusjoonis;
* kasuta sama Adafruiti DHT teeki nagu DHT22 peatükis;
* loe õhutemperatuur ja suhteline õhuniiskus;
* kontrolli funktsiooniga `isnan()`, kas andurilt saadi kehtivad näidud;
* arvuta kuumaindeks funktsiooniga `dht.computeHeatIndex(temperatuur, ohuniiskus, false)`;
* kuva Serial Monitoris temperatuur, suhteline õhuniiskus ja arvutatud kuumaindeks;
* jäta mõõtmiste vahele vähemalt kaks sekundit;
* esita kommenteeritud programmikood.

Funktsiooni kolmas argument `false` määrab, et sisend- ja väljundtemperatuuri ühik on Celsiuse kraad.

Kuumaindeks on mõeldud eelkõige kuumade ja niiskete tingimuste hindamiseks. Jahedamate tingimuste korral ei tohiks tulemust tõlgendada üldise mugavusindeksina.

[Kuumaindeksi arvutamise selgitus](https://www.wpc.ncep.noaa.gov/html/heatindex_equation.shtml)

[Näitekood](meedia/lahendus1.md)

## Ligikaudne keskmine kiirus

Ehita kahe HC-SR501 PIR-liikumisanduriga seade, mis hindab liikuva inimese või muu sooja objekti keskmist kiirust kahe mõõtepunkti vahel.

Keskmine kiirus arvutatakse valemiga:

$$
kiirus = \frac{mõõtepunktide\ vaheline\ kaugus}{liikumiseks\ kulunud\ aeg}
$$

Nõuded lahendusele:

* vali vajalikud komponendid ja koosta ühendusjoonis;
* paiguta kaks PIR-andurit teadaolevale kaugusele ning nii, et nende tuvastusalad võimalikult vähe kattuksid;
* määra mõlemal anduril võimalikult lühike viiteaeg;
* oota enne mõõtmist, kuni mõlemad PIR-andurid on pärast sisselülitamist stabiliseerunud;
* tuvasta kummagi anduri väljundi üleminek olekust `LOW` olekusse `HIGH`;
* salvesta esimese anduri rakendumise aeg funktsiooniga `millis()`;
* salvesta teise anduri rakendumise aeg ainult siis, kui esimene andur on juba rakendunud;
* arvuta kahe ajamomendi vahe sekundites;
* arvuta keskmine kiirus meetrites sekundis ja kilomeetrites tunnis;
* kuva tulemus Serial Monitoris;
* lähtesta mõõtmine pärast tulemuse kuvamist;
* esita kommenteeritud programmikood.

PIR-anduril on lai tuvastusala ja selle rakendumishetk pole täpselt määratud. Seetõttu sobib ülesanne keskmise kiiruse arvutamise põhimõtte õppimiseks, mitte täppismõõtmiseks.

[Lahendus Tinkercadis](https://www.tinkercad.com/things/7fAl1Fbw7X3-keskmine-kiirus?sharecode=gutFIa5qB359G3dN3XFVBHUbmmsi5Asrxt9h1dy4LbY)
