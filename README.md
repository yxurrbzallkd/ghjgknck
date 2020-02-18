# MAP project
Given user location as longitude and latitude and a year makes a map with 10 closest film locations

## Usage
run main.py file and enjoy
![picture](image1.png)
![picture](image2.png)
![picture](image3.png)

## Libraries required
SQLITE3
```bash
pip install sql3
```
Geopy
```bash
pip install geopy
```
Pandas
```bash
pip install pandas
```
Folium
```bash
pip install folium
```
Flask
```bash
pip install flask
```

## Included files
all_cities.csv - merged data from 3 different datasets. Contains names of cities, their location as latitude and longitude and country they are in

For more information about the data, go to https://simplemaps.com/data/world-cities

c_to_c.pickle - dictionary {city: (latitude, longitude) for all known cities}
data.db - SQL database of films (title, country, state, city, latitude, longitude and more)

# Creation Process

## Stage 1: Parsing data
parser.py - parse data and turn it into an SQL database

## Stage 2: Finding closest films
get_ten_closest_movies_locations_with_titles in main.py
(retreive all movies from a certain year with an sql query and sort cities they were made in by proximity)

# Stage 3: Creating a Map
make_map in main.py
film locations are blue circles, 100 closest cities are marked by blue circles (the smaller they are, the further away city is) and user location is a red circle

## HTML
there are 2 html templates apart from the map itself
index.html and main.html
here is a lookthrough them:
The most important patr of main.html is:
```html
 <form method="post" action="/generate_map">
```
From here parameters (latitude, longitude and year) for generating the map are passed to generate_map function that returns html template of the created map