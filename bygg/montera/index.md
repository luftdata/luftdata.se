---
section: Bygg en mätstation
layout: docs
title: Montera mätstationen
authors:
  - Luftdaten.info
  - Hannes Ebner
pagination:
  start:
    name: Kom igång
    link: /bygg/
  previous:
    name: Koppla ihop elektroniken
    link: /bygg/koppla/
  next:
    name: Konfigurera mätstationen
    link: /bygg/konfigurera/
lead: true
wide: true
---

Nu ska vi fästa delarna i varandra och montera i väderskyddet.

Vi sätter ihop NodeMCU und partikelsensorn SDS011 med ett buntband så att WLAN-antennen pekar bort ifrån sensorn:

![](../img/montera_1.png)

Vi tar ytterligare ett buntband och fäster temperatursensorn på slangen:

![](../img/montera_2.png)

Vi drar USB-kabel genom en avloppsböj (börja på sidan utan tätning) och ser till att partikelsensorns fläkt är på undersidan. Skjut in delarna så att sensorn sitter fast i rörets böj, slangen och USB-kabeln ska sticka ut på andra sidan:

![](../img/montera_3.png) | ![](../img/montera_4.png)

![](../img/montera_5.png) | ![](../img/montera_6.png)

Nu är vi nästan klara. Vi tar en till avloppsböj och skjuter på den första (utan att klämma några kablar). Temperatursensorn positionerar vi så att den hamnar strax innanför rörändan. Om slangen sticker ut mycket kan den kortas ner, men den ska sticka ut nån centimeter.

Dra myggnät eller liknande över rörens öppna ändar så att insekter hindras från att komma in.

{% if page.pagination.next %}
---
#### Nästa steg: [{{ page.pagination.next.name }}]({{ page.pagination.next.link }})
{% endif %}