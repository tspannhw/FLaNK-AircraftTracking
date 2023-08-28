# FLaNK-AircraftTracking

FLaNK Aircraft Tracking with ADSB antenna and REST




### Resources

#### REST

OpenSky Network REST API

* https://github.com/tspannhw/FLaNK-ADSB/tree/main


#### FlightAware

https://flightaware.com/adsb/stats/user/TimothySpann


#### Hardware

* https://flightaware.store/products/indoor-antenna-17cm-two-coil

* https://flightaware.store/products/pro-stick-plus

* setup https://www.flightaware.com/adsb/piaware/build

#### Flightaware Web page

This is your local IP and is linked off your flightaware page

* http://192.168.1.161:8080/

#### OpenSky REST API

https://openskynetwork.github.io/opensky-api/rest.html

#### Important Fields

* field: hex is ICAO identifier
* field: flight is IDENT identifier
* field: altBaro is the altitude in feet (barometric)
* field: lat, lon is latitude and longitude
* field: gs is the ground speed in knots
* field: altGeom is altitude (geometric)

Schema:   https://github.com/tspannhw/pulsar-adsb-function/blob/main/aircraft.schema


#### Managing MiNiFI Agent on ADSB Device

Link:   http://nifi1:10090/efm/ui/


https://medium.com/cloudera-inc/using-apache-nifi-to-backup-and-restore-minifi-flows-from-cloudera-efm-87f303b56ebd

https://medium.com/cloudera-inc/edge-managing-c-and-java-agents-d6590c963e9c



#### MiNiFi Agent Flow

Reads JSON data from ADSB REST endpoint -> http://localhost:8080/data/aircraft.json?_=${random()}


#### Articles

* https://medium.com/@tspann/tracking-aircraft-in-real-time-with-open-source-554124125011
* https://community.cloudera.com/t5/Community-Articles/Ingesting-Flight-Data-ADS-B-USB-Receiver-with-Apache-NiFi-1/ta-p/247940
* 


#### Flink SQL Queries

````

select alt_baro,
       gs,
       alt_geom,
       baro_rate,
       mach, 
       hex, flight, lat, lon
from aircraft;

select max(alt_baro) as MaxAltitudeFeet, min(alt_baro) as MinAltitudeFeet, avg(alt_baro) as AvgAltitudeFeet,
       max(alt_geom) as MaxGAltitudeFeet, min(alt_geom) as MinGAltitudeFeet, avg(alt_geom) as AvgGAltitudeFeet,
       max(gs) as MaxGroundSpeed, min(gs) as MinGroundSpeed, avg(gs) as AvgGroundSpeed, 
       count(alt_baro) as RowCount, 
       hex as ICAO, flight as IDENT
from aircraft 
group by flight, hex;


select icao24, callsign, firstSeen, lastSeen, estDepartureAirport, estArrivalAirport, arrivalAirportCandidatesCount,
      estDepartureAirportHorizDistance, estDepartureAirportVertDistance, estArrivalAirportHorizDistance, 
      estArrivalAirportVertDistance, departureAirportCandidatesCount
from openskyairport


select * from `sr1`.`default_database`.`adsb`



````

#### Other Source Code Options including Apache Pulsar


Function Source: https://github.com/tspannhw/pulsar-adsb-function

Analytics Source: https://github.com/tspannhw/FLiP-Py-ADS-B

OpenSky REST NiFi:  https://github.com/tspannhw/FLaNK-ADSB




#### Videos

* https://www.youtube.com/watch?v=0LMOglFN8ZA
  
