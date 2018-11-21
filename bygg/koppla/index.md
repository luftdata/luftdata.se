---
section: Bygg en mätstation
layout: docs
title: Koppla ihop de elektroniska komponenterna
authors:
  - Luftdaten.info
  - Hannes Ebner
pagination:
  start:
    name: Kom igång
    link: /bygg/
  previous:
    name: Installera firmware
    link: /bygg/firmware/
  next:
    name: Montera mätstationen
    link: /bygg/montera/
lead: false
wide: true
---

Du behöver [överföra firmware](../firmware) innan du kopplar ihop alla komponenter! Detta för att om det skulle vara så att firmware inte kan överföras så behöver du inte ta isär och sätta ihop allt igen. Det minskar också risken för att skada anslutningar när du kopplar in och ur USB-kabeln.

<div class="note">
  <h6>Andra versioner av NodeMCU än v3</h6>
  <p>Instruktionerna refererar till version 3 av NodeMCU. Detta kan identifieras med hjälp av anslutningarna VU och G (se kopplingsschema nedan). Hos andra versioner står RSV vid dessa anslutningar. På dessa kan VIN användas istället för VU och GND kan användas istället för G bredvid micro USB-porten.</p>
</div>

## Kopplingsschema NodeMCU v3 + SDS011 + DHT22

![Kopplingsschema NodeMCUv3 + SDS011 + DHT22](../img/nodemcuv3_sds011_dht22.jpg)

Se längre ner för hur BME/BMP-sensorerna ska kopplas.

## Koppla SDS011 (partiklar)

Alla pins är numrerade från vänster till höger. Se till att kopplingskablarna verkligen sitter på rätt ställe, det är lätt hänt att de hamnar mellan eller bredvid pins.

```
SDS011 Pin 1 -> Pin D1 / GPIO5
SDS011 Pin 2 -> Pin D2 / GPIO4
SDS011 Pin 3 -> GND
SDS011 Pin 4 -> unused
SDS011 Pin 5 -> VU (NodeMCU v3) / VIN (NodeMCU v1,v2)
SDS011 Pin 6 -> unused
SDS011 Pin 7 -> unused
```

## Koppla DHT22 (temperatur och luftfuktighet)

Alla pins är numrerade från vänster till höger. "Gallret" är framsidan.

Vissa DHT22 har väldigt tunna pins som kan göra det svårt att få kopplingskablarna att sitta ordentligt. I sådana fall kan det hjälpa att vrida om kopplingskablarna 90 grader för att de ska få bättre fäste.

```
DHT22 Pin 1 -> Pin 3V3 (3.3V)
DHT22 Pin 2 -> Pin D7 (GPIO13)
DHT22 Pin 3 -> unused
DHT22 Pin 4 -> Pin GND
```

## Koppla BMP180, BMP180 och BME280 (temperatur, luftfuktighet, lufttryck)

Dessa sensorer kopplas in via I2C som kräver 4 kablar:

```
BMx VCC -> Pin 3V3
BMx GND -> Pin GND
BMx SCL -> Pin D4 (GPIO2)
BMx SDA -> Pin D3 (GPIO0)
```

## Koppla in andra sensorer eller displays

Se ["Vanliga frågor"](/faq).

{% if page.pagination.next %}
---
#### Nästa steg: [{{ page.pagination.next.name }}]({{ page.pagination.next.link }})
{% endif %}
