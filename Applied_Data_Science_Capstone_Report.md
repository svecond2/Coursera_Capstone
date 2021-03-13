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

### How the Data will be used
We'll use the first pack of data on the url which we will scrape into a pandas data frame. We'll have boroughs, neighbourhoods, total inhabitants and average age from the table on the page. This dataset is then bases for the analysis. TomTom API was selected as the most user friendly and permisive api to retrieve the longitude and latitude from the Neighbourhoods (as open street maps did not work correctly for example). When we retrieve the location data, we can get the venues for each Neighbourhood from the Foursquare API and get into clustering. Once we cluster our Neighbourhoods based on the venues, we will be able to chart that using Folium on the map and find the most interesting places to open our new Café. We'll focus on places where Café is not in the top 10 venues, however clusters should allow us to know, that the Café should work there as in other Neighbourhoods in the same cluster it works perfectly (as the Café is in the top 10). We'll try to also use geojson of the cycling paths and overlay it on the Folium map to see, which Neighbourhoods could have edge also based on Cyclists riding through there (and you might want to open Café close to the cycling lane).