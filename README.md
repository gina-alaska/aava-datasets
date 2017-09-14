# AAVA Dataset Repo

Quick location to store the basic data and documentation on how to convert the google docs to the appropriate geojson files.

## Requirements

1. https://github.com/teknofire/yak
2. gdal
3. this repo

## New instructions 2.0!!!

### Getting started
1. Clone this respository  
  `git clone git@github.com:gina-alaska/aava-datasets`
2. Make sure that the `yak` command is installed and `yak aava --help` is available. (http://github.com/teknofire/yak)
3. `cd aava-datasets`

### Adding new datasets

#### Create ubermap layer
1. Create new geojson_layer in http://uber.mapbits.org

   **NOTE:** Until the layer is added to a map it is useful to include the data set name in the layer name.  After it has been added to a map it can then be changed to just say "Plot Locations"
2. Copy contents for style, popup and options tab from an existing layer to the new layer.
3. Make note of url for the layer this will need to be used layer.  (example: http://uber.mapbits.org/orgs/aaga/geojson_layers/105/edit)
4. Create a new map that loads the layer.  Example: http://uber.mapbits.org/orgs/aaga/maps/oumalik

#### Create geojson file from google spreadsheet

1. Create a new directory for the dataset in the clone of the aava-datasets repository.
2. Initialize the new dataset directory
  ```
  mkdir AWESOME_DATASET
  cd AWESOME_DATASET
  yak aava --init .
  # note on a linux system you will need to specify the --browser flag
  yak aava --init --browser firefox .
  ```
  This will ask a series of questions about the dataset.
  1. URL for google spreadsheet to download.  This should be the shared link url that can be found by clicking on the `Share` button on the top right and then clicking
  2. URL for the ubermap layer to save the geojson for that you noted above.  This should reference a geojson_layer and not a map or other type of layer.  Example: http://uber.mapbits.org/orgs/aaga/geojson_layers/105/edit
3. This should then open a browser window to the specified ubermap layer window.
4. Click the data tab and upload the generated geojson file.

#### Troubleshooting issues with creating new layers

1. If the Google spreadsheet is not set to be sharable via url the CLI tool will be unable to export the CSV version in order to convert to a GeoJSON file.
2. In order to convert the geojson file from a CSV to a GeoJSON the CSV needs to contain a `lat` and `lon` columns.  You can look at the `.vrt` file to see exactly what fields or to customize the fields that it's trying to use for a particular dataset.

### Updating existing data set

1. cd into the subdirectory with the dataset you wish to updated
2. Run the updater!
    * on OSX run `yak aava`
    * on Linux run `yak aava -b firefox` or whatever browser you want it to use
3. In the browser go to the data tab and click the "Choose file" button
4. Browse to the directory and find the file that you are trying to update.  
5. Click the "Save" button

## Manual instructions for converting datasets into geojson

1. Download doc as CSV file, the filename depends on what the dataset is coming from, just replace the existing csv file in the appropriate sub directory.
2. Run the yak command listed for the dataset
3. Go to the [ubermap](http://ubermap.mapbits.org/) edit page and open the data tab
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

## legacy

Google Doc: https://docs.google.com/spreadsheets/d/1B3Zfsjz1WTVeck3qy1LxUE4PCZghm-nwHz1tVkChJe0/edit#gid=0

Ubermap edit: http://ubermap.gina.alaska.edu/geojson_layers/93/edit

Convert command

    yak geojson -f -p EPSG:4326 legacy.vrt

## pingos

Google Doc: https://docs.google.com/spreadsheets/d/1_auaWnrHv_7DzNPFJtcxIs52ETToEEVasDL3eAfUuAw/edit#gid=0

Ubermap edit: http://ubermap.gina.alaska.edu/geojson_layers/94/edit

Convert command

    yak geojson -f -p EPSG:4326 pingos.vrt

## prudhoe-bay-arcsees

Google Doc: https://docs.google.com/spreadsheets/d/15WD1v6Jvmx2zcT9zy-o49Wpl5vjNrHDh27lr3AS_tZE/edit#gid=0" > prudhoe-bay-arcsees.csv

Ubermap edit: http://ubermap.gina.alaska.edu/geojson_layers/95/edit

Convert command

    yak geojson -f -p EPSG:4326 prudhoe-bay-arcsees.vrt

## unalaska

Google Doc: https://docs.google.com/spreadsheets/d/1AiYW6ko0hhlfdm38bhNcSyJ9pZaZUoxBbcydY7G0ucY/edit#gid=0

Ubermap edit: http://ubermap.gina.alaska.edu/geojson_layers/96/edit

Convert command

    yak geojson -f -p EPSG:4326 unalaska.vrt

## northslope-arcss

Google Doc: https://docs.google.com/spreadsheets/d/1oNX_DDhEtXqb6a-zYwIOJEcKezDyDZXz4IeoyMli7Uk/edit#gid=0" > northslope-arcss.csv

Ubermap edit: http://ubermap.gina.alaska.edu/geojson_layers/97/edit

Convert command

    yak geojson -f -p EPSG:4326 northslope-arcss.vrt

## arctic-network

Google Doc: https://docs.google.com/spreadsheets/d/1omWwVidybUVjGB5tx2uXFK-geLmsAriYsfRDW243XTY/edit#gid=0" > arctic-network.csv

Ubermap edit: http://ubermap.gina.alaska.edu/geojson_layers/98/edit

Convert command

    yak geojson -f -p EPSG:4326 arctic-network.vrt

## flxtwrzona

Google Doc: https://docs.google.com/spreadsheets/d/1y1aQwW69lpE3_-cIQAhvh59hySx1cNeFRTbCFJM2QXU/edit#gid=899663236

Ubermap edit: http://uber.mapbits.org/orgs/aaga/geojson_layers/105/edit

Convert command

    yak geojson -f -p EPSG:4326 flxtwrzona.vrt

##hacmldbay

Google Doc: https://docs.google.com/spreadsheets/d/19hPsKk2F6bV-ZkVxo80dtKN5GMxkIENpTw9ROTiFOfQ/edit#gid=0

Ubermap edit: http://uber.mapbits.org/orgs/aaga/geojson_layers/112/edit

Convert command

    yak geojson -f -p EPSG:4326 hacmldbay.vrt

## hacmldbay

Google Doc: https://docs.google.com/spreadsheets/d/19hPsKk2F6bV-ZkVxo80dtKN5GMxkIENpTw9ROTiFOfQ/edit#gid=0

Ubermap edit: http://uber.mapbits.org/orgs/aaga/geojson_layers/112/edit

Convert command

    yak geojson -f -p EPSG:4326 hacmldbay.vrt
