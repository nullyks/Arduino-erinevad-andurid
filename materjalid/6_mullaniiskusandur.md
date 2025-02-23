# Mullaniiskuse andurid

Levinud mullaniiskuse andurid töötavad kahel erineval põhimõttel - mõõdetakse, mulla elektrilist takistust kahe kontaktpunkti vahel (takistuspõhine mullaniiskusandur) või moodustatakse kahe elektroodi abil kondensaator, kus muld toimib dielektrikuna (mahutavuspõhine mullaniiskusandur). Takistuspõhise mullaniiskusanduri puhul on takistus seda väiksem, mida niiskem on muld. Mahutavuspõhise mullaniiskusanduri puhul mõõdetakse aega, mis kulub kindla pinge juures kondensaatori laadimiseks, kuna dielektrikuna selles kondensaatoris toimib muld ja märjema mulla dielektriline konstant on suurem, siis mida märjem on muld, seda kiiremine kondensaator täis laaditakse.

Ülaltoodust järeldub, et mõlema anduri puhul ei saa me tegelikult täpselt teada mulla suhtelist niiskust, vaid ainult niiskuse muutumist võrreldes mingi kindla algväärtusega. Seega tuleb oma rakenduses see algväärtus kalibreerida.

## Mahutavuspõhise mullaniiskussensori liidestamine Arduino UNO-ga
![alt text](meedia/capSensor.png)
*Allikas: https://media.digikey.com/pdf/data%20sheets/dfrobot%20pdfs/sen0193_web.pdf*

Sensoril on kolm viiku: signaal (1), toide (2), maandus (3). Toide (2) ja maandus (3) ühendatakse vastavalt Arduino UNO 5V ja GND viikudega. Signaali (1) loetakse analoogviigu abil.

Näitekood:
~~~cpp
//sensori tagastatav väärtus kuivana õhu käes
#define kuivData 520 
//sensori tagastatav väärtus kui see on kastetud vette
#define veesData 260 
int vahemikud = (kuivData - veesData)/3; 
int mullaNiiskus = 0;

void setup() {
 Serial.begin(9600); 
}

void loop() {
mullaNiiskus = analogRead(A0); //eeldame, et sensori signaalviik on ühendatud A0-ga
if(mullaNiiskus > veesData && mullaNiiskus < (veesData + vahemikud)){
    Serial.println("Väga niiske");
}else if(mullaNiiskus > (veesData + vahemikud) && mullaNiiskus < (kuivData - vahemikud)){
    Serial.println("Niiske");
}else if(mullaNiiskus < kuivData && mullaNiiskus > (kuivData - vahemikud)){
    Serial.println("Kuiv");
}
delay(100);
} 
~~~

## Takistuspõhise mullaniiskussensori liidestamine Arduino UNO-ga

![alt text](meedia/rstSensor.jpg)

*Allikas: https://github.com/sparkfun/Soil_Moisture_Sensor*

Sensoril on kolm viiku: toide (1), maandus (2) ja signaal (3). Toide (1) ja maandus (2) ühendatakse vastavalt Arduino UNO 5V ja GND viikudega. Signaali (3) loetakse analoogviigu abil.

![alt text](meedia/rstSensorNäide.png)

[Interaktiivne simulatsioon](https://www.tinkercad.com/things/4pnOvk3wPmM-mullaniiskusandur?sharecode=pWHr1Q7Gbze-wi4If8gJDYhszK5PpjZSsQYjYZZKnzA)