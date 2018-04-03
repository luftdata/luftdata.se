---
layout: post
title: "Luftdata i Grafana"
date: 2018-03-06
categories: faq
wide: true
permalink: /faq/luftdata-i-grafana
authors:
  - Erik Näsström
---
[Grafana](https://grafana.com/)
är en plattform för att visualiser och analysera data via diagram och tabeller. För att kunna använda Grafana för att visualisera din data måste du även ha en databas, Grafana stödjer flera olika databaser som t.ex.:
* Graphite
* InfluxDB
* MySQL
* PostgreSQL

Och många fler, du hittar en komplett lista på deras [hemsida](https://grafana.com/plugins?type=datasource)
Den vanligaste är InfluxDB och resten av instruktionerna kommer att bygga på att den används.

## Docker installation
Lättast är att använda denna färdiga docker installation som ger dig Telegraf (StatsD), InfluxDB och Grafana i ett färdigkonfigurerat paket: [Länk](https://github.com/samuelebistoletti/docker-statsd-influxdb-grafana)

## Manuell installation

### 1. Installera InfluxDB
Då SD kort är känsliga för stora mängder data som skrivs och läses så rekommenderas det att installera din databas på en separat enhet, InfluxData har guider för hur du genomför installationen på flera olika system här: [LÄNK](https://docs.influxdata.com/influxdb/v1.4/introduction/installation)

Vill du trots varningen installera InfluxDB på din raspberry följer instruktionerna nedan.

```
# ladda hem http transport 
sudo apt-get install apt-transport-https
curl -sL https://repos.influxdata.com/influxdb.key | sudo apt-key add - source /etc/os-release

# Kommandot ovan borde ge ett "OK" om allt gick vägen.
echo "deb https://repos.influxdata.com/debian jessie stable" | sudo tee /etc/apt/sources.list.d/influxdb.list
sudo apt-get update && sudo apt-get install influxdb
```

Byt ut jessie i kommandot ovan om du kör en annan version.

Om du inte fick något felmeddelande så är det nu dags att konfigurera InfluxDB

```
# För att konfigurera tjänsten körs följande kommando: 
sudo nano /etc/influxdb/influxdb.conf
# editera följande tre rader genom att ta bort  "#" tecknet. 
# [http]
  # Determines whether HTTP endpoint is enabled.
   enabled = true
  # The bind address used by the HTTP service.
   bind-address = ":8086"
  # Determines whether HTTP authentication is enabled.
   auth-enabled = false
  # The default realm sent back when issuing a basic auth challenge.
  # realm = "InfluxDB"
  # Determines whether HTTP request logging is enable.d
  # log-enabled = true
#### 
För att sedan spara tryck ctrl+x och Y och enter
```
Skriv sedan `service influxd restart` i din terminal och tryck Enter för att starta om IndluxDB.

Om allt fungerade skall du kunna surfa in på {ip-adressen}:8083 och få upp en sida med texten<br>
```404 page not found```
<br>
Nästa steg är att i terminalen skapa en ny databas genom följande kommandon:
```
sudo influx
CREATE DATABASE luftdata
```
För att kontrollera att den verkligen skapades kan du skriva `show databases` och då skall den lista två stycken, `_internal`och `luftdata`som du just skapade.
```
root@InfluxDB:/ # influx
Visit https://enterprise.influxdata.com to register for updates, InfluxDB server management, and monitoring.
Connected to http://localhost:8086 version unknown
InfluxDB shell version: unknown
> create database luftdata2
> show databases
name: databases
---------------
name
_internal
luftdata
>
```
Om du vill kan du testa så att databasen fungerar genom att först köra kommandot `exit` för att läman influx konsolen och sedan köra följande kommando för att skriva värden till databasen:
```
curl -i -XPOST "http://localhost:8086/write?db=luftdata&precision=s" --data-binary 'test,sensornamn=Demo temperatur=50 '
```
Kör sedan följande kommando för att lista värdet igen:
```
influx -execute 'SELECT * FROM test' -database luftdata
```
Om det nu fungerade att skriva och läsa bör du få en tabell som nedan, antal värden beror på hur många gånger du körde det första kommandot:
```
root@InfluxDB:/ # influx -execute 'SELECT * FROM test' -database luftdata
name: test
----------
time                    sensornamn      temperatur
1522668199000000000     Demo            50
```

### 2. Installera Grafana
#### 2.1 Molntjänst
Ett alternativ är att använda Grafanas molntjänst, den är gratis men innehåller ett antal begränsningar:
* En Användare
* Upp till 5 dashboards
* SSL (inte en begränsning)

Om du vill använda deras molntjänst så klickar du på den högra bilden på https://grafana.com/get och följer deras instruktioner.

#### 2.2 Lokal installation
#### Lägg till några paket och bintrays nyckel till nyckelringen:
```
sudo apt-get install apt-transport-https curl
curl https://bintray.com/user/downloadSubjectPublicKey?username=bintray | sudo apt-key add -
```
#### Uppdatera Raspberryns APT källor<br>
**För Raspberry pi 1 och Raspberry Pi Zero W**<br>
`echo "deb https://dl.bintray.com/fg2it/deb-rpi-1b jessie main" | sudo tee -a /etc/apt/sources.list.d/grafana.list`<br>
**För Raspberry Pi 2 och Raspberry Pi 3**<br>
`echo "deb https://dl.bintray.com/fg2it/deb jessie main" | sudo tee -a /etc/apt/sources.list.d/grafana.list`<br>
_(byt ev. ut jessie i kommandona ovan om du använder en annan version)_<br>
#### Installera
```
sudo apt-get update
sudo apt-get install grafana
```
#### Starta servern (init.d service)
Starta Grafana genom att köra `sudo service grafana-server start`<br>
Detta kommer att starta Grafana server processen som grafana användaren som skapades under installationen. Standard port för HTTP är **3000* och användare och grupp är **admin**.

Om du vill ställa in så att grafana startar vid uppstart så kör kommandot:<br>
`sudo update-rc.d grafana-server defaults`

För att testa din Grafana installation så öppna en webbläsare och gå till {ip-adressen}:3000<br>
Du bör då komma till Grafanas startsida.

### 3. Koppla din partikelsensor till InfluxDB
Gå till konfigurationsskärmen för din partikelsensor och fyll i uppgifterna för din InfluxDB installation längst ned:<br>
<img src="/assets/luftdata_influxdb.png" /><br>
Spara och starta om din sensor, i fortsättningen kommer din partikelsensor att automatiskt rapportera sina mätvärden till din InfluxDB databas.

### 4. Skapa grafer i Grafana
När du har loggat in i Grafana så kan du skapa _"Dashboards"_ för uppsättningar av olika grafer och tabeller eller så kan du importera andra användares Dashboards som är gjorda för Luftdata.<br>
Du hittar dessa här: https://grafana.com/dashboards?search=luftdaten

Du kan även ta inspiration av några offentliga dashboards med aktuell data [här](http://luftdata.se/faq/grafana-dashboards)
