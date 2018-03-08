---
layout: post
title: "Dela mätvärden"
date: 2018-03-06
categories: faq
wide: true
permalink: /faq/luftdata-influxdb-och-grafana
authors:
  - Erik Näsström
---
Förutom den statistik som du kan få via kartan på [luftdata.se](http://sweden.maps.luftdaten.info/#5/63.000/16.000) så finns det några andra alternativ:

## API
Luftdaten.info har ett eget API där du kan komma åt information från andra sensorer än din egen, följ instruktionerna på vår sida om [dataåtkomst](http://luftdata.se/data/)

## OpenSenseMap
Du kan dela med dig av datan från din partikelsensor till openSenseMap och se statistik via deras sida. Läs mer under vår [FAQ kring openSenseMap](http://luftdata.se/faq/luftdata-till-opensensemap)

## Home-Assistant
[Home-Assistant](https://home-assistant.io/) är en populär plattform för hemautomatisering.<br>
Luftdaten finns som en komponent att installera här: https://home-assistant.io/components/sensor.luftdaten/<br>
Nedan finns ett exempel för hur det kan se ut i Home-Assistant. Exempel på .yaml kod för denna med medelvärden och kvaliten i text hittar du [här](https://github.com/Naesstrom/home_assistant/blob/master/sensors/luftdaten.yaml)<br>
<img src="/assets/luftdata_hass.png" />

## Internt som JSON
Du kan även hämta informationen direkt från din sensor som JSON via adressen http: // {ip-till-sensorn} /data.json<br>
IP till din sensor är den som är aktiv i ditt lokala nätverk, inte 192.168.4.1 som användes under den ursprungliga konfigurationen. Denna går t.ex. bra att använda i Node-Red för vidare bearbetning.
