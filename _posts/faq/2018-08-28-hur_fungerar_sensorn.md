---
layout: post
title: "Hur fungerar sensorn egentligen?"
date: 2018-08-28 09:19:00
categories: faq
wide: true
permalink: /faq/hur-fungerar-sensorn
authors:
  - Linus Ludvigsson
---
Sensorn bygger på ljusspridning. Partiklar sprider ljus beroende på sin storlek och antal, fler partiklar sprider mer ljus (högre spridd intensitet) färre sprider mindre. Partiklar >0.5 µm sprider ljus enl Mie spridning, Förenklat så sprider stora partiklar (PM10) ljus i en mindre vinkel, och små partiklar (PM2.5) sprider i en större vinkel. Spridningen beror också på vilket material partikeln består av och vilket brytningsindex den har, ex. partiklar bestående av sot eller kvarts kommer ge olika spridning.

Massan beräknas utifrån antaganden om vilken densitet som partiklarna har samt antagande om brytningsindex. Sensorn i SDS011 räknar inte antalet partiklar utan utgår från ljusspridningen från den provtagna luften.

Det man skulle kunna göra är att räkna baklänges från masskoncentrationen med antagandet om att alla partiklar är sfäriska och har en densitet på 1. Det skulle för mätvärden på 4 µg/m3 PM2.5 och 8 µg/m3 PM10 ge en antalskoncentration på 496 partiklar/ml luft, vilket är ett helt OK värde för för utomhusluft.

Som en side note så kan man få ut antalskoncentration ner på enstaka partiklar mha ljusspridning, men det kräver bättre kontroll över optiken och hur partiklarna rör sig genom lasern. Ytterligare en side note om omvandling från massa till antal är att man i princip kan strunta i PM10 värdet och bara räkna på PM2.5. Antalet partiklar är alltid bra mycket högre i de små storleksfraktionerna, i exemplet ovan ger PM2.5 490 partiklar/ml medan PM10 bara ger ett tillskott på 6#/ml.
