### näitekood

~~~cpp
#include <DHT.h>

// DHT sensor setup
#define DHTPIN 2        // Sensor on ühendatud digitaalsisendisse 2
#define DHTTYPE DHT22   // Kasutame DHT22 sensorit

DHT dht(DHTPIN, DHTTYPE);

void setup() {
    Serial.begin(9600);
    dht.begin();
}

void loop() {
    float T = dht.readTemperature();  // Temperatuur Celsiuse järgi
    float R = dht.readHumidity();     // Õhuniiskus protsentides

    if (isnan(T) || isnan(R)) {
        Serial.println("Sensorilt lugemine ebaõnnestus!");
        return;
    }

    // Heat Index arvutamine vastavalt valemile
    float HI = heatIndex(T, R);

    Serial.print("Temperatuur: ");
    Serial.print(T);
    Serial.print(" °C, Õhuniiskus: ");
    Serial.print(R);
    Serial.print(" %, Heat Index: ");
    Serial.print(HI);
    Serial.println(" °C");

    delay(2000);  // Oota 2 sekundit enne uut mõõtmist
}

// Heat Index'i arvutamise funktsioon
float heatIndex(float T, float R) {
    float c1 = -8.78469475556;
    float c2 = 1.61139411;
    float c3 = 2.33854883889;
    float c4 = -0.14611605;
    float c5 = -0.012308094;
    float c6 = -0.0164248277778;
    float c7 = 0.002211732;
    float c8 = 0.00072546;
    float c9 = -0.000003582;

    return c1 + (c2 * T) + (c3 * R) + (c4 * T * R) + 
           (c5 * T * T) + (c6 * R * R) + 
           (c7 * T * T * R) + (c8 * T * R * R) + 
           (c9 * T * T * R * R);
}
~~~