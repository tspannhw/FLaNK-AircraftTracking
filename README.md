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


#### Other Source Code Options including Apache Pulsar


Function Source: https://github.com/tspannhw/pulsar-adsb-function

Analytics Source: https://github.com/tspannhw/FLiP-Py-ADS-B


#### Videos

* https://www.youtube.com/watch?v=0LMOglFN8ZA
  
