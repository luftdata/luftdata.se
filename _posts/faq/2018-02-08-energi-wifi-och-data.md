---
layout: post
title: "Hur mycket energi och data förbrukar mätstationen?"
date: 2018-02-08 11:13:00
categories: faq
wide: true
permalink: /faq/energi-wifi-och-data
authors:
  - Erik Näsström
---
## Kostnad

Hela partikelsensorn drar ungefär 1 watt, om den är på ett helt år så blir det (1W x 24h x 365 dagar) / 1000 = 8.76 kWh så ungefär 3,50:- per år. _(40 öre/KWh)_

## Energi

USB kabeln kan förlängas till ca 6-7m då ingen data skickas via ledningarna utan bara elen.
Lösningar för att driva enheten via solceller och batteri är under utveckling.

## WIFI

Wifi måste alltid vara igång, ESP8266 enheten lagrar ingen data lokalt så utan uppkoppling finns ingen data.
Dataförbrukningen är extremt låg då den bara skickar stationens ID, klockslag och mätdatan som text.