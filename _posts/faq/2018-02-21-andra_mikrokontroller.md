---
layout: post
title: "Andra mikrokontroller?"
date: 2018-02-21 21:00:00
categories: faq
wide: true
permalink: /faq/andra-mikrokontroller
authors:
  - Erik Näsström
---

Som det nämns i Bygg guiden så finns det flera olika versioner av NodeMCU korten och även andra versioner som går att använda. Här följer information om hur du ser skillnad mellan dom och hur du monterar respektive variant.

| Generation        | Version           | “Vanligt” Namn  |
| ------------- |:-------------:| -----:|
| 1a      | 0,9 | V1 |
| 2a      | 1,0      |   V2 |
| 2a | 1,0      |    V3 |

Det som jag har skrivit som _Vanligt namn_ är vad de olika korten kallas på diverse inköpssidor. Den största skillnaden mellan V2 och V3
är att V3 tillverkas av flera olika aktörer som t.ex. Lolin och är en aning bredare än V2 korten.

## NodeMCU V1
Originalet men nu väldigt efter i utvecklingen och går knappt att hitta. Oftast med ett gult kretskort och måtten 47mm x 31mm.

Den har en ESP-12 modul och 4MB flashminne

| Utseende        | Kopplingsschema           |
| ------------- |:-------------:| 
| <img src="https://i1.wp.com/www.esp8266learning.com/wp-content/uploads/2016/03/NodeMCU-v0.9.jpg" width="240" /> | <img src="/assets/NodeMCU_v1.svg" width="240" /> |

## NodeMCU v2

V2 fixade en del problem med V1 som t.ex. bredden så att den passar in bättre på ett breadboard. Chippet uppgraderades från ESP-12 till ESP-12E

| Utseende        | Kopplingsschema           |
| ------------- |:-------------:| 
| <img src="https://www.conrad.com/medias/global/ce/9000_9999/9400/9430/9437/1613301_ZB_00_FB.EPS_1000.jpg" width="240" /> | <img src="/assets/NodeMCU_v2.svg" width="240" /> |


## NodeMCU v3

V3 är den vanligaste kopian som går att beställas från t.ex. aliexpress, wish osv. men det finns inget officiellt 3e generationskort. V3 är en mindre ändrad variant av tillverkaren LoLin, skillnader är exempelvis USB ström ut och GND istället för 2 reservportar som finns på V2.

Se upp med dessa kort dock, deras fotavtryck är betydligt större än V2 så om du har ett kretskort som den skall passa i så kommer det att skilja mellan storlekarna.

| Utseende        | Kopplingsschema           |
| ------------- |:-------------:| 
| <img src="https://cdn.tindiemedia.com/images/resize/ewVRNa1aQJp9kjQbuJhJnCYxkIk=/p/full-fit-in/2400x1600/i/52445/products/2016-06-26T18%3A06%3A06.695Z-2.jpg" width="240" /> | <img src="/assets/NodeMCU_v3.svg" width="240" /> |

## Wemos D1 mini

Wemos D1 Mini är nykommlingen och som börjat användas mer än NodeMCU korten. Den har samma bredd som NodeMCU V2 men med sina 34,2mm höjd är den nästan en tredjedel kortare. Hårdvaran är en ESP-8266EX MCU och den har 4Mb flashminne, den har 9 GPIO pinnar vilket bör räcka för de flesta projekten.

| Utseende        | Kopplingsschema           |
| ------------- |:-------------:| 
| <img src="/assets/wemos_photo.jpeg" width="240" /> | <img src="/assets/Wemos_D1_Mini.svg" width="240" /> |
