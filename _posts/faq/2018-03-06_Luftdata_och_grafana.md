---
layout: post
title: "Luftdata, InfluxDB & Grafana"
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



Also for "Home Assistant" there is a plugin, the configuration instructions can be found here: 
https://home-assistant.io/components/sensor.luftdaten/

rom the sensor itself, the data can be retrieved as JSON via the address http: // {ip-des-sensors} /data.json or http: // fine dust sensor {nodemcu-id} .local. The IP is the IP of the sensor in the local network, not the 192.168.4.1, which is used for the initial configuration. The 2nd variant should normally work under Linux and MacOS. For Windows possibly still a software must be installed. See the point 'Access to the sensor'.
