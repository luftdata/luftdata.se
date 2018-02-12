---
layout: post
title: "Mäter sensorn rätt?"
date: 2018-02-12 09:54:00
categories: faq
wide: true
permalink: /faq/matnoggrannhet-sds011
authors:
  - Peter Krantz
---

I Tyskland har flera utvärderingar gjorts av den sensor, Nova Fitness Co. SDS011, som vanligen används i mätstationen: 

I en analys av _Materialprüfungsanstalt Universität Stuttgart_ (Materialprovningsanstalten vid Stuttgarts Universitet) framgår att SDS011 korrelerar med data från Grimm OPC 1.109 för PM1 och PM2.5 (finkorniga partiklar) men att vissa enstaka händelser kan missas för PM10.

Källa: Frick, Reichert, 2016, _[Validierungsversuche mit kostengünstiger Feinstaubmesstechnik und erste Ergebnisse des Sensor-Netzwerks Stuttgart](https://luftdaten.info/wp-content/uploads/2017/05/ALS-Kolloquium_2016_FrickReichert_small.pdf)_, Materialprüfungsanstalt Universität Stuttgart.

En annan analys av _LUBW, Statens institut för miljömätning och naturskydd i Baden-Württemberg_, framkommer att de uppmätta värdena för sensorn SDS011 och partikelsensorn från Grimm korrelerar under dagar med en genomsnittlig luftfuktighet på ca 50-70% och partikelnivåer under 20 μg/m³. Dock reagerar SDS011-sensorerna på växlingar i klimatförhållanden som luftfuktighet, lufttryck och lufttemperatur, vilket kan resultara i signifikanta avvikelser.

Dessutom fann man att SDS011-sensorerna kan leverera olika värden beroende på produktionsbatch. För att kunna garantera jämförbara mätvärden även vid olika batcher skulle sensorerna behöva kalibreras före användning, vilket för närvarande inte är möjligt.

Källa: 2017, _[Messungen mit dem Feinstaubsensor SDS011](http://www4.lubw.baden-wuerttemberg.de/servlet/is/268831/messungen_mit_dem_feinstaubsensor_sds011.pdf?command=downloadContent&filename=messungen_mit_dem_feinstaubsensor_sds011.pdf)_, LUBW Landesanstalt für Umwelt, Messungen und Naturschutz Baden-Württemberg, s 20




