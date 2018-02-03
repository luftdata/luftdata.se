---
layout: post
title: "Hur kopplar man in andra sensorer?"
date: 2018-02-03 09:39:00
categories: faq
wide: true
permalink: /faq/andra-sensorer
authors:
  - luftdaten.info
  - Hannes Ebner
---
Mätstationen har stöd för andra sensorer utöver SDS011 och DHT22. Aktuellt finns det stöd för följande:

  - PPD42NS (luftpartiklar, första sensorn som luftdaten.info använde sig av)
  - SDS011, SDS018, SDS021 (luftpartiklar, SDS011 är den aktuella rekommendationen)
  - BMP180/BMP280 (temperatur, lufttryck)
  - BME280 (temperatur, luftfuktighet, lufttryck)
  - DHT22 (temperatur, luftfuktighet)

Se [bygginstruktionerna](/bygg/koppla) för kopplingsscheman för SDS011 och DHT22.

BMP180, BMP280 och BME280 kopplas in via I2C:

```
BMx VCC -> Pin 3V3
BMx GND -> Pin GND
BMx SCL -> Pin D4 (GPIO2)
BMx SDA -> Pin D3 (GPIO0)
```

Du behöver aktivera den nya sensorn i konfigurationen och starta om enheten för att initialisera sensorn.