---
title: Dataåtkomst
lang: sv
layout: docs
wide: true
authors:
 - Hannes Ebner
lead: true
---
Det finns flera olika sätt att komma åt all data som skickas till luftdaten.info. Denna sida sammanfattar åtkomst- och licensinformation.

## API

Det finns olika åtkomstpunkter, beroende på vilka data man vill komma åt. API:et levererar endast data som är aktuell nu, samt genomsnittsvärden för de senaste 5 minuter, den senaste timmen och de senaste 24 timmar.

### Aktuell data (de senaste 5 minuter)

- Alla sensorer: `http://api.luftdaten.info/static/v1/data.json`
- En specifik sensor: `http://api.luftdaten.info/v1/sensor/{apiID}/`
- Alla sensorer som matchar parametrarna: `http://api.luftdaten.info/v1/filter/{query}`
  - `type={sensor type}`: comma separated list of sensor types, i.e. 'SDS011,BME280'
  - `area={lat,lon,distance}`: all sensors within a max. radius
  - `box={lat1,lon1,lat2,lon2}`: all sensors in a 'box' with the given coordinates
  - `country={country code}`, t.ex. `SE`
  
### Genomsnittsdata för olika tidsperioder
  
- http://api.luftdaten.info/static/v2/data.json - average of all measurements per sensor of the last 5 minutes for all sensors
- http://api.luftdaten.info/static/v2/data.1h.json - average of all measurements per sensor of the last hour
- http://api.luftdaten.info/static/v2/data.24h.json - average of all measurements per sensor of the 24 hours
- http://api.luftdaten.info/static/v2/data.dust.min.json - same as data.json but dust sensors only
- http://api.luftdaten.info/static/v2/data.temp.min.json - same as data.json but temp./humidity/air pressure sensors only

## Arkiv

Utöver API:et med realtidsdata finns även ett arkiv med CSV-dumpar på [`http://archive.luftdaten.info`](http://archive.luftdaten.info/). Varje mapp motsvarar en dag och innehåller alla mätningar för samtliga sensorer. Filnamnen är uppbyggda enligt följande schema: `YYYY-MM-DD_<sensor-typ>_sensor_<sensor-id>.csv`.

Du kan enkelt ta reda på en sensors ID-nummer genom att klicka på en sensor på kartan, "Sensor ID" dyker sedan upp i listan till höger:

![Hitta sensor ID](img/sensorid.png) 

## Licenser

Licensen för data är [Database Contents License (DbCL) v1.0](https://opendatacommons.org/licenses/dbcl/1-0/).

Licensen för mjukvaran [airrohr-firmware](https://github.com/opendata-stuttgart/sensors-software/tree/master/airrohr-firmware) är [GNU General Public License (GPL) v3](https://www.gnu.org/licenses/gpl-3.0.en.html).