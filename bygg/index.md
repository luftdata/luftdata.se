---
section: Bygg en mätstation
layout: docs
title: Kom igång
authors:
  - Luftdaten.info
  - Hannes Ebner
pagination:
  next:
    name: Installera firmware
    link: /bygg/firmware/
lead: true
wide: true
---

Monteringen är utformad så att alla kan bygga en mät&shy;station. Med endast 7 kopplings&shy;kablar och 2 bunt&shy;band gör du ett utvecklings&shy;kort och en sensor till en mät&shy;station.

Innehållet i dessa instruktioner är baserade på [motsvarande instruktioner på tyska på luftdaten.info](https://luftdaten.info/feinstaubsensor-bauen/). Det finns även [alternativa instruktioner](/assets/bygginstruktioner_lov-iot.pdf) i ett utskriftsvänligt format som har tagits fram av projektet [LoV-IoT](https://www.loviot.se/).

![Bild på färdig mätstation](img/matstation.jpg)

Nedan finns en lista med alla delar som behövs, samt rekommenderade inköpsställen om man befinner sig i Sverige. Gå direkt till avsnittet "Färdiga paketeringar" nedan om du är intresserad av att köpa ett helt kit.

## Inköpslista

  * NodeMCU ESP8266 v3 (CPU & WLAN) [[Lawicel](https://www.lawicel-shop.se/nodemcu-v3-with-esp-12e-ch340), [Kjell](https://www.kjell.com/se/sortiment/el-verktyg/arduino/utvecklingskort/nodemcu-utvecklingskort-p87949), [Amazon](https://www.amazon.de/dp/B06Y1ZPNMS/)]
  * SDS011 (partikelsensor) [[m.nu](https://www.m.nu/sensorer-matinstrument/nova-pm-sensor-sds011-1), [Lawicel](https://www.lawicel-shop.se/nova-pm-sensor-sds011), [AliExpress](https://www.aliexpress.com/wholesale?SortType=price_asc&shipCountry=de&SearchText=sds011&CatId=523), [Segor](http://www.segor.de)]
  * DHT22 (temp. och luftfuktighet, *valfritt* - se även alternativ för mer stabil sensor - BME280 - nedan) [[m.nu](https://www.m.nu/sensorer-matinstrument/dht22-temperature-humidity-sensor-extras), [Lawicel](https://www.lawicel-shop.se/dht22-temperature-humidity-sensor), [Amazon](https://www.amazon.de/dp/B06XF4TNT9/)]
  * BME280 (temperatur, tryck, luftfuktighet, *valfritt*) Kan kräva lödning. [r-pi.se](https://r-pi.se/products/bme280-gy-sensor-spi-o-i2c-fukttemp-och-barometrisk-tryck), [Lawicel](https://www.lawicel-shop.se/catalogsearch/result/?q=BME280), [Elfa](https://www.elfa.se/sv/bme280-temperature-humidity-pressure-sensor-adafruit-2652/p/30091192?q=BME280&pos=2&origPos=2&origPageSize=10&track=true)
  * Kopplingskablar, ca. 20 cm, hona-hona [[m.nu](https://www.m.nu/breadboarding/breadboarding-premium-female-female-jumper-wires-40-x-6-150mm), [Lawicel](https://www.lawicel-shop.se/kablage-labb/kopplingstrad/jumper-wires-f-f-15cm-10p), [Kjell](https://www.kjell.com/se/sortiment/el-verktyg/arduino/tillbehor/luxorparts-delbar-kopplingskabel-40-pol-hona-hona-p87906)]
  * USB-kabel, längd beroende på situation, USB 2.0 A hane - USB 2.0 micro hane, t.ex. platt utformning för fönstertätningar [[Conrad](https://www.conrad.se/USB-2.0-F%f6rl%e4ngningskabel-Renkforce-%5b1x-USB-2.0-A-hane-1x-USB-2.0-A-hona%5d-H%f6gflexibel-3-m-Svart.htm?websale8=conrad-swe&pi=1365367&amp;ci=SHOP_AREA_258249_0410105)]
  * USB-strömadapter [[IKEA](https://www.ikea.com/se/sv/p/koppla-usb-laddare-med-1-port-vit-40412278/) (prisvärt och [säker](https://youtu.be/uRe9w5PKmsE)), [Kjell](https://www.kjell.com/se/sortiment/dator-natverk/datortillbehor/usb-tillbehor/usb-laddare/linocell-mini-usb-laddare-2-4-a-svart-p95717), [Biltema](http://www.biltema.se/sv/Kontor---Teknik/Mobilt/Kablar-och-laddare/Reseladdare-USB-2000036148/)]
  * Buntband [[Bauhaus](https://www.bauhaus.se/buntband-100-x-2-5-transparent-100-pack.html)]
  * Slang, invändig diameter 6 mm, längd ca. 20 cm [[Bauhaus](https://www.bauhaus.se/pvc-slang-6x1-5mm.html), [Biltema](http://www.biltema.se/sv/Bat/VVS/Slang/Vattenslang-10-m-2000017745/?artId=15330)]
  * 2x avloppsböj som väderskydd (böj 87°, Ø 75mm, t.ex. Marley Silent HT) [[Bauhaus](https://www.bauhaus.se/ht-avloppsror-boj-87-o75mm.html), [Biltema](http://www.biltema.se/sv/Bygg/VVS/Ror-och-rordelar/Avloppsror-och-rordelar/Avloppsboj-2000023051/?artId=87264)]

Har du hittat nån bra källa för en byggdel? Hör av dig till [{{ site.contact }}](mailto:{{ site.contact }}) så lägger vi till infon här.

## Färdiga paketeringar

  * [r-pi.se](https://r-pi.se) erbjuder [ett färdigt "Luftpaket"](https://r-pi.se/labb-experiment/vader/luftdatas-luftkitt-med-partikelmatning) som innehåller alla delar som behövs.
  * Vi anordnar workshops där vi försöker tillhandahålla alla delar antingen till självkostnadspris eller kostnadsfritt om vi lyckas hitta en sponsor för workshopen. Håll koll på [nyhetsflödet](/nyheter) och [Facebook-gruppen](https://www.facebook.com/groups/luftbubblan/) för att få uppdateringar om planerade workshops!

{% if page.pagination.next %}
---
#### Nästa steg: [{{ page.pagination.next.name }}]({{ page.pagination.next.link }})
{% endif %}
