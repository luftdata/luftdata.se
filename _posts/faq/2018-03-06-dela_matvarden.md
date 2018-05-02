---
layout: post
title: "Dela mätvärden"
date: 2018-03-06
categories: faq
wide: true
permalink: /faq/luftdata-influxdb-och-grafana
authors:
  - Erik Näsström
  - Torbjörn Söderberg
---
Förutom den statistik som du kan få via kartan på [luftdata.se](http://sweden.maps.luftdaten.info/#5/63.000/16.000) så finns det några andra alternativ:

## API

Luftdaten.info har ett eget API där du kan komma åt information från andra sensorer än din egen, följ instruktionerna på vår sida om [dataåtkomst](https://luftdata.se/data/).

## OpenSenseMap

Du kan dela med dig av datan från din partikelsensor till openSenseMap och se statistik via deras sida. Läs mer under vår [FAQ kring openSenseMap](/faq/luftdata-till-opensensemap).

## Home-Assistant

[Home-Assistant](https://home-assistant.io/) är en populär plattform för hemautomatisering.<br>
Luftdaten finns som en komponent att installera här: [`https://home-assistant.io/components/sensor.luftdaten/`](https://home-assistant.io/components/sensor.luftdaten/).<br>
Nedan finns ett exempel för hur det kan se ut i Home-Assistant. Exempel på .yaml kod för denna med medelvärden och kvaliten i text hittar du på [`https://github.com/Naesstrom/home_assistant/blob/master/sensors/luftdaten.yaml`](https://github.com/Naesstrom/home_assistant/blob/master/sensors/luftdaten.yaml).<br>

<img src="/assets/luftdata_hass.png" />

## Home-Assistant via JSON

Via en medlem i vår Facebook grupp kommer detta förslag, istället för att hämta datan via nätet till Home-Assistant kan du hämta det direkt från sensorns JSON flöde. Skapa följande sensorer för att hämta in luftdatan och temperatur samt luftfuktiget.

{% raw %}
```yaml
sensor:
  - platform: command_line
    name: "Luftdata PM10"
    command: 'curl http://192.168.xx.xx/data.json'
    value_template: "{{ value_json.sensordatavalues[0].value | round(2) }}"
    unit_of_measurement: "µg/m³"
  - platform: command_line
    name: "Luftdata PM2.5"
    command: 'curl http://192.168.xx.xx/data.json'
    value_template: "{{ value_json.sensordatavalues[1].value | round(2) }}"
    unit_of_measurement: "µg/m³"
  - platform: command_line
    name: "Luftdata Temperature DHT22"
    command: 'curl http://192.168.xx.xx/data.json'
    value_template: "{{ value_json.sensordatavalues[2].value | round(1) }}"
    unit_of_measurement: "°C"
  - platform: command_line
    name: "Luftdata Humidity DHT22"
    command: 'curl http://192.168.xx.xx/data.json'
    value_template: "{{ value_json.sensordatavalues[3].value | round(1) }}"
    unit_of_measurement: "%"
```
{% endraw %}

## Internt som JSON

Du kan även hämta informationen direkt från din sensor som JSON via adressen `http://{ip-till-sensorn}/data.json`.<br>
IP till din sensor är den som är aktiv i ditt lokala nätverk, inte 192.168.4.1 som användes under den ursprungliga konfigurationen. Denna går t.ex. bra att använda i Node-Red för vidare bearbetning.
