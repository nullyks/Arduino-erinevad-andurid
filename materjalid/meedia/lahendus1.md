# Tajutava temperatuuri näitekood

Näide kasutab Adafruiti DHT teeki, mille paigaldamist kirjeldab [DHT22 peatükk](../5_DHT22_andur.md).

~~~cpp
#include <DHT.h>

const int DHT_VIIK = 2;
const int DHT_TUUP = DHT22;

DHT dht(DHT_VIIK, DHT_TUUP);

void setup() {
  Serial.begin(9600);
  dht.begin();
}

void loop() {
  // DHT22 vajab mõõtmiste vahel vähemalt ligikaudu kaks sekundit.
  delay(2000);

  float temperatuur = dht.readTemperature();
  float ohuniiskus = dht.readHumidity();

  if (isnan(temperatuur) || isnan(ohuniiskus)) {
    Serial.println("DHT22 lugemine ebaõnnestus.");
    return;
  }

  // Kolmas argument false tähendab, et kasutame Celsiuse kraade.
  float kuumaindeks =
      dht.computeHeatIndex(temperatuur, ohuniiskus, false);

  Serial.print("Temperatuur: ");
  Serial.print(temperatuur, 1);
  Serial.print(" °C, suhteline õhuniiskus: ");
  Serial.print(ohuniiskus, 1);
  Serial.print(" %, kuumaindeks: ");
  Serial.print(kuumaindeks, 1);
  Serial.println(" °C");
}
~~~

Kuumaindeks on mõeldud eelkõige kuumade ja niiskete tingimuste hindamiseks. Jahedamate tingimuste korral ei kirjelda tulemus üldist soojusmugavust.
