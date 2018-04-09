---
section: Bygg en mätstation
layout: docs
title: Börja rapportera data
authors:
  - Luftdaten.info
  - Hannes Ebner
pagination:
  start:
    name: Kom igång
    link: /bygg/
  previous:
    name: Konfigurera mätstationen
    link: /bygg/konfigurera/
lead: false
wide: true
---

Vi behöver lite information innan din mätstation blir en del av nätverket och dyker upp på "partikelkartan". Skicka ett mail till [{{ site.contact }}](mailto:{{ site.contact }}) med följande information:

  - ID av din NodeMCU som alltid är synlig högst upp i webbgränssnittet. IDn var också synlig som siffra i WLAN-namnet när du konfigurerade din mätstation ("Feinstaubsensor-`ID`"). 
  - Din adress: gatuadress med postnummer och ort (publiceras inte och används enbart för att beräkna grova koordinater till kartan).
  - Beskrivning av stationens omgivning, t.ex. höjd över mark, närhet till väg, trafikmängd eller liknande.
  - Din e-post-adress (publiceras inte).

<div class="note">
  <h6>Frågor?</h6>
  <p>Om du fortfarande har frågor efter att ha läst våra <a href="/faq">vanliga frågor</a> eller dessa <a href="/bygg">instruktioner</a> så får du gärna ta kontakt med oss via våra <a href="/om#contact">kontaktvägar</a>.</p>
</div>

{% if page.pagination.next %}
---
#### Nästa steg: [{{ page.pagination.next.name }}]({{ page.pagination.next.link }})
{% endif %}
