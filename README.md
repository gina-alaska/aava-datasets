# AAVA Dataset Repo

Quick location to store the basic data and documentation on how to convert the google docs to the appropriate geojson files.

## Requirements

1. https://github.com/teknofire/yak
2. gdal
3. this repo

## New instructions 2.0!!!

1. clone this respository
  
  `git clone git@github.com:gina-alaska/aava-datasets`

3. cd into the subdirectory with the dataset you wish to updated
3. Run the updater!
  
  on OSX run `yak aava`

  on Linux run `yak aava -b firefox` or whatever browser you want it to use
4. In the browser go to the data tab and click the "Choose file" button
5. Browse to the directory and find the file that you are trying to update.  
6. Click the "Save" button

## Manual instructions for converting datasets into geojson

1. Download doc as CSV file, the filename depends on what the dataset is coming from, just replace the existing csv file in the appropriate sub directory.
2. Run the yak command listed for the dataset
3. Go to the [ubermap](http://ubermap.gina.alaska.edu/) edit page and open the data tab
4. Under upload new file click the "Choose File" button and select the updated geojson generated by the yak command
5. Click the "Save" button.  Map should refresh with the latest points.

## ImnavaitCreek_TVEXPORT

Google Doc: https://docs.google.com/a/alaska.edu/spreadsheets/d/1MphOrOIdkEd3kh4FaL-ioqNXhLOvK0TtJxiB_ImLkhM/edit#gid=0

Ubermap Edit: http://ubermap.gina.alaska.edu/geojson_layers/5/edit

Convert command

    yak geojson -f -p EPSG:4326 *.vrt  

## HAPPYVALLEY_TVEXPORT

Google Doc: https://docs.google.com/a/alaska.edu/spreadsheets/d/1MEujZvicnEYZSs0XbI57kevMcSMlVbpPI0qD84zReJk/edit#gid=899663236

Ubermap Edit: http://ubermap.gina.alaska.edu/geojson_layers/6/edit

Convert command

    yak geojson -f -p EPSG:4326 *.vrt

## ToolikLake_TVEXPORT

Very basic conversion of the csv to a geojson, nothing special here.

Google Doc: https://docs.google.com/a/alaska.edu/spreadsheets/d/1T-nP10lMuV5B20E5rDKA0rG1AES8O6AI8bAiqXrdnt4/edit#gid=311456934

Ubermap edit: http://ubermap.gina.alaska.edu/geojson_layers/2/edit

    yak geojson -f -p EPSG:4326 ToolikLake_TVEXPORT.vrt

## AAVA Points of Interest

This csv file gets split into multiple files based on the group column.  Currently the only GeoJSON file that gets used is the one for group 0.

Google Doc: https://docs.google.com/a/gina.alaska.edu/spreadsheets/d/1ZJwLMz2r4KO5uvCdRo_1hjlV8P-NdMJ1IIsbtq-gC7s/edit?usp=sharing

Ubermap edit: http://ubermap.gina.alaska.edu/geojson_layers/1/edit

    yak geojson -f -p EPSG:4326 -s group AAVA_Datasets_Grouped.vrt

## willows_tvexport

Google Doc: https://docs.google.com/a/alaska.edu/spreadsheets/d/1y1fOsxCOTyE-MMzGPsgGl_71Yf3ipaWQQw0EhBnvteQ/edit#gid=0

Ubermap edit: http://ubermap.gina.alaska.edu/geojson_layers/8/edit

Convert command

    yak geojson -f -p EPSG:4326 willows_tvexport.vrt

## poplars_tvexport

Google Doc: https://docs.google.com/a/alaska.edu/spreadsheets/d/11eba-_-m--PGfeteshdjr7hVhW-SOhVrgX_MCkVjcAQ/edit#gid=0

Ubermap edit: http://ubermap.gina.alaska.edu/geojson_layers/7/edit

Convert command

    yak geojson -f -p EPSG:4326 poplars_tvexport.vrt

## oumalik_tvexport

Google Doc: https://docs.google.com/a/alaska.edu/spreadsheets/d/120V0NK9n-627Krs2d2xAwD6ibMka5qxSmNuF-rSdy-s/edit#gid=0

Ubermap edit: http://ubermap.gina.alaska.edu/geojson_layers/9/edit

Convert command

    yak geojson -f -p EPSG:4326 oumalik_tvexport.vrt

## prudhoe_tvexport

Google Doc: https://docs.google.com/a/alaska.edu/spreadsheets/d/1ph7aiXTL5B2lPB3lNXsJ-bqh4SaBaAz-qyPyXjI2TmM/edit#gid=0

Ubermap edit: http://ubermap.gina.alaska.edu/geojson_layers/3/edit

Convert command

    yak geojson -f -p EPSG:4326 prudhoe_tvexport.vrt

## frostboils_tvexport

Google Doc: https://docs.google.com/a/alaska.edu/spreadsheets/d/1wsH84xwmSR4vNjhypDvqdtd5Od5VGVB3amGdKX3c3NM/edit#gid=0

Ubermap edit: http://ubermap.gina.alaska.edu/geojson_layers/10/edit

Convert command

    yak geojson -f -p EPSG:4326 frostboils_tvexport.vrt

## Atqasuk

Google Doc: https://docs.google.com/spreadsheets/d/17fXKyj54mTsPKZjqHlYANL1LzURpRP8XpfpcNuIIAV8/edit#gid=0

Ubermap edit: http://ubermap.gina.alaska.edu/geojson_layers/12/edit

Convert command

    yak geojson -f -p EPSG:4326 Atqasuk.vrt

## tfire

Google Doc: https://docs.google.com/spreadsheets/d/1JsuKIcLNiqY0hUXJCj2ExJ88qTxQ6PVfN28x99NhVz8/edit#gid=0

Ubermap edit: http://ubermap.gina.alaska.edu/geojson_layers/13/edit

Convert command

    yak geojson -f -p EPSG:4326 tfire.vrt


## nome_tvexport

Google Doc: https://docs.google.com/a/alaska.edu/spreadsheets/d/1JxhCAQPvcGluigToUjKdTQ9JO6jMVkxuDBGHt6i-fXw/edit

Ubermap edit: http://ubermap.gina.alaska.edu/geojson_layers/14/edit

Convert command

    yak geojson -f -p EPSG:4326 nome_tvexport.vrt

## atlas1

Google Doc: https://docs.google.com/spreadsheets/d/1XnoIqzhNj0NekVew3tyKoF9DL-hk_5SkrMC7-qlpSZ8/edit

Ubermap edit: http://ubermap.gina.alaska.edu/geojson_layers/87/edit

Convert command

    yak geojson -f -p EPSG:4326 atlas1.vrt


## atlas2

Google Doc: https://docs.google.com/spreadsheets/d/1a5SAH0SRNeQmiZQdlSZZdIdhagxzXxY05knUmHsuaqU/edit

Ubermap edit: http://ubermap.gina.alaska.edu/geojson_layers/90/edit

Convert command

    yak geojson -f -p EPSG:4326 atlas2.vrt

## barrow-ibp

Google Doc: https://docs.google.com/spreadsheets/d/160jb4039Hp2SN7tFEJXblXPjo3mZ6eUJm4BU-R9E4ns/edit#gid=0" > barrow-ibp.csv

Ubermap edit: http://ubermap.gina.alaska.edu/geojson_layers/91/edit

Convert command

    yak geojson -f -p EPSG:4326 barrow-ibp.vrt

## barrow-ngee

Google Doc: https://docs.google.com/a/alaska.edu/spreadsheets/d/1bJsWoFxtDKAcSp28yWFmRZODV8RZHzMpKjpO3a6viME/edit?usp=drive_web" > barrow-ngee.csv

Ubermap edit: http://ubermap.gina.alaska.edu/geojson_layers/92/edit

Convert command

    yak geojson -f -p EPSG:4326 barrow-ngee.vrt
