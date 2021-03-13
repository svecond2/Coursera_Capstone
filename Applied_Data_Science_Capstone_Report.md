# Applied Data Science Report

@created by Ondrej Svec

## Introduction
I've chosen the challenge of recommendation of the best spot to open a new Café in a beautiful city of Prague. The focus will be to find out the Neighbourhoods which are most suitable for that task, but actually do not have Café in any of the top 10 venues and also have a good amount of inhabitants in the area. We'll use opendata from Prague, Foursquare data, TomTom api to get the locations of Neighbourhoods and also opendata of cycling paths (as we know that cyclists love to get coffee). 

## Data
We'll use the following data in the capstone:
* Neighbourhoods and boroughs of Prague with total number of inhabitants and average age: https://vdb.czso.cz/vdbvo2/faces/cs/index.jsf?page=vystup-objekt&z=T&f=TABULKA&skupId=1372&katalog=30845&pvo=DEM01D-PHA&pvo=DEM01D-PHA&str=v33&c=v3~2__RP2019MP12DP31#fx=0
* TomTom API to retrieve longitude and latitude based on Neighbourhoods
* Foursquare data to retrieve venues (explore endpoint) located in the Neighbourhoods
* GeoJson with the cycling paths: http://opendata.iprpraha.cz/CUR/DOP/DOP_Cyklogenerel_l/WGS_84/DOP_Cyklogenerel_l.json