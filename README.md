# AAVA Dataset Repo

Quick location to store the basic data and documentation on how to convert the google docs to the appropriate geojson files.

## Requirements

1. https://github.com/teknofire/yak
2. gdal
3. this repo

## Instructions for converting datasets into geojson

1. Download doc as CSV file, the filename depends on what the dataset is coming from, just replace the existing csv file in the appropriate sub directory.
2. Run the yak command listed for the dataset
3. Go to the [ubermap](http://ubermap.gina.alaska.edu/) edit page and open the data tab
4. Under upload new file click the "Choose File" button and select the updated geojson generated by the yak command
5. Click the "Save" button.  Map should refresh with the latest points.

## ToolikLake_TVEXPORT

Very basic conversion of the csv to a geojson, nothing special here.

Google Doc: https://docs.google.com/a/gina.alaska.edu/spreadsheets/d/1T-nP10lMuV5B20E5rDKA0rG1AES8O6AI8bAiqXrdnt4/edit#gid=311456934

Ubermap edit: http://ubermap.gina.alaska.edu/geojson_layers/2/edit

    yak geojson -f -p EPSG:4326 ToolikLake_TVEXPORT.vrt
    
## AAVA Points of Interest

This csv file gets split into multiple files based on the group column.  Currently the only GeoJSON file that gets used is the one for group 0.

Google Doc: https://docs.google.com/a/gina.alaska.edu/spreadsheets/d/1ZJwLMz2r4KO5uvCdRo_1hjlV8P-NdMJ1IIsbtq-gC7s/edit?usp=sharing

Ubermap edit: http://ubermap.gina.alaska.edu/geojson_layers/1/edit

    yak geojson -f -p EPSG:4326 -s group AAVA_Datasets_Grouped.vrt
