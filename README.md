# **Investigating Food Venue Concentration and Daytime Noise Complaints in Leeds**

## 1. Project Background
Food and drink venues support local economies, social life and evening activity, but they may also create noise management challenges in urban areas where homes and businesses are close together.

This project explores whether postcode sectors with more food and drink venues in Leeds also have more daytime noise nuisance complaints. It combines venue data, council complaint records, postcode lookup data and boundary data to identify spatial patterns and possible priority areas.

The aim is not to prove direct causation, but to provide evidence-based reference suggestions for noise control at the Leeds municipal level, community planning decisions, order management by local businesses, and environmentally sensitive homebuyers.

## 2. Repository Contents
This repository contains the following main files and folders:

- `README.md`  
  Provides the project background, data information, project aims, and reproducibility guide.

- `Programming_Project.ipynb`  
  Contains the full Python workflow for data cleaning, spatial processing, statistical analysis, and visualisation.

- `data_raw/`  
  Stores the original datasets used in the project. For seamless reproducibility, the notebook accesses these files directly via their GitHub raw URLs

- `data_processed/`  
  Stores cleaned or processed datasets generated during the analysis.

- `output/`  
  Stores the final visualisation outputs, including one non-spatial figure and one spatial figure.

## 3. Data Information
This project uses open datasets to analyse the relationship between eating and drinking venues and noise nuisance complaints in Leeds. The datasets are stored in the `data_raw` folder.

- `Leeds_Food&Drink.csv`  
  Source: https://datamillnorth.org/dataset/places-to-eat-and-drink-in-leeds-2gp70  
  Use: Identifies food and drink venues in Leeds by postcode.  
  Attribution: Places to eat and drink in Leeds, © Leeds City Council, 2017. Licensed under the Open Government Licence.

- `Leeds_Noise.csv`  
  Source: https://datamillnorth.org/dataset/noise-nuisance-2rl31  
  Use: Provides daytime noise nuisance complaint records by postcode sector.  
  Attribution: Noise Nuisance, © Leeds City Council, 2017. Licensed under the Open Government Licence.

- `Leeds_ONSPD.csv`  
  Source: https://geoportal.statistics.gov.uk/datasets/ab22699816994c02bd4995e3f431e7e5/about  
  Use: Provides postcode coordinates and geographic lookup information.  
  Attribution: ONS Postcode Directory, Office for National Statistics, 2021. Licensed under the Open Government Licence v3.0.

- `Leeds_lsoa_resident_pop.csv`  
  Source: https://observatory.leeds.gov.uk/data-catalog-explorer/indicator/I351/?geoId=G1&view=table  
  Use: Provides contextual population information by LSOA.  
  Attribution: Resident population, indicator I351, Leeds Observatory, 2017.

- `Leeds.geojson`  
  Source: https://mapservices.leeds.gov.uk/arcgis/rest/services/Public/Boundary/FeatureServer  
  Use: Provides the Leeds boundary layer for spatial mapping.  
  Attribution: Leeds boundary data, Leeds City Council / ArcGIS Online. Contains OS data © Crown copyright and database right.

The noise data represent reported complaints rather than measured noise levels. Some supporting datasets do not exactly match the 2017 study period, so they are mainly used for postcode matching, mapping and contextual interpretation.

## 4. Project Aims
This project analyses whether postcode sectors with more food and drink venues in Leeds also have more daytime noise nuisance complaints. The code cleans and standardises the venue, complaint, postcode lookup, boundary and population datasets, then matches venue postcodes with ONSPD coordinates and aggregates both venue and complaint records to postcode-sector level.

The analysis uses descriptive statistics, correlation tests, a Poisson GLM and a 75th-percentile threshold to examine the overall relationship and identify local priority sectors. The final spatial and non-spatial visualisations provide reference suggestions for Leeds municipal noise control, community planning, business order management and environmentally sensitive homebuyers.

## 5. Reproducibility Guide
- Clone or download this repository.

- Open the project folder in VS Code, Jupyter Notebook, or another Python environment.

- Install the required packages if they are not already available:

```bash
pip install pandas numpy geopandas matplotlib statsmodels
```

- Open `Programming_Project.ipynb`.

- Run all sections from #1 to #11 without changing the section order.

- Make sure the notebook can access the fixed GitHub raw data links. An internet connection is required because the raw datasets are read directly from online URLs.

- Review the printed cleaning summaries, model outputs, priority postcode sectors, and final visualisations.

- To regenerate the final figures, rerun Sections 10 and 11 after all earlier data preparation and analysis sections have been completed.
