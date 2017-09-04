# INSPIRE ready Geoserver
INSPIRE ready geoserver (using app-schema from British Geological Survey)

## Background 

Example of INSPIRE and app-schema out of the box compose. The docker compose will build the structure referenced in the following report [INSPIRE WFS cookbook](https://data.gov.uk/sites/default/files/library/INSPIREWFSCookbook_v1.0.pdf): 

The docker compose uses 2 slightly modified images obtained in these repositories:

* [postgis](https://github.com/kartoza/docker-postgis)
* [geoserver](https://github.com/kartoza/docker-geoserver)

## Run it 

To run it is is best first to build the images:
```
docker-compose build --no-cache
```

And then to run it
```
docker-compose up
```

### Testing

Geoserver runs on port 8080 (ip: 10.10.10.2) and has the default geoserver login (admin:geoserver).

Geoserver:
```
http://10.10.10.2:8080/geoserver
http://localhost:8080/geoserver/ows?service=wfs&version=2.0.0&request=GetCapabilities
http://10.10.10.2:8080/geoserver/wfs?request=GetFeature&service=wfs&version=2.0.0&typeName=gsmlgu:GeologicUnit&outputFormat=gml32&count=2
```
And ETF
```
http://10.10.10.4:8080/etf-webapp
```


### Network

The containers run on network: *10.10.10.0/16* with gateway: 10.10.10.1




## Versions

* OS Debian Jesse
* Geoserver 2.11.2
* Postgresql 9.5
* Postgis 2.2

## Credits for geoserver

* Tim Sutton (tim@kartoza.com)
* Shane St Clair (shane@axiomdatascience.com)
* Alex Leith (alexgleith@gmail.com)

## Credits for postgis

* Tim Sutton (tim@kartoza.com)

