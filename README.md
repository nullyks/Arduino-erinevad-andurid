# Erinevate andurite liidestamine Arduino UNO-ga

See õppematerjal selgitab jõu- ja paindeanduri, TMP36 temperatuurianduri, HC-SR04 kaugusanduri, HC-SR501 PIR-liikumisanduri, DHT22 õhuniiskus- ja temperatuurianduri ning mullaniiskusandurite kasutamist ja Arduino UNO-ga liidestamist.

## Kasutatavad arendusplaadid

Kursusel kasutatakse Arduino UNO R3 ja Arduino UNO R4 WiFi arendusplaate. Õppematerjali ühendusskeemid ja Tinkercadi näited on koostatud UNO R3 jaoks.

Näidetes kasutatavad viigud ja Arduino funktsioonid töötavad ka UNO R4 WiFi plaadil. Mõlemad plaadid kasutavad 5 V loogikataset ning neil on samades kohtades digitaalviigud D0–D13 ja analoogviigud A0–A5. Plaatide olulised erinevused tuuakse materjalis eraldi välja.

| Erinevus | Arduino UNO R3 | Arduino UNO R4 WiFi |
|---|---|---|
| USB-pistik | USB-B | USB-C |
| Mikrokontroller | 8-bitine ATmega328P | 32-bitine Renesas RA4M1 |
| Soovituslik vool ühe I/O-viigu kaudu | kuni 20 mA | kuni 8 mA |
| Analoog-digitaalmuunduri resolutsioon | 10 bitti | vaikimisi 10 bitti, kuni 14 bitti |

Lisateavet plaatide erinevuste kohta leiad [Arduino ametlikust UNO R3 ja UNO R4 võrdlusest](https://support.arduino.cc/hc/en-us/articles/9350551575964-What-s-the-difference-between-UNO-R3-and-UNO-R4-boards).

## Eelteadmised

Enne selle õppematerjali kasutamist peaks õppija oskama:

* ühendada Arduino UNO arendusplaadi arvutiga;
* valida Arduino IDE-s õige arendusplaadi ja pordi;
* laadida programmi Arduino arendusplaadile;
* kasutada makettplaati ning lugeda lihtsat ühendusjoonist;
* avada Arduino IDE Serial Monitori.

Vajaduse korral vaata enne jätkamist läbi [Arduino sissejuhatuse õppematerjal](https://github.com/nullyks/Arduino-sissejuhatus).

## Õpieesmärgid

Pärast õppematerjali läbimist oskad erinevate andurite abil mõõta temperatuuri, õhuniiskust, mulla niiskust ja kaugust. Saad teada, kuidas takistuse muutumise põhjal hinnata paindumist ja rakendatud jõudu ning kuidas PIR-liikumisanduriga liikumist tuvastada.

## Õpiväljundid

Materjali edukalt läbinud õppija oskab:

* loetleda ja kirjeldada Arduino arendusplaadiga liidestatavaid andureid;
* selgitada käsitletud andurite tööpõhimõtteid;
* ühendada andureid Arduino UNO arendusplaadiga;
* lugeda ja töödelda andurite väljastatud analoog- ja digitaalsignaale;
* kalibreerida suhtelist mõõtetulemust andvaid andureid;
* luua andureid kasutavaid lihtsaid seadmeid.

## Hindamisjuhend

Selle õppematerjali puhul ei rakendata eristavat hindamist.

Õppija on materjali omandanud, kui ta suudab iseseisvalt lahendada vähemalt neli iseseisvat ülesannet viiest. Korrektne lahendus sisaldab seadme ühendusjoonist ja kommenteeritud programmikoodi.

## Ohutus

* Koosta või muuda vooluahelat ainult siis, kui Arduino on USB-kaablist ja muudest toiteallikatest lahutatud.
* Enne toite ühendamist kontrolli komponentide viikude järjestust ja polaarsust.
* Veendu, et 5 V ja GND poleks omavahel otse ühendatud.
* Ära ületa Arduino arendusplaadi viikude lubatud voolu.

## Vajalikud vahendid

*   1 x personaalarvuti (sobib Windowsi, Linuxi või macOS-iga)
*   1 x Arduino UNO R3 või Arduino UNO R4 WiFi arendusplaat
*   1 x plaadile sobiv USB-andmesidekaabel (UNO R3 puhul tavaliselt USB-B, UNO R4 WiFi puhul USB-C)
*   3 x LED (soovitatavalt erivärvilised)
*   3 x takisti (470 Ω)
*   1 x takisti (4,7 kΩ)
*   1 x takisti (47 kΩ)
*   1 x takisti (10 kΩ, vajalik palja neljaviigulise DHT22 anduri korral)
*   1 x paindeandur
*   1 x FSR-jõuandur
*   1 x TMP36 temperatuuriandur
*   2 x HC-SR501 PIR-liikumisandur
*   1 x HC-SR04 ultraheli-kaugusandur
*   1 x DHT22 õhutemperatuuri- ja õhuniiskusandur või vastav andurimoodul
*   1 x mahutavuspõhine mullaniiskusandur
*   1 x takistuspõhine mullaniiskusandur
*   1 x makettplaat
*   makettplaadi juhtmed (isane-isane)
*   makettplaadi juhtmed (emane-isane)

## Õppematerjali osad
* [FSR-jõuandur ja paindeandur](materjalid/1_FSR_tüüpi_andurid.md)
* [TMP36 temperatuuriandur](materjalid/2_TMP36_temperatuuriandur.md)
* [HC-SR04 ultraheli-kaugusandur](materjalid/3_HC-SR04_kaugusandur.md)
* [HC-SR501 PIR-liikumisandur](materjalid/4_PIR_tüüpi_andurid.md)
* [DHT22 temperatuuri- ja õhuniiskusandur](materjalid/5_DHT22_andur.md)
* [Mullaniiskusandurid](materjalid/6_mullaniiskusandur.md)
* [Iseseisvad ülesanded](materjalid/7_iseseisvad_ülesanded.md)

## Õppematerjali koostajad

Tanel Toova (tanel.toova@tlu.ee)
