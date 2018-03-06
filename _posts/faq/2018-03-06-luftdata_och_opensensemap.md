---
layout: post
title: "Skicka Luftdata till opensensemap"
date: 2018-03-06
categories: faq
wide: true
permalink: /faq/luftdata-till-opensensemap
authors:
  - Luftdaten.info
  - Erik Näsström
---

# Registrera en Luftdata.se partikelsensor på openSenseMap
Du kan dela med dig av datan från din partikelsensor till openSenseMap om du följer dom här stegen.

## 1. Leta reda på inställningarna för din sensor och [registrera](https://opensensemap.org/register) en ny senseBox
- Genom webgränssnittet för din partikelmätare kan du se vilka sensorer du har anslutit([Fig. 1](#figure-1-webinterface-particualte-matter-sensor)).
- Gå till [https://opensensemap.org/register](https://opensensemap.org/register), fyll i ditt namn, plats och övriga uppgifter.
- I avdelningen **Hardware** väljer du **luftdaten.info**. Välj nu korrekt konfiguration enligt den/de sensorer som du har i din lokala installation ([Fig. 2](#figurre-2-registration-on-opensensemap)).
- Avsluta registreringen
- **OBS:** Kopiera ditt senseBox ID. Detta är en 24 tecken lång sträng som ser ut som denna: *58a88c6b650831d8a3625e01*
- Om du registrerade dig med en giltig e-post fpr du även ditt ID via e-post.

## 2. Ställ in din sensor
- Gå till webbgränssnittet för din sensor.
- Öpnna konfigurationen.
- Klistra in ditt senseBox ID i rutan bredvid **Send to openSenseMap** och kryssa i rutan.
- Spara inställningarna med knappen längst ned på sidan.

## Färdigt
Din sensor bör nu börja skicka sin data även till openSenseMap!

## Figur 1: Webbgränssnitt för partikelsensor
_Här ser du vilka sensorer du har kopplade till just din partikelsensor samt rutan längst ned där du klistrar in ditt ID_<br>
<img src="/assets/luftdata_opensensemap.png"/>

## Figur 2: Registrering hos openSenseMap
_Här väljer du samma uppsättning med sensorer som du har i Fig.1_<br>
<img src="/assets/sensebox_luftdaten.png"/>
